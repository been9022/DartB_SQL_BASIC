# 📘 SQL_BASIC 4주차 정규 과제

SQL_BASIC 정규 과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고, 핵심 개념을 정리한 뒤 간단한 SQL 문제를 직접 풀어보는 방식으로 진행합니다.

이번 주는 SQL 쿼리를 작성하는 흐름, 쿼리 작성 템플릿, 데이터 타입 변환, 문자열 함수를 학습합니다.

완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀 수행 인증란은 필수입니다.**

---

## 📚 SQL_BASIC_4th_TIL

### 섹션 4. SQL 쿼리 잘 작성하기, 쿼리 작성 템플릿 및 오류를 잘 디버깅하기

### 3-2. SQL 쿼리를 작성하는 흐름

### 3-3. 쿼리 작성 템플릿과 생산성 도구

### 섹션 5. 데이터 탐색 - 변환

### 4-1. INTRO

### 4-2. 데이터 타입과 데이터 변환(CAST, SAFE_CAST)

### 4-3. 문자열 함수(CONCAT, SPLIT, REPLACE, TRIM, UPPER)

---

## ✨ 선택 강의

- 3-4. 오류를 디버깅하는 방법: 오류 메시지 해석과 디버깅 흐름을 더 익히고 싶을 때 선택 수강

---

## 🏁 전체 강의 수강 계획

| 주차 | 필수 강의 범위 | 선택 강의 | 완료 여부 |
| --- | --- | --- | --- |
| 1주차 | 1-1 ~ 2-1 | 1 | ✅ |
| 2주차 | 2-2 ~ 2-3 | 2-4 | ✅ |
| 3주차 | 2-5, 2-7 ~ 2-8 | 2-6 | ✅ |
| 4주차 | 3-2 ~ 4-3 | 3-4 | ✅ |
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
- 쿼리 작성 순서
- 쿼리 작성 템플릿
- 데이터 타입
- CAST
- SAFE_CAST
- CONCAT
- REPLACE
- TRIM

## 01.

```
개념 이름: 쿼리 작성 템플릿
개념 설명: 쿼리를 작성하기 전에 템플릿을 설정해두고 작성하는 것이 좋다. espanso를 활용하여 쿼리 작성 템플릿을 완성하였다. 
예시 쿼리: # 쿼리를 작성하는 목표, 확인할 지표
# 쿼리 계산 방법:
# 데이터의 기간
# 사용할 테이블
# Join KEY
# 데이터 특징

SELECT

FROM
WHERE


```

## 02.

```
개념 이름: CAST
개념 설명: 자료 타입을 변경하는 함수
예시 쿼리: CAST(1 AS STRING) # 숫자 1을 문자 1로 변경
```


# 2️⃣ 수행 인증란


<img width="475" height="710" alt="수강인증" src="https://github.com/user-attachments/assets/ca50044d-a3e0-4a22-b10e-2090a3af6087" />
<img width="1121" height="647" alt="SQL3" src="https://github.com/user-attachments/assets/89613f57-b1ce-4949-bd4c-59122b892ae9" />
<img width="935" height="636" alt="SQL2" src="https://github.com/user-attachments/assets/fdbf5b2b-b4bd-4ce2-95d1-60ddf484b01d" />
<img width="1252" height="615" alt="SQL1" src="https://github.com/user-attachments/assets/e996cf59-64b4-4dd3-8524-9bc955ff48b7" />


# 3️⃣ 확인 문제

프로그래머스는 로그인이 필요하므로, 로그인 후 문제 풀이를 진행해주세요.

## 🧩 문제 1

문제 링크: [특정 옵션이 포함된 자동차 리스트 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/157343)

풀이 과정:

```
- 찾으려는 문자열 조건:`OPTIONS`에 ‘네비게이션’이 포함되어 있을 것
- 사용한 문자열 조건 문법:`WHERE OPTIONS LIKE '%네비게이션%'` (`%`는 앞뒤에 다른 문자가 있어도 된다는 뜻)
- 정렬 기준:`ORDER BY CAR_ID DESC` — 자동차 ID 내림차순

```

<img width="1725" height="806" alt="정1" src="https://github.com/user-attachments/assets/c15882d2-2d64-42d1-9e24-8cd4674909d8" />


## 🧩 문제 2

문제 링크: [강원도에 위치한 생산공장 목록 출력하기](https://school.programmers.co.kr/learn/courses/30/lessons/131112)

풀이 과정:

```
- 문제에서 요구한 조건: 강원도에 위치한 식품공장을 조회한다
- WHERE 절로 옮긴 방식:' WHERE ADRESS LIKE '강원도%'로 '강원도'로 시작하는 공장만 선택한다.
- 정렬 기준: 'OREDER BY FACTORY_ID ASC'로 공장 ID를 오름차순 정렬한다. 
```

<img width="1786" height="752" alt="정2" src="https://github.com/user-attachments/assets/80b5f27d-9c39-4022-81aa-bf8a8cb6c72a" />

## 🧩 문제 3

문제 링크: [이름에 el이 들어가는 동물 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/59047)

풀이 과정:

```
- 찾으려는 문자열 패턴: 이름 어디에든 el이 들어가는 개
- 대소문자를 처리한 방식: LOWER(NAME)으로 이름을 소문자로 바꾼 뒤 '%el%'과 비교
- 정렬 기준: 이름 오름차순, 이름이 같으면 동물 ID 오름차순
```

<img width="1366" height="622" alt="정3" src="https://github.com/user-attachments/assets/f44af5fd-946b-4577-b981-eaa91f440bb4" />


## 🧩 문제 4

문제 링크: [카테고리 별 상품 개수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/131529)

풀이 과정:

```
- 추출한 문자열 범위: `PRODUCT_CODE`의 앞 2자리 (`LEFT(PRODUCT_CODE, 2)`)
- 그룹화 기준: 앞 2자리가 같은 상품끼리 묶음 (`GROUP BY LEFT(PRODUCT_CODE, 2)`)
- 정렬 기준: 카테고리 코드 오름차순 (`ORDER BY CATEGORY ASC`)

```

<img width="1702" height="696" alt="정4" src="https://github.com/user-attachments/assets/4c111cf3-5a3a-4e2b-bf5c-811a8c1f3c7d" />


---

# 4️⃣ 이번 주 회고

```

1. 쿼리 작성 흐름을 잡을 때 도움이 된 방법: 먼저 문제에서 *출력할 열 → 필터 조건 → 그룹화 → 정렬 기준*을 찾아 SQL의 `SELECT → WHERE → GROUP BY → ORDER BY`에 대응시켰다.
2. 타입 변환이나 문자열 처리에서 조심해야 할 점: 상품코드는 숫자가 아닌 문자열이므로 앞 2자리를 `LEFT(PRODUCT_CODE, 2)`로 추출한다. `LIKE`로 검색할 때는 ‘포함’이면 양쪽에 `%`, ‘시작’이면 뒤에만 `%`를 붙인다.
3. 앞으로 문제 풀이 때 먼저 확인할 것: 각 열의 자료형과 원하는 결과 열, 조건에 해당하는 열, 정렬 방향을 먼저 확인한다.

```

수고하셨습니다!




