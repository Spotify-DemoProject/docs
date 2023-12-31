* README.md is written in KOREAN
# Spotify Demo Project
Spotify API로부터 앨범 및 아티스트 데이터를 수집 & 적재하는 자동화 데이터 파이프라인입니다.

# Pipeline Structure
<img width="809" alt="스크린샷 2023-12-31 오후 8 53 21" src="https://github.com/Spotify-DemoProject/docs/assets/130134750/f3e863a2-d4ae-4fad-9e8a-a0b2fc09ec2f">

# Used Stacks
### Scheduling
- Airflow (Docker 기반의 서비스 빌드)
- Cron

### API & ETL
- FastAPI + uvicorn[standard]

### Processing
- Spark (Streaming Kafka Application)
- Kafka

### DL(Storage)
- AWS S3

### Monitoring
- Grafana
