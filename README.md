# 📅 일정 관리 CLI 프로그램

이 프로젝트는 Python과 MySQL을 이용한 간단한 **일정 관리 커맨드라인 인터페이스(CLI)** 프로그램입니다.  
사용자는 일정 추가, 조회, 완료 처리 기능을 수행할 수 있습니다.

---

## ✅ 기능

1. **일정 추가**  
   사용자로부터 일정 제목, 설명, 시작일, 종료일을 입력받아 DB에 저장합니다.

2. **일정 조회**  
   DB에 저장된 모든 일정을 출력합니다.

3. **일정 완료 처리**  
   특정 일정의 완료 여부(`is_completed`)를 `True`로 업데이트합니다.

4. **종료**  
   프로그램을 종료합니다.

---

## 🧱 데이터베이스 구조

- **데이터베이스 이름**: `schedule_db`
- **테이블 이름**: `schedules`

```sql
CREATE TABLE IF NOT EXISTS schedules (
    id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(200) NOT NULL,
    description TEXT,
    start_datetime DATETIME NOT NULL,
    end_datetime DATETIME,
    is_completed BOOLEAN DEFAULT FALSE
);
