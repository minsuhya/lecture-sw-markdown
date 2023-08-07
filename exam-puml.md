# UML - https://github.com/danielyaa5/puml-for-markdown/tree/main

@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Context.puml
!include https://raw.githubusercontent.com/minsuhya/lecture-sw-markdown/master/puml/c4_styles.puml
!include https://raw.githubusercontent.com/minsuhya/lecture-sw-markdown/master/puml/constants.puml

left header

\t<font size=22 color=black>$SYSTEM_NAME - System View</font>

\t<font size=14 color=#484848>The goals of my project are described here</font>

end header

System(sysName, "Labeling System\n", "", $sprite="cloud", $tags="primary", $link="./level_2_container_view.puml")

Boundary(labelers, ' \n<font color=black size=16>Labelers</font>', 'Human Resources') {
    Person(labelerB, "Labelers B", "Labeler Type 2\n", $tags="a")
    Person(labelerA, "Labelers A", "Labeler Type 2\n", $tags="a")
}
Rel_U(sysName, labelerB,"  Trigger samples for labeling")
Rel_D(labelerB, sysName," Store labeling results        ")

System(videoSamples, "Videos", "Users and internal customers", $sprite="youtube")
Rel_D(videoSamples, labelerA, " Send samples to labelers")

System(modelTrainingInference, "Model Training + Inference\n\n<font color=#e0575e><$RoboMaker></font>\n", "", $tags="secondary")
Rel_D(labelerA, modelTrainingInference," Send labels")
Rel_R(modelTrainingInference, sysName, "Send model scores")
Rel_L(sysName, modelTrainingInference, "Send labels")

HIDE_STEREOTYPE()
@enduml

#  system view

@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml
!include https://raw.githubusercontent.com/minsuhya/lecture-sw-markdown/master/puml/c4_styles.puml
!include https://raw.githubusercontent.com/minsuhya/lecture-sw-markdown/master/puml/constants.puml


left header

\t<font size=22 color=black>$SYSTEM_NAME - Container View</font>

\t<font size=14 color=black><U+25CF>  Goal 1</font>
\t<font size=14 color=black><U+25CF>  Goal 2</font>
\t<font size=14 color=black><U+25CF>  Goal 3</font>
\t<font size=14 color=black><U+25CF>  Goal 4</font>





end header


Person(labelerA, "Labeler A", "\t     Labeler-A Description     \t\n", $tags="a")
ContainerDb(bigQueryLabelDB, "LabelADb", "BigQuery", "A database where type A labels are stored")
ContainerDb(modelScoreDb, "ModelScoreDB", "BigQuery", "A database where model scores are stored")
Person(labelerB, "Labeler B", "\t     Labeler-B Description     \t\n", $tags="a")
ContainerDb($LABELED_DATASOURCE_ID, "$LABELED_DATASOURCE_NAME", "$LABELED_DATASOURCE_TYPE", $LABELED_DATASOURCE_DESC)
System_Boundary(sysName, ' \n<font color=black size=16>Label System FooBarBaz</font>') {
    Container(samplingPipeline, "Pipeline", "some-etl-framework", "ETL job for sampling / labeling", $tags="primary", $link="./level_3_component_view_pipeline.puml")
    Container(labelRetrievalJob, "LabelRetrievalJob", "some-etl-framework", "DAG for retrieving and storing label data from labelers.", $tags="primary", $link="./level_3_component_view_label_retrieval_job.puml")
    ContainerDb($SAMPLE_LABELS_ID, $SAMPLE_LABELS_TABLE, $SAMPLE_LABELS_TYPE, $SAMPLE_LABELS_COMPONENT_DESC)
    ContainerDb($DAILY_COLLECTED_SAMPLES_ID, $DAILY_COLLECTED_SAMPLES_TABLE, $DAILY_COLLECTED_SAMPLES_TYPE, $DAILY_COLLECTED_SAMPLES_DESC)
    ContainerQueue(sampleQueue, "SampleQueueFoo", "SQS", "Samples which should be double reviewed")
    Container(labelerBApi, "ReviewQueueAPI", "NodeJS", "API for pulling samples for review", $sprite="server")
    Container(btBqSnapshotJob, "ExportBigQuerySnapshot", "some-etl-framework", "A job to take daily BQ snapshots\nof //$SAMPLE_LABELS_TABLE//", $tags="primary", $link="./level_4_activity_diagram_export_bq_snapshot_job.puml")
}
System(modelTrainingInference, "Model Training + Inference\n\n<font color=#e0575e><$RoboMaker></font>\n", "")

Rel_R(samplingPipeline, $DAILY_COLLECTED_SAMPLES_ID, " ")
Rel_D(samplingPipeline, sampleQueue, " ")
BiRel_D($SAMPLE_LABELS_ID, samplingPipeline, " ")
Rel_L(labelRetrievalJob, $SAMPLE_LABELS_ID, " ")
Rel_L($LABELED_DATASOURCE_ID, labelRetrievalJob, " ")
Rel_R(sampleQueue, labelerBApi, " ")
Rel_R(labelerBApi, labelerB, " ")
Rel_R(labelerB, $LABELED_DATASOURCE_ID, " ")
Rel_L(modelScoreDb, samplingPipeline, " ")
Rel_D(modelTrainingInference, modelScoreDb, " ")
Rel_D(bigQueryLabelDB, modelTrainingInference, " ")
Rel_L(labelerA, bigQueryLabelDB, " ")
Rel_L($SAMPLE_LABELS_ID, modelTrainingInference, " ")
Rel_D($SAMPLE_LABELS_ID, btBqSnapshotJob, " ")

HIDE_STEREOTYPE()
@enduml

# Component View

@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Component.puml
!include https://raw.githubusercontent.com/minsuhya/lecture-sw-markdown/master/puml/c4_styles.puml
!include https://raw.githubusercontent.com/minsuhya/lecture-sw-markdown/master/puml/constants.puml

LAYOUT_LANDSCAPE()

left header

\t<font size=22 color=black>Some Job - Component View</font>

end header


Component(scheduler, "Scheduler", "some-etl-framework", "Kicks off the job at some interval")
Component(extractTransform, "DatasourceExtractTransform", "Operator", "Pull data from labeler datasource and perform any transforms before storing the data")
Component(loader, "DatasourceLoader", "Operator", "Update //$SAMPLE_LABELS_TABLE// with new labels")
Component(someMicroService, "SomeMicroService", "SubDag", "Foo bar baz")
Component(performCalculations, "PerformCalculation", "Operator", "Trigger the calculation of xyz")
Component(calculatePrevalence, "CalculatePrevalence", "Operator", "Trigger the calculation prevalence and store it")
ComponentDb($SAMPLE_LABELS_ID, $SAMPLE_LABELS_TABLE, $SAMPLE_LABELS_TYPE, $SAMPLE_LABELS_COMPONENT_DESC)

Rel_R(scheduler, extractTransform, " ")
Rel_R(extractTransform, loader, " ")
Rel_R(loader, performCalculations, "When all labels retrieved")
Rel_U(loader, $SAMPLE_LABELS_ID, " ")
Rel_D(loader, "someMicroService", " ")
Rel_R(performCalculations, calculatePrevalence, " ")

center footer



end footer

HIDE_STEREOTYPE()
@enduml

# test

@startuml
!include https://raw.githubusercontent.com/minsuhya/lecture-sw-markdown/master/puml/level_1_system_view.puml
@enduml

@startuml
!include https://raw.githubusercontent.com/minsuhya/lecture-sw-markdown/master/puml/level_2_container_view.puml
@enduml
