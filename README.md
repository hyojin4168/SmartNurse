
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

```
View (JSP)
│
├─ Controller (Spring MVC)
│
├─ Service
│
├─ DAO (MyBatis)
│
└─ Oracle Database
```

## 🧑‍💻 담당 역할
- 개인 프로젝트 (Full Stack 개발)
- DB 및 ERD 설계
- Spring MVC 기반 CRUD 기능 구현
- Chart.js를 활용한 데이터 시각화
- UI/UX 설계 (Bootstrap)

---

## 💡 프로젝트 차별점

- 🩺 **간호학 전공 기반의 실무 이해도**  
  단순한 CRUD 구현을 넘어, 실제 병동 간호 기록 흐름(SOAP, PIE 등)을 분석하여  
  데이터 구조와 화면 설계를 임상 프로세스에 맞게 설계했습니다.

- 💾 **의료데이터 구조화 설계 경험**  
  환자 정보, Vital Sign, 간호기록을 분리·연결하는 ERD를 직접 설계하여  
  의료정보시스템(EMR) 구조를 체계적으로 반영했습니다.

- 🧩 **Spring MVC + MyBatis 기반의 안정적인 백엔드 구조**  
  Controller-Service-DAO 계층 분리를 통해 유지보수성과 확장성을 확보하였으며,  
  Oracle DB와의 연동을 통해 실제 병원 시스템과 유사한 데이터 처리 흐름을 구현했습니다.

- 📊 **Chart.js를 활용한 데이터 시각화**  
  환자의 Vital Sign 변화를 시각화하여, 의료 데이터의 가독성과 즉시성을 높였습니다.

- 🔐 **보안 및 권한 설계 적용**  
  간호사/관리자 권한을 분리하여 데이터 접근 제어를 구현함으로써,  
  의료정보 보안의 기본 원칙을 반영했습니다.

- ⚙️ **확장 가능한 의료 플랫폼 구조 설계**  
  향후 HL7 FHIR 표준 및 AI 분석 모듈(Python Flask) 연동을 고려한  
  유연한 시스템 아키텍처를 설계했습니다.
  
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
