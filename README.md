# SQLD
1. 엔터티를 도출하고 그린다.
2. 엔터티를 배치한다. (중요한 엔터티를 왼쪽 상단에 배치한다.)
3. 엔터티 간의 관계를 설정한다.
4. 관계명을 서술한다. (계좌를 개설한다. 주문을 발주한다. 종목을 선택한다.)
5. 관계 참여도를 표현한다. (관계 참여도는 한 개의 엔터티와 다른 엔터티 간의 참여하는 관계 수를 의미한다. 즉, "고객이 여러 개의 계좌를 개설할 수 있다"와 같은 의미를 표현하는 것이다.) 
## 중요한 엔터티를 가급적 왼쪽 상단에 배치한다.
## ERD는 이해가 쉬워야 하고 너무 복잡하지 않아야 한다.

## 데이터 모델링 고려사항
* 독립성이 확보된 모델은 고객의 업무 변화에 능동적으로 대응할 수 있다.
* 독립성을 확보하기 위해서는 중복된 데이터를 제거해야 한다.
* 데이터 중복을 제거하는 방법이 바로 정규화이다.
* 고객의 요구사항을 간결하고 명확하게 표현해야 한다.

# 3층 스키마
* 사용자, 설계자, 개발자가 데이터베이스를 보는 관점에 따라 데이터 베이스를 기술하고 이들 간의 관계를 정의한 ANSI 표준이다.
* 3층 스키마는 데이터 독립성을 확보하기 위한 방법이다.
* 3단계 계층으로 분리해서 독립성을 확보하는 방법으로 각 계층을 View라고 한다.

### 논리적 독립성 : 개념 스키마가 변경되더라도 외부 스키마가 영향을 받지 않는 것이다.
### 물리적 독립성 : 내부 스키마가 변경되더라도 개념 스키마가 영향을 받지 않는 것이다.

### 외부 스키마
 * 사용자 관점, 업무상 관련이 있는 데이터 접근이다.
 * 관련 데이터베이스의 View를 표시한다.
 * **응용 프로그램이 접근하는 데이터 베이스**를 정의한다.
### 개념 스키마
 * 설계자 관점, 사용자 전체 집단의 데이터베이스 구조이다.
 * 전체 데이터베이스 내의 규칙과 구조를 표현한다.
 * **통합 데이터베이스 구조이다.**
### 내부 스키마
 * 개발자 관점, 데이터 베이스의 **물리적 저장 구조**이다.
 * 데이터 저장 구조, 레코드 구조, 필드 정의, 인덱스 등을 의미한다.

# 엔터티
 * 엔터티는 업무에서 관리해야 하는 데이터 집합을 의미하며, 저장하고 관리되어야 하는 데이터이다.
 * 엔터티는 개념, 사건, 장소 등의 명사이다.
 * 엔터티는 변별할 수 있는 사물이다.
 * 정보를 저장할 수 있는 어떤 것이다.
 * 데이터베이스 내부에서 변별 가능한 객체이다.
 * 정보가 저장될 수 있는 장소, 사람, 사건, 개념, 물건 등이다.

## 비즈니스 프로세스 예시
  1. 고객이 회원가입을 한다. 회원으로 가입할 때는 회원ID, 패스워드, 이름, 주소, 전화번호 등을 입력해야 한다.
  2. 회원으로 가입하기 위해서는 반드시 하나의 계좌를 개설해야 한다.
  3. 고객은 계좌를 여러 개 개설할 수 있다.
  4. 계좌를 개설할 때는 계좌번호, 계좌명, 예수금, 계좌개설 지점, 계좌담당자가 입력된다.

## 엔터티의 특징
  ### 식별자
    - 엔터티는 유일한 식별자가 있어야 한다.
  ### 인스턴스 집합
    - **2개 이상의 인스턴스**가 있어야 한다.
    - 즉, 고객정보는 2명 이상 있어야 한다.
  ### 속성
    - 엔터티는 반드시 속성을 가지고 있다.
  ### 관계
    - 엔터티는 다른 엔터티와 최소한 한 개 이상 관계가 있어야 한다.
    - ex) 고객은 계좌를 개설한다.
  ### 업무
    - 엔터티는 업무에서 관리되어야 하는 집합이다.
  
  ### 릴레이션과 테이블, 인스턴스
    - 릴레이션과 테이블은 같은 의미라고 해석하면 된다. 릴레이션에 기본키 및 제약조건을 설정하면 테이블이 된다.
    - 단 Relationship은 릴레이션 간의 관계를 의미한다.
    - 인스턴스는 릴레이션이 가질 수 있는 값을 의미한다. 간단하게 생각하면 행의 수를 의미한다.
  
  # 엔터티 종류
    * 엔터티의 종류는 유형과 무형에 따른 종류, 엔터티가 발생하는 시점에 따른 종류로 나누어진다.
    * 엔터티를 유형과 무형으로 분류하는 기준은 물리적 형태의 존재 여부이다.
  
  ## 유형과 무형에 따른 엔터티 종류
  
  ### 유형 엔터티
    - 업무에서 도출되며 지속적으로 사용되는 엔터티이다.
    - 고객, 강사, 사원 등
  
  ### 개념 엔터티
    - 유형 엔터티는 물리적 형태가 있지만, 개념 엔터티는 물리적 형태가 없다.
    - 개념적으로 사용되는 엔터티이다.
    - 거래소 종목, 코스닥 종목, 생명보험 상품
  
  ### 사건 엔터티
    - 비즈니스 프로세스를 실행하면서 생성되는 엔터티이다.
    - ex) 주문, 체결, 취소주문, 수수료 청구 등
  
  ## 발생 시점에 따른 엔터티 종류
  
  ### 기본 엔터티
    - 키 엔터티라고도 한다.
    - 다른 엔터티로부터 영향을 받지 않고 **독립적으로 생성되는 엔터티이다.**
    - 고객, 상품, 부서 등 (내 프로젝트의 경우 고객, 음식)
  ### 중심 엔터티
    - 기본 엔터티와 행위 엔터티 간의 중간에 있는 것이다.
    - 즉, 기본 엔터티로부터 발생되고 행위 엔터티를 생성하는 것이다.
    - ex ) 계좌, 주문, 취소, 체결 등 (내 프로젝트의 경우 레시피, 다이어리)
  ### 행위 엔터티
    - 2개 이상의 엔터티로부터 발생된다.
    - 주문 이력, 체결 이력 등 (내 프로젝트의 경우, Challenge - User와 Recipe, Diary에서 영향)
  
  # 속성(Attribute)
  * 속성이라는 것은 업무에서 필요한 정보인 엔터티가 가지는 항목이다.
  * 속성은 더 이상 분리되지 않는 단위로, 업무에 필요한 데이터를 저장할 수 있다.
  * 인스턴스의 구성요소이고 의미적으로 더 이상 분해되지 않는다.
  
  # 속성의 특징과 종류
  ## 속성의 특징
  * 속성은 업무에서 관리되는 정보이다.
  * 속성은 하나의 값만 가진다.
  * 주식별자에게 함수적으로 종속된다. 즉, 기본키가 변경되면 속성의 값도 변경된다는 것이다.
  
  ## 속성의 종류
  ## 분해 여부에 따른 속성의 종류
  ### 단일 속성
    - 하나의 의미로 구성된 것으로 회원ID, 이름 등이다.
  ### 복합 속성
    - 여러 개의 의미가 있는 것으로 대표적으로 주소가 있다.
    - 주소는 시, 군, 동 등으로 분해될 수 있다.
  ### 다중값 속성
    - 속성에 여러 개의 값을 가질 수 있는 것으로 예를 들어 상품 리스트가 있다.
    - 다중값 속성은 엔터티로 분해된다.
    (나의 경우, challenge_list, food_list, diary_list)
    
  ## 특성에 따른 속성의 종류
  ### 기본 속성
    - 비즈니스 프로세스에서 도출되는 **본래의 속성**이다.
    - 회원ID, 이름, 계좌번호, 주문 일자 등 (user_email, food_name, food_protein)
  ### 설계 속성
    - 데이터 모델링 과정에서 발생되는 속성이다.
    - 유일한 값을 부여한다.
    - 상품코드, 지점코드 등 (challenge_id, diary_id )
  ### 파생 속성
    - 다른 속성에 의해서 만들어지는 속성이다.
    - 합계, 평균 등
  
  # 관계(Relationship)
  * 관계는 엔터티 간의 관련성을 의미하며 존재 관계와 행위 관계로 분류된다.
  * 존재 관계는 두 개의 엔터티가 존재 여부의 관계가 있는 것이고, 행위 관계는 두 개의 엔터티가 어떤 행위에 의한 관련성이 있는 것이다.

  ## 관계의 종류
  ### 존재 관계
  * 존재 관계는 엔터티 간의 상태를 의미한다. 예를 들어 고객이 은행에 회원가입을 하면, 관리점이 할당되고, 그 할당된 관리점에서 고객을 관리한다.
  ### 행위 관계
  * 행위 관계는 엔터티 간에 어떤 행위가 있는 것으로, 계좌를 사용해서 주문을 발주하는 관계가 만들어진다.
  * 예를 들어 증권회사는 계좌를 개설하고 주문을 발주하는 것이다.

  ## 관계 차수(Cardinality)
  ### 관계 차수
    * 관계 차수는 두 개의 엔터티 간에 관계에 참여하는 수를 의미한다.
    * 예를 들어 한 명의 고객은 여러 개의 계좌를 개설할 수 있다. 이러한 경우는 1대 N 관계가 된다.
  ### M대 N 관계
    * M대 N 관계는 두 개 엔터티가 서로 여러 개의 관계를 가지고 있는 것이다.
    * 예를 들어 한 명의 학생이 여러 과목을 수강할 수 있다. 반대로 한 개의 과목은 여러 명의 학생이 수강한다. 그래서 M대N관계가 발생한다.
    * 관계형 데이터베이스에서 M대 N 관게의 Join은 카테시안 곱이 발생한다. 그래서 M대 N 관계를 1 대 N, N대1로 해소해야 한다.
  ### 필수적 관계와 선택적 관계
    * 필수적 관계는 반드시 하나는 존재해야 하는 관계이고 선택적 관계는 없을 수도 있는 관계이다.
    * 필수적 관계는 "|"로 표현되고, 선택적 관계는 "O"로 표현된다.
    
  ## 식별 관계와 비식별 관계
  ### 식별 관계
    * 고객과 계좌 엔터티에서 고객은 독립적으로 존재할 수 있는 강한 개체이다.
    * 강한 개체는 어떤 다른 엔터티에게 의존하지 않고 독립적으로 존재한다.
    * 강한 개체는 다른 엔터티와 관계를 가질 때 다른 엔터티에게 기본키를 공유한다.
    * 강한 개체는 식별 관계로 표현된다.
    * 즉, 식별 관계란 고객 엔터티의 기본 키인 회원ID를 계좌 엔터티의 기본키의 하나로 공유하는 것이다.
    * 강한 개체의 기본키 값이 변경되면 식별 관계에 있는 엔터티의 값도 변경된다.
    * 여기서 계좌 엔터티는 약한 개체가 된다.
  ### 비식별 관계
    * 비식별 관계는 강한 개체의 기본키를 다른 엔터티의 기본키가 아닌 일반 칼럼으로 관계를 가지는 것이다.
    * 예를 들어 관리점 엔터티의 기본키는 지점 코드이고 고객 엔터티와 비식별 관계를 가지고 있다. 즉, 지점 코드는 고객 엔터티의 기본키가 아닌 일반 칼럼으로 참조된다.
      (Foreign Key를 Primary Key로 사용하는 엔터티 vs Foreign Key를 그냥 속성으로 사용하는 엔터티) 
      
  # 엔터티 식별자(Entity Identifier)
    식별자라는 것은 엔터티를 대표할 수 있는 유일성을 만족하는 속성이다. 
    일반적으로 회원ID, 계좌번호, 주민등록번호, 외국인등록번호, 여권번호 등이 있다.
  ## 주식별자(기본키, Primary Key)
    * 최소성 : 주식별자는 최소성을 만족하는 키이다.
    * 대표성 : 주식별자는 엔터티를 대표할 수 있어야 한다.
    * 유일성 : 주식별자는 엔터티의 인스턴스를 유일하게 식별한다.
    * 불변성 : 주식별자는 자주 변경되지 않아야 한다.
    
  ## 키의 종류
  ### 기본 키
    * 후보 키 중에서 엔터티를 대표할 수 있는 키이다.
  ### 후보 키
    * 후보키는 유일성과 최소성을 만족하는 키이다.
  ### 슈퍼 키
    * 슈퍼키는 유일성은 만족하지만 최소성을 만족하지 않는 키이다.
  ### 대체 키
    * 대체키는 여러 개의 후보키 중에서 기본키를 선정하고 남은 키이다.
  ### 외래 키
    * 하나 혹은 다수의 다른 테이블의 기본 키 필드를 가리키는 것으로 참조 무결성을 확인하기 위해서 사용되는 키이다.
    * 즉, 허용된 데이터 값만 데이터베이스에 저장하기 위해서 사용된다.
  
  ## 식별자의 종류
    * 식별자는 대표성, 생성 여부, 속성의 수, 대체 여부로 분류된다.
  ### 1.식별자의 대표성
    * 주식별자는 엔터티를 대표할 수 있는 식별자이다. 예를 들어 회원 ID는 고객 엔터티에 주식별자가 된다.
  #### 주식별자
    * 유일성과 최소성을 만족하면서 엔터티를 대표하는 식별자이다.
    * 다른 엔터티와 참조 관계로 연결될 수 있다.
  #### 보조 식별자
    * 유일성과 최소성은 만족하지만 대표성을 만족하지 못하는 식벌자이다.
  ### 2.생성 여부
  #### 내부 식별자
    * 내부 식별자는 엔터티 내부에서 스스로 생성되는 식별자이다.
    * 부서코드, 주문번호, 종목 코드 등
  #### 외부 식별자
    * 다른 엔터티와의 관계로 인하여 만들어지는 식별자이다.
    * 계좌 엔터티의 회원 ID
  ### 3.속성의 수
  #### 단일 식별자
    - 하나의 속성으로 구성된다.
    - 고객 엔터티의 회원 ID
  #### 복합 식별자
    - 두 개 이상의 속성으로 구성된다.
  ### 4.대체 여부
  #### 본질 식별자
    - 비즈니스 프로세스에서 만들어지는 식별자이다.
  #### 인조 식별자
    - 인위적으로 만들어지는 식별자이다.
    - 후보 식별자 중에서 주식별자로 선정할 것이 없거나 주식별자가 너무 많은 칼럼으로 되어 있는 경우에 사용한다.
    - 즉 순서번호(Sequence Number)를 이용해서 식별자를 만드는 것이다.
    
