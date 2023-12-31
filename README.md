# SW Engineering 

## Table of Contents

<!-- vim-markdown-toc GFM -->

- [소프트웨어 공학 개요](#소프트웨어-공학-개요)
- [소프트웨어 개발 프로세스와 방법론](#소프트웨어-개발-프로세스와-방법론)
- [프로젝트 관리와 계획](#프로젝트-관리와-계획)
- [소프트웨어 요구공학(Software Requirements Engineering)](#소프트웨어-요구공학software-requirements-engineering)
- [소프트웨어 설계: CASE 도구, UML과 같은 표준 형식 사용](#소프트웨어-설계-case-도구-uml과-같은-표준-형식-사용)
- [소프트웨어 개발: 프로그래밍 언어로 소프트웨어를 구축](#소프트웨어-개발-프로그래밍-언어로-소프트웨어를-구축)
- [소프트웨어 테스트](#소프트웨어-테스트)
- [소프트웨어 유지보수](#소프트웨어-유지보수)
- [소프트웨어 품질](#소프트웨어-품질)
- [소프트웨어 형상 관리](#소프트웨어-형상-관리)

<!-- vim-markdown-toc -->

## 소프트웨어 공학 개요
  * 소프트웨어
  * 소프트웨어 위기
  * 소프트웨어 공학의 정의
  * 소프트웨어 공학 환경 - 계층화된 기술
  * 소프트웨어 프로세스 모델
  * 좋은 소프트웨어의 기준
## 소프트웨어 개발 프로세스와 방법론
  * 소프트웨어 구축 과정, 주요한 패러다임은 애자일 프로세스와 폭포수 프로세스
  * 소프트웨어 생명주기
  * 프로세스
     * 프로세스 종류
     * 프로세스 정의
     * 좋은 프로세스의 특성
  * 프로세스 모델
     * 폭포수 모델
     * 프로토타이핑 모델
     * 나선형 모델
     * 진화적 모델
     * V 모델
     * Unified Process
     * 애자일 프로세스
  * 지원 프로세스
     * 관리 프로세스
     * 품질보증 프로세스
     * 형상 관리 프로세스
  * 방법론
     * 구조적 방법론
     * 정보공학 방법론
     * 객체지향 방법론
## 프로젝트 관리와 계획
  * 개요
  * 프로젝트 시작
     * 프로젝트 가치
     * 프로젝트 리스크
     * 타당성 분석
  * 소프트웨어 일정 계획
     * 목표 설정
     * 프로젝트 범위
     * WBS
     * 스케줄링
  * 소프트웨어 규모의 산정
  * 소프트웨어 개발 비용 산정
     * COCOMO
     * 기능점수
  * 팀 구성
     * 팀 역할
     * 직능별 조직
     * 프로젝트별 조직
     * 매트릭스 조직
     * 애자일 조직
  * 실행과 모니터링
     * 프로젝트 실행
     * 프로젝트 모니터링
     * 번다운 차트
  * 위험 분석과 관리
     * 위험식별
     * 위험평가
     * 위험관리
## 소프트웨어 요구공학(Software Requirements Engineering)
  * 소프트웨어 요구사항: 소프트웨어 요구 사항의 추출, 분석, 명세, 검증
      * 기능 요구
      * 비기능 요구
      * 요구 대상에 의한 분류
  * 요구공학 프로세스
      * 요구 추출
          * 요구정보 출처
          * 고객의 발표
          * 문헌 양식 조사
          * 인터뷰
          * 설문
          * 브레인스토밍
          * 프로토타이핑
          * 문서분석
          * 심층워크샵
          * 집단창의력기법
          * 집단의사결정기법
          * 컨텍스트 다이어그램
      * 요구 분석
          * 요구 품질
          * 도메인 분석
          * 시나리오 기반 분석
      * 요구 명세
          * 작성 방법
          * 유스케이스
              * 유스케이스 다이어그램
              * 유스케이스 명세
              * 유스케이스 사이의 관계
      * 요구 검증
  * 요구사항 모델링
      * 모델링 기초
          * 관점과 추상화 수준
          * 소프트웨어와 모델링
          * 모델 사이의 관계
      * UML
          * UML 역사
          * UML 다이어그램
          * 모델링 과정
      * 정적 모델링
          * 객체지향 개념
          * 클래스 다이어그램
      * 동적 모델링
          * 시퀀스 다이어그램
          * 협동 다이어그램
          * 상태 다이어그램
      * 제어 모델링
      * 모델 검증
## 소프트웨어 설계: CASE 도구, UML과 같은 표준 형식 사용
  * 개요
  * 설계 원리
      * 설계 기본 개념
          * 서브시스템, 모듈
          * 설계 관점
          * 설계 작업 과정
      * 품질 목표
      * 전통적인 설계 원리
          * 추상화
          * 캡슐화
          * 모듈화
          * 결합
          * 응집
      * 객체지향 설계 원리(SOLID)
          * 인터페이스와 구현의 분리
          * 단일 책임의 원리
          * 개방 폐쇄의 원리
          * 리스코프 교체의 원리
          * 인터페이스 분리의 원리
          * 의존 관계 역전의 원리
      * 설계 메트릭
          * 전통적인 메트릭
          * 객체지향 메트릭
  * 아키텍처 설계
      * 아키텍처 기초
          * 아키텍처란?
          * 아키텍처의 역할
          * 아키텍처의 표현
      * 아키텍처 스타일
          * Client/Server
          * Layered
          * Event-Driven
          * MVC
          * MVP
          * MVVM
          * Pipe and Filter
          * Data-Centric
          * Data-Flow
          * Peer-to-Peer 스타일
      * 디자인 패턴
          * 디자인 패턴의 혜택
          * 디자인 패턴의 형식
          * 생성패턴
              * 추상팩토리 (Abstact Factory)
              * 빌더 (Builder)
              * 팩토리 메서드 (Factory Method)
              * 프로토타입 (Prototype)
              * 싱글톤 (Singleton)
          * 구조패턴
              * 어댑터 (Adaper)
              * 브릿지 (Bridge)
              * 복합 (Composite)
              * 데코레이터 (Decorator)
              * 퍼사드 (Facade)
              * 플라이웨이트 (Flyweight)
              * 프록시 (Proxy)
          * 행동패턴
              * 역할사슬 (Chain of Responsibility)
              * 커맨드 (Command)
              * 메멘토 (Memento)
              * 미디에이터 (Mediator)
              * 인터프리터 (Interpreter)
              * 이터레이터 (Iterator)
              * 전략 (Strategy)
              * 상태 (State)
              * 옵저버 (Observer)
              * 탬플릿 메소드 (Template method)
              * 비지터 (Visitor)
      * 아키텍처 평가
          * 개요
          * SAAM
          * ATAM
          * CBAM
          * ARID
  * 구조적 설계
  * 상세 설계
  * UI/UX 설계
      * UI/UX 설계원칙
      * UI 기본 개념
          * 사용성
          * 멘탈 모델
          * 피드백
          * 제약
      * UI 설계 원리
      * UI 설계 과정
          * 사용자 분석
          * 태스크 분석
          * UI 설계와 구현
          * 사용성 테스트
      * UI 요소
      * 화면 및 출력 설계
          * 화면 설계
          * 출력 설계
  * 설계 명세서와 결과의 확인
## 소프트웨어 개발: 프로그래밍 언어로 소프트웨어를 구축
  * 코딩 작업
      * 작업 과정
      * 자주 발생하는 오류
  * 코딩 표준
      * 명명 규칙
      * 형식
      * 문장과 수식
      * 오류처리
      * 주석
  * 설계에서 코드 생성
      * 연관의 코딩
      * 시퀀스 다이어그램의 코딩
  * 리팩토링
      * 리팩토링 개념
      * 리팩토링 과정
      * 코드 스멜
      * 리펙토링 사례
  * 코드 품질 향상 기법
      * FTR(Formal Technical Review)
          * 피어리뷰
          * 인스펙션
          * 워크스루
      * 정적 분석
      * 테스트 중심 개발
## 소프트웨어 테스트
  * 개요
      * 버그, 오류, 결함, 고장
      * 테스트 원리
      * 테스트 작업 과정
      * 테스트 케이스
  * 소프트웨어 테스트 원칙
  * 테스트 프로세스
  * 화이트박스 테스트(구조 테스트)
      * 논리 흐름의 표현
      * 검증 기준
  * 블랙박스 테스트(기능 테스트)
      * 동등 분할 기법
      * 경곗값 분석
      * 원인 결과 그래프
  * 단계별 테스트
      * 단위테스트
      * 통합 테스트
          * 빅뱅 통합
          * 하향식 통합
          * 상향식 통합
          * 연쇄식 통합
      * 시스템 테스트와 비기능성 테스트
          * 기능 테스트
          * 성능 테스트
          * 보안 테스트
          * UI 테스트
          * 인수 테스트
  * 테스트 자동화 도구와 테스트 문서화
## 소프트웨어 유지보수
  * 유지보수 개요
      * 변경의 이유와 유지보수 유형
      * Lehman의 법칙
  * 유지보수 작업 과정
      * 유지보수 작업
      * 유지보수 프로세스
      * 프로그램의 이해
      * 변경 파악과 분석
  * 3R
      * 역공학
          * 역공학 작업 순서
          * 역공학의 용도
          * 재문서화
          * 설계 복구
      * 재공학
          * 리엔지니어링 목적
          * 리엔지니어링 과정
      * 재사용
  * 소프트웨어 형상 관리
      * 베이스라인
      * 형상관리 절차
  * 소프트웨어 척도
## 소프트웨어 품질
  * 개요
      * 품질 개념
      * 소프트웨어 품질
  * 소프트웨어 품질의 분류
  * 소프트웨어 제품의 품질 표준
  * 프로세스 품질 표준
      * CMMi
      * ISO 9001
  * 소프트웨어 품질 보증
  * 품질 제어와 검토
      * 품질 모델
      * 품질 관리
          * 품질 보증 조직
          * 프로세스와 표준을 정의
          * 품질 보증 활동
          * 인스펙션
      * 품질 측정
          * 품질 측정의 유용성
          * 품질 메트릭
      * 프로세스 개선
  * 소프트웨어신뢰도
## 소프트웨어 형상 관리
  * 소프트웨어 시스템은 매우 복잡, 형상(버전과 소스 제어)이 표준화되고 구조적인 방법으로 관리 필요
  * 형상식별
  * 형상통제
  * 형상감사
 . * 형상기록
