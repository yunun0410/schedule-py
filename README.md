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
⚙️ 설치 및 실행 방법
1. 필요 패키지 설치
bash
복사
편집
pip install pymysql
2. MySQL 서버 실행 후, 포트 확인
기본 포트는 3306이지만, 코드에서는 3307로 사용 중입니다.

본인의 환경에 맞게 수정하세요.

3. 데이터베이스 및 테이블 생성
MySQL CLI 또는 GUI를 통해 아래 쿼리 실행:

sql
복사
편집
CREATE DATABASE schedule_db;
USE schedule_db;

CREATE TABLE schedules (
    id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(200) NOT NULL,
    description TEXT,
    start_datetime DATETIME NOT NULL,
    end_datetime DATETIME,
    is_completed BOOLEAN DEFAULT FALSE
);
4. 프로그램 실행
bash
복사
편집
python your_script_name.py
🔐 DB 연결 정보 (기본값)
항목	값
host	localhost
port	3307
user	root
password	1234
database	schedule_db

⚠️ 보안상 실제 배포 시에는 환경변수로 DB 정보를 관리하는 것을 권장합니다.

📌 사용 예시
markdown
복사
편집
1. 일정 추가
2. 일정 보기
3. 일정 완료
4. 종료
선택: 1
일정 제목 : 회의
내용 : 팀 미팅
일정 시작일 : 2025-07-20 10:00:00
일정 종료일 : 2025-07-20 11:00:00
일정이 추가 되었습니다
📄 라이선스
본 프로젝트는 학습용으로 자유롭게 사용 가능합니다.
