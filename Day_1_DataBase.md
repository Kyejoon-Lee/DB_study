



# DataBase

## 1. DB의 등장

- 여러 가지 언어로 만들어진 Data들은 만들어진 언어로만 modify가 가능하였다.
- Modify 과정 중 정보의 누락 및 변경의 어려움이 존재
- 모든 곳에서 access가능하며 일괄적으로 관리가 가능한 언어가 필요
- 모든 것을 OS가 관리하기 때문에 과부하가 많이 걸림



## 2. DB의 특징

- Redundant 의 문제를 해결
- 동시 다발적인 접근이 가능
- Query 가 단순하고 정형화 되어있다.
- DB = Schema + Instance
- Schema 는 저장될 데이터의 설계도(Usually not modify)

- Instance 저장되는 데이터(Easy to modify)

  ### 2-1. 3 Schema Architecture

  - External Schema :  user가 볼 수 있는 외부의 구조 like View
  - Conceptual Schema :  보통적으로 가변 할 수 없는 데이터의 기본 구조
  - Physical Schema : 실제 데이터가 물리적으로 저장되는 구조
  - Logical independence : Conceptual Schema 가 변경 될 경우 External Schema는 영향을 받지 않는다.
  - Physical independence : Physical Schema 가 변경 될 경우 Conceptual Schema는 영향을 받지 않는다.

  ​																											![1559177245385](C:\Users\student\AppData\Roaming\Typora\typora-user-images\1559177245385.png)

  

## 3. DB Language

- DML 
  - 검색 : SELECT
  - 추가 : INSERT
  - 수정 : UPDATE
  - 삭제 : DELETE
  - ex : SELECT FROM WHERE , INSERT FROM ~

- DDL
  - 생성 : CREATE
  - 변경 : ALTER
  - 삭제 : DROP
  - *TABLE의 관리 변경 : TRUNCATE

- DCL 
  - DBMS의 보안 : 1. 인증 , 2. 권한

- TCL 
  - Transaction 하는 동안 recovery 하기 위해 원자성을 가지고 있다
  - 각 과정에 대한 log(영속성)이 존재한다
  - 위의 log에 대해 commit 및 rollback이 가능



## 4. ER Modeling

- ER modeling 은 conceptual schema에 대한 디자인을 하는것이다.

  ### 4.1 Entity 

  - 세상에 지칭 할 수 있는 모든것을 의미한다

  - Attribute :  Entity의 특성들을 의미한다.

    #### 4.1.1 Attribute의 종류

    - Simple : 단 하나의 value를 가지는 경우
    - Composite : 다른 attribute로 부터 구성된 경우
    - Multi-value : 단 하나가 아니 여러 값을 가지고 있는 경우
    - Complex : composite + multi-value
    - Derived : 다른 attribute로 부터 계산되어진 값
    - NULL : 값이 존재하지 않는 경우

    ![1559193580761](C:\Users\student\AppData\Roaming\Typora\typora-user-images\1559193580761.png)

  - Key :  Attribute 중 Entity를 유일하게 증명 할 수 있는 요소

    ​		 모든 Entity는 다른 Key값을 갖는다, NULL값을 가질 수 없다(개체 무결성)

    #### 4.1.2 Key의 종류

    - Candidate : Attribute의 유일하게 식별할 수 있는 속성들을 의미한다
      					 (다수의 경우가 될 수도 있다)
    - Primary :  Candidate 중 선택 한 속성
    - Alternate : Primary key 를 제외한 나머지 Candidate key
    - Super :  key들의 집합으로 이루어진 그룹형 key 
    - Foreign : Relation 을 맺고 있는 Entity에서 참조한 key

  ### 4.2 Relationship

  - 많은 Entity 들과 연결 관계를 표시
  - 1: 1, 1:N, N:M 의 연결을 맺는 관계형이 존재 
  - 쉽게 생각해 각 Entity의 primary 값을 추출 후 하나의 관계로 합친 table과 같다
  - 이미 하나의 relation이 존재하는 두가지 Entity 가 또 다른 relation을 가질 수 있다 

  ![1559193627149](C:\Users\student\AppData\Roaming\Typora\typora-user-images\1559193627149.png){width=50%}

  

  

  

  