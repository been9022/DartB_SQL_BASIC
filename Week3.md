# 📘 SQL_BASIC 3주차 정규 과제

SQL_BASIC 정규 과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고, 핵심 개념을 정리한 뒤 간단한 SQL 문제를 직접 풀어보는 방식으로 진행합니다.

이번 주는 집계 함수와 `GROUP BY`, `HAVING`을 학습합니다.

완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀 수행 인증란은 필수입니다.**

---

## 📚 SQL_BASIC_3rd_TIL

### 섹션 3. 데이터 탐색 - 조건, 추출, 요약

### 2-5. 집계(GROUP BY + HAVING + SUM/COUNT)

### 2-7. 정리

### 2-8. 새로운 집계 함수 소개(GROUP BY ALL, 2024-02-26에 나온 함수)

---

## ✨ 선택 강의

- 2-6. 연습 문제: 집계와 조건 조회를 더 연습하고 싶을 때 선택 수강

---

## 🏁 전체 강의 수강 계획

| 주차 | 필수 강의 범위 | 선택 강의 | 완료 여부 |
| --- | --- | --- | --- |
| 1주차 | 1-1 ~ 2-1 | 1 | ✅ |
| 2주차 | 2-2 ~ 2-3 | 2-4 | ✅ |
| 3주차 | 2-5, 2-7 ~ 2-8 | 2-6 | ✅ |
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
- COUNT
- SUM
- AVG
- MAX
- MIN
- GROUP BY
- HAVING
- 집계 기준

## 01.

```
개념 이름: GROUP BY
개념 설명: 그룹화 한 값에 조건 설정하기
예시 쿼리:
SELECT
 type1,
 COUNT(id) AS cnt
FROM basic.pokemon
GROUP BY
 type1
```

## 02.

```
개념 이름: HAVING
개념 설명: GROUP BY한 후 조건을 설정하고 싶은 경우
예시 쿼리:
SELECT
 type1,
 COUNT(id) AS cnt
FROM basic.pokemon
GROUP BY
 type1
HAVING cnt >= 10
ORDER BY cnt DESC
```



---

# 2️⃣ 수행 인증란

아래 중 하나 이상을 첨부해주세요.

- 강의 수강 화면 캡처
- 문제 풀이 정답 화면 캡처
- SQL 실행 결과 화면 캡처

  <img width="1245" height="877" alt="결3" src="https://github.com/user-attachments/assets/521aa862-e411-457a-97b1-a7cc8d870215" />
<img width="907" height="521" alt="강의수강인증" src="https://github.com/user-attachments/assets/bc260dbe-0b9a-4c12-8abc-88bd0303d8e0" />


---

# 3️⃣ 확인 문제

프로그래머스는 로그인이 필요하므로, 로그인 후 문제 풀이를 진행해주세요.

## 🧩 문제 1

문제 링크: [최댓값 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/59415)

풀이 과정:

```
- 문제 요구사항: 동물 보호소에 가장 최근에 들어온 동물의 보호 시작 시간을 조회한다.
- 사용한 SQL 절: SELECT, FROM, MAX(), AS
- 새로 배운 점: 날짜 데이터에도 MAX()함수를 사용할 수 있으며, 가장 큰 날짜 값이 가장 최근 시간을 의미한다.
```

<img width="1456" height="626" alt="1번문제" src="https://github.com/user-attachments/assets/d899d2ce-cd1e-4249-ba38-06e7713b20bc" />


## 🧩 문제 2

문제 링크: [가장 비싼 상품 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/131697)

풀이 과정:

```
- 사용한 집계 함수: MAX()
- 집계 대상 컬럼: PRICE
- 결과를 검증한 방법: 예시의 판매가인 10,000원, 9,000원, 22,000원을 비교하여 가장 큰 값인 22,000원이 출력되는지 확인했다. 
```

<img width="1635" height="572" alt="2번문제" src="https://github.com/user-attachments/assets/e3799334-7f47-4af5-8e10-b2972c170523" />


## 🧩 문제 3

문제 링크: [고양이와 개는 몇 마리 있을까](https://school.programmers.co.kr/learn/courses/30/lessons/59040)

풀이 과정:

```
- 그룹화 기준: ANIMAL_TYPE
- WHERE와 HAVING 중 사용한 절: WHERE
- 처음 틀렸다면 틀린 이유:  처음에는 WHERE 조건을 넣지 않아 고양이와 개 외의 동물까지 집계될 가능성이 있었다
- 새로 배운 SQL 패턴: WHERE로 필요한 행을 먼저 선택한 뒤, GROUP BY와 COUNT()로 종류별 개수를 구하는 패턴
```

<!-- 정답을 맞추게 되면, 정답입니다. 이 부분을 캡처해서 이 주석을 지우시고 첨부해주시면 됩니다. -->

---

# 4️⃣ 이번 주 회고

```
1. 문제를 SQL로 옮길 때 가장 어려웠던 부분: 동물의 종류별 개수를 구하기 위해 GROUP BY와 COUNT()를 함께 사용해야 한다는 점이 어려웠다.
2. WHERE와 HAVING의 차이를 어떻게 이해했는지: WHERE는 그룹화하기 전의 개별 데이터를 조건으로 걸러내고, HAVING은 그룹화한 후의 집계 결과에 조건을 적용한다고 이해했다.
3. 다음 주에 더 연습하고 싶은 문제 유형: GROUP BY, COUNT(), WHERE, HAVING을 함께 활용해 조건별 개수를 구하는 문제를 더 연습하고 싶다. 
```

수고하셨습니다!




