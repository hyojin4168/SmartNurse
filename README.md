
# 🏥 SmartNurse - 병동 간호기록 관리 시스템

## 📘 프로젝트 개요
**SmartNurse**는 병동 간호사가 환자의 상태(Vital Sign)과 간호기록을  
효율적으로 관리할 수 있도록 설계된 **의료정보시스템형 웹 프로젝트**입니다.  
간호학 전공자의 임상 경험을 바탕으로 실제 간호기록 흐름과 병동 업무 프로세스를  
시스템화하여 효율적인 의료 데이터 관리와 접근성을 높이는 것을 목표로 합니다.

---

## 🧩 주요 기능
| 구분 | 기능명 | 설명 |
|------|---------|------|
| 1️⃣ | 로그인 / 권한 관리 | 간호사, 관리자 계정 구분 및 세션 관리 |
| 2️⃣ | 환자관리 | 환자 등록, 조회, 수정, 삭제 (CRUD) |
| 3️⃣ | Vital Sign 기록 | 체온, 혈압, 맥박 입력 및 그래프 시각화 (Chart.js) |
| 4️⃣ | 간호기록 관리 | SOAP형 간호기록 작성 및 키워드 검색 |
| 5️⃣ | 관리자 대시보드 | 통계 및 그래프 시각화, 근무자별 기록 현황 |

---

## ⚙️ 개발 환경
- **Language:** Java (JDK 11)
- **Framework:** Spring MVC, MyBatis  
- **Database:** Oracle XE  
- **Frontend:** JSP, JSTL, Bootstrap, Chart.js  
- **Server:** Apache Tomcat 9  
- **Tools:** STS3, SQL Developer, ERDCloud, GitHub  

---

## 🗂️ 데이터베이스 설계

### 📘 ERD 구조

[ NURSE ]
nurse_id (PK)
name
department
position
password

    │ 1:N
    ▼
[ NURSING_RECORD ]
record_id (PK)
patient_id (FK)
nurse_id (FK)
record_date
category
content

    ▲
    │ N:1
    │
[ PATIENT ]
patient_id (PK)
name
birth
gender
ward
admission_date

markdown
코드 복사
    │ 1:N
    ▼
[ VITAL_SIGN ]
vs_id (PK)
patient_id (FK)
record_date
temperature
blood_pressure
pulse

📌 **핵심 관계 요약**
- 한 명의 **간호사(NURSE)** 는 여러 간호기록을 작성할 수 있음 (1:N)  
- 한 명의 **환자(PATIENT)** 는 여러 Vital Sign과 간호기록을 가짐 (1:N)  
- **NURSING_RECORD** 와 **VITAL_SIGN** 은 `patient_id` 로 환자 테이블과 연결됨  

---

## 📈 시스템 구조

[ View (JSP) ]
↓
[ Controller (Spring MVC) ]
↓
[ Service ]
↓
[ DAO (MyBatis) ]
↓
[ Oracle Database ]

## 🧑‍💻 담당 역할
- 개인 프로젝트 (Full Stack 개발)
- DB 및 ERD 설계
- Spring MVC 기반 CRUD 기능 구현
- Chart.js를 활용한 데이터 시각화
- UI/UX 설계 (Bootstrap)

---

## 💡 프로젝트 차별점
- 간호학 전공자의 임상 프로세스 이해 기반 설계  
- 실제 간호기록 양식(SOAP, PIE) 반영  
- 환자 중심의 직관적 UI 구성  
- 의료정보시스템(EMR) 실무 구조 반영  

---

## 🚀 향후 발전 방향
- HL7 FHIR 기반 데이터 구조로 확장  
- JWT 기반 인증 시스템 도입  
- Python Flask 기반 이상징후 탐지 AI 모듈 연동  

---

## 📚 버전 이력
| 버전 | 날짜 | 내용 |
|-------|--------|-------|
| v0.1 | 2025-11 | 프로젝트 기획 및 초기 설계 |
| v0.2 | 예정 | DB 설계 및 CRUD 구현 예정 |

---

## 📎 GitHub Repository
> 🔗 [SmartNurse Repository](#)  
(※ 코드 업로드 후 링크 추가 예정)
