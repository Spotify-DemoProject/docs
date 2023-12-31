* README.md is written in KOREAN
# Spotify Demo Project
Spotify API로부터 앨범 및 아티스트 데이터를 수집 & 적재하는 자동화 데이터 파이프라인입니다.<br><br>

# Pipeline Structure
<img width="809" alt="스크린샷 2023-12-31 오후 8 53 21" src="https://github.com/Spotify-DemoProject/docs/assets/130134750/f3e863a2-d4ae-4fad-9e8a-a0b2fc09ec2f"><br><br>

# Used Stacks
### Scheduling
- Airflow (Docker 기반의 서비스 빌드) : API 서버 작업 스케줄링 & Kafka 메세지 발행
- Cron : Postgres DB 백업 & Spotify Access Token 재발급

### API & ETL
- FastAPI + uvicorn[standard] : ETL 프로세스 수행

### Processing
- Spark (Streaming Kafka Application) : Kafka 메세지의 파라미터를 기반으로 데이터 가공
- Kafka : Spark 어플리케이션 작업 스케줄링

### DL(Storage)
- PostgreSQL : 반복 사용 API 파라미터 적재
- AWS S3 : 백업 스냅샷(.sql) 및 가공 데이터(.parquet) 적재

### Monitoring
- Grafana<br><br> : Kafka 서버 모니터링

# Results
### Parquet 데이터 적재 (앨범 / 아티스트)
<img width="721" alt="스크린샷 2023-12-30 오후 9 57 48" src="https://github.com/Spotify-DemoProject/docs/assets/130134750/4dfdd9af-da34-4508-aff5-100c8f93206d">

### Postgres 데이터 백업
<img width="653" alt="스크린샷 2023-12-31 오후 9 03 25" src="https://github.com/Spotify-DemoProject/docs/assets/130134750/7d5a4c54-0c16-4f2b-9580-fb6984ec3495">

