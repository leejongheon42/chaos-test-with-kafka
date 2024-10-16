# chaos-test-with-kafka
카프카 미러메이커를 이용한 구버전, 신버전 카프카 마이그레이션 정합성 테스트

# 테스트 방법
- clusterA / clusterB / mirrorMaker docker-compose 파일 실행
- mirrorMaker docker 진입하여 mirrorMaker 실행
  - /opt/bitnami/kafka/bin/connect-mirror-maker /tmp/kafka/config/mm2.properties
 
- kafka-ui-A 접속해서 topic 생성
  - 파티션 3개 / Replication Factor 3개
- Kafka-ui-B 토픽 복사여부 확인
- Consumer.py 와 Producer.py 순차적으로 실행시키고 evnet 복사되는지 여부 테스트
