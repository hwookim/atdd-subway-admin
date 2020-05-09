# 지하철 정보 관리

## 1단계 - 노선 / 인수 테스트

 - [x] 시나리오에 따른 인수 테스트 / 프로덕션 코드 작성
```
  Scenario: 지하철 노선을 관리한다.
    When 지하철 노선 n개 추가 요청을 한다.
    Then 지하철 노선이 추가 되었다.
    
    When 지하철 노선 목록 조회 요청을 한다.
    Then 지하철 노선 목록을 응답 받는다.
    And 지하철 노선 목록은 n개이다.
    
    When 지하철 노선 수정 요청을 한다.
    Then 지하철 노선이 수정 되었다.

    When 지하철 노선 제거 요청을 한다.
    Then 지하철 노선이 제거 되었다.
    
    When 지하철 노선 목록 조회 요청을 한다.
    Then 지하철 노선 목록을 응답 받는다.
    And 지하철 노선 목록은 n-1개이다.
```

## 2단계 - 노선 / 페이지 연동

 - [x] 지하철 노선 관리 CRUD 작성
    - [x] 노선 추가
    - [x] 노선 조회
        - [x] 노선 클릭 시 상세정보 출력
        - [x] 수정 팝업 시 기존 정보 출력
    - [x] 노선 수정
        - [x] 수정 후 수정된 정보 출력
    - [x] 노선 삭제

## 3단계 - 노선별 지하철역 / 인수테스트

 - [x] 시나리오에 따른 인수테스트 작성
    - [x] mock서버를 통한 테스트 진행
 
 ```
 Scenario: 지하철 노선에 역을 추가하고 제거한다.
        Given 지하철역이 여러 개 추가되어있다.
        And 지하철 노선이 추가되어있다.
   
        When 지하철 노선에 지하철역을 등록하는 요청을 한다.
        Then 지하철역이 노선에 추가 되었다.
   
        When 지하철 노선의 지하철역 목록 조회 요청을 한다.
        Then 지하철역 목록을 응답 받는다.
        And 새로 추가한 지하철역을 목록에서 찾는다.
   
        When 지하철 노선에 포함된 특정 지하철역을 제외하는 요청을 한다.
        Then 지하철역이 노선에서 제거 되었다.
   
        When 지하철 노선의 지하철역 목록 조회 요청을 한다.
        Then 지하철역 목록을 응답 받는다.
        And 제외한 지하철역이 목록에 존재하지 않는다.
 ```