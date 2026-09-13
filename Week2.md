# 📘 SQL_BASIC 2주차 정규 과제

SQL_BASIC 정규 과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고, 핵심 개념을 정리한 뒤 간단한 SQL 문제를 직접 풀어보는 방식으로 진행합니다.

이번 주는 저장된 데이터를 확인하는 방법과 `SELECT`, `FROM`, `WHERE`의 기본 구조를 학습합니다.

완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀 수행 인증란은 필수입니다.**

---

## 📚 SQL_BASIC_2nd_TIL

### 섹션 3. 데이터 탐색 - 조건, 추출, 요약

### 2-2. 저장된 데이터 확인하기(데이터베이스, 데이터 웨어하우스, ERD)

### 2-3. 데이터 탐색(SELECT, FROM, WHERE)

---

## ✨ 선택 강의

- 2-4. SELECT 연습 문제: SELECT, FROM, WHERE를 더 연습하고 싶을 때 선택 수강

---

## 🏁 전체 강의 수강 계획

| 주차 | 필수 강의 범위 | 선택 강의 | 완료 여부 |
| --- | --- | --- | --- |
| 1주차 | 1-1 ~ 2-1 | 1 | ✅ |
| 2주차 | 2-2 ~ 2-3 | 2-4 | ✅ |
| 3주차 | 2-5, 2-7 ~ 2-8 | 2-6 | 🍽️ |
| 4주차 | 3-2 ~ 4-3 | 3-4 | 🍽️ |
| 5주차 | 4-4 ~ 4-6 | 4-5, 4-7 | 🍽️ |
| 6주차 | 5-2 ~ 5-5 | 5-6 | 🍽️ |
| 7주차 | 필수 강의 없음 | 6-2, 6-3, 6-4, 6-5 | 🍽️ |

---

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념 정리

아래 키워드 중 중요하다고 생각한 개념을 2개 이상 골라 짧게 정리해주세요. 3개보다 더 많이 정리하고 싶다면 자유롭게 항목을 추가해도 좋습니다.

이번 주 키워드:
- SELECT
- FROM
- WHERE
- 조건식
- ORDER BY
- LIMIT
- 테이블 구조 확인

## 01.

```
개념 이름: SELECT
개념 설명:  테이블에 저장되어 있는 컬럼을 선택, 여러 컬럼 명시 가능, col1 AS "별칭"으로 컬럼의 이름도 별칭 지정 가능
예시 쿼리: SELECT  
 id AS pokemon_id
```

## 02.

```
개념 이름: FROM 
개념 설명: 데이터를 확인할 Table 명시
예시 쿼리: FROM `inflearn-bigquery-507707.basic.pokemon`
```

## (선택) 03.

```
개념 이름: WHERE
개념 설명: FROM에 명시된 Table에 저장된 데이터를 필터링
헷갈린 점: select, from, where 순서를 쿼리를 짤 때 생각하는게 어려웠다. 
```

---

# 2️⃣ 수행 인증란

아래 중 하나 이상을 첨부해주세요.

- 강의 수강 화면 캡처
  <img width="582" height="347" alt="인증" src="https://github.com/user-attachments/assets/1b5b99b5-5e15-4f1f-ba5c-cda7608d87b0" />

- 문제 풀이 정답 화면 캡처
  <img width="1871" height="750" alt="정답1" src="https://github.com/user-attachments/assets/2791e73f-142b-4d23-9d8a-91e8ad3d706c" />

- SQL 실행 결과 화면 캡처
<img width="1832" height="801" alt="실습" src="https://github.com/user-attachments/assets/15248de9-17a7-449c-9a85-bb2526130635" />

---

# 3️⃣ 확인 문제

프로그래머스는 로그인이 필요하므로, 로그인 후 문제 풀이를 진행해주세요.

## 🧩 문제 1

문제 링크: [모든 레코드 조회하기](https://school.programmers.co.kr/learn/courses/30/lessons/59034)

풀이 과정:

```
- 테이블에서 확인한 컬럼: ANIMAL_ID, ANIMAL_TYPE, DATETIME, INTAKE_CONDITION, NAME, SEX_UPON_INTAKE
- SELECT와 FROM을 작성한 방식: 모든 동물의 정보를 조회하라고 했으니 컬럼을 하나하나 나열할 필요 없이 SELECT *로 전체 컬럼을 가져왔다. FROM ANIMAL_INS로 대상 테이블을 지정했다.
- 새로 배운 점: ORDER_BY는 항상 쿼리 맨 마지막에 온다는 것을 알게 되었다. 정렬 기준을 따로 안정하면 기본이 오름차순이라는 것을 알게 되었다. 
```

<img width="1871" height="750" alt="정답1" src="https://github.com/user-attachments/assets/e9eae305-c68c-4922-94fa-ab99257b0ea1" />


## 🧩 문제 2

문제 링크: [아픈 동물 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/59036)

풀이 과정:

```
- 문제에서 요구한 조건: 동물 보호소에 들어온 동물 중 아픈 동물의 아이디와 이름을 조회하고 아이디 순으로 정렬해야 한다
- WHERE 절로 옮긴 방식: INTAKE_CONDITION = 'Sick' 조건을 사용해 아픈 동물만 조회한다.
- 정렬 기준이 있다면 사용한 기준: ANIMAL_ID를 기준으로 오름차순 정렬
- 새로 배운 점: WHERE를 사용하면 원하는 조건에 해당하는 행만 골라낼 수 있고, ORDER BY를 사용하면 특정 컬럼을 기준으로 결과를 정렬할 수 있다는 점을 배웠다.
```

<img width="1756" height="821" alt="정답2" src="https://github.com/user-attachments/assets/9d8e821c-3133-4402-81ae-0a4448fccedb" />


---

# 4️⃣ 이번 주 회고

```
1. SELECT, FROM, WHERE 중 가장 헷갈린 개념: WHERE가 가장 헷갈렸다. 어떤 조건을 넣어야 원하는 데이터만 조회할 수 있는지 구분하는 부분이 어려웠다.
2. 문제를 풀 때 가장 자주 확인하게 된 부분: 문제에서 어떤 컬럼을 출력해야 하는지와 어떤 조건에 해당하는 데이터만 골라야 하는지를 가장 자주 확인했다.
3. 다음 주 문제 풀이에서 의식하고 싶은 습관: 문제를 읽을 때 먼저 SELECT = 무엇을 / FROM = 어디서 / WHERE = 어떤 조건으로를 구분한 뒤 SQL문을 작성하는 습관을 들이고 싶다.
```

수고하셨습니다!




