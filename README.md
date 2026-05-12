# Pictures 
<img width="988" height="622" alt="Addslashes" src="https://github.com/user-attachments/assets/35990b66-310a-476e-8fed-46965ab0bc91" />

- 입력값을 addslashes 함수 처리하여 주석처리를 이용한 injection 이 통하지 않는 모습
<img width="914" height="653" alt="prepared_statement" src="https://github.com/user-attachments/assets/ac04d06a-56c1-43eb-ab37-e47b2546deba" />

-prepared_statement 를 적용해 입력값을 쿼리부분과 명확히 구분하는 상태로 보완
<img width="988" height="694" alt="html_entity" src="https://github.com/user-attachments/assets/f3da06df-64a8-4d35-a611-5ff26ab87130" />

-htmlentities 사용하여 자바스크립트를 형태의 공격을 문자열 처리로 무효화








# Web Security Practice

Ubuntu 기반 Apache/PHP/MySQL 환경에서  
웹 취약점(SQL Injection, XSS)을 직접 실습하고  
기본적인 방어 방법을 적용해본 프로젝트입니다.
학습 과정에서 "누구나 쉽게 따라 하며 배우는 웹 해킹 첫걸음"(권현준 저)을 참고했습니다.

---

## Project Overview

웹 보안을 단순 이론으로만 공부하지 않고,  
직접 웹 환경을 구축하고 취약점을 테스트해보며  
동작 원리를 이해하기 위해 진행한 프로젝트입니다.

## What I learned

- Ubuntu Linux 환경 구축
- Apache + PHP + MySQL 연동
-  MySQL을 이용한 기본적인 데이터베이스 구성 및 조회 실습
- 웹 브라우저와 서버 간 요청/응답 방식 이해
- 로그인 및 검색 기능 구현
- SQL Injection 실습
- Prepared Statement를 이용한 SQL Injection 방어
- XSS 발생 기본 원리 분석
- htmlentities()를 이용한 기본적인 XSS 방어

---

## Environment

- Ubuntu Linux
- Apache2
- PHP
- MySQL
- VMware

---

## Project Structure

```text
login.html
login.php
login_safe.php
search.html
search.php
```

---


### 1. Login Function (`login.php`)

- ID/PW 입력 기능 구현
- SQL 쿼리 동작 방식 학습
- SQL Injection 취약점 실습
- addslashes()를 이용한 기본 입력 처리 실습


### 2. SQL Injection Defense (`login_safe.php`)

- Prepared Statement 적용
- 사용자 입력과 SQL 쿼리를 분리하여 처리
- SQL Injection 방어 방식 학습

사용 함수:

- `mysqli_prepare()`
- `mysqli_stmt_bind_param()`
- `mysqli_stmt_execute()`

---

### 3. Search Function (`search.php`)

- 검색 기능 구현
- 검색어 출력 기능 구현
- htmlentities()를 이용한 기본적인 XSS 방어 실습

Example:

- `echo htmlentities($query);`

### upgrade plan

- 사용자의 비밀번호를 직접 서버에 저장하는 대신 암호 해시 함수를 적용하여 보안성을 강화해보고 싶습니다.
- SQL Injection 실습 과정에서 사용되는 문자열 함수(length, substring 등)의  입력값 분석 자동화 방식에 대해 추가적으로 학습해보고 싶습니다.

## Notes

본 프로젝트는 학습 목적의 로컬 환경 실습 프로젝트입니다.  
실제 서비스 공격 목적이 아닌 웹 보안 원리 이해를 목표로 진행하였습니다.


