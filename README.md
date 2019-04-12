# BigData-Architecture-Assignment
엔코아 '빅데이터 아키텍처 수립 평가 과제' DB반 5조

## 하둡 아키텍처 설계 및 구축 과제
- 주어진 과제에 맞춰 시스템 구성도를 작성하고 직접 구축해보는 과제
- Ambari를 활용하여 하둡 시스템 

## Condition A
- 3개 이상의 DataNode로 구성된 cluster를 구성하는 HDFS를 만들 것
  - A. YARN/MR(MAP/REDUCE)/Zookeeper가 service로 존재할 것
  - B. HDP를 이용하는 경우 관리 DBMS는 MariaDB or Mysql
  - C. Data Block Size는 32MB로 설정
  - D. Block Replication(복제)는 2로 설정
  - E. NameNode와 Hive service는 각각 다른 Host에서 구동할 것
- Hive 서비스 제공
  - A. Hive metastore는 hive 서버(hive server master)와 동일한 호스트에 존재할 것
  - B. Hive JDBC를 제공할 것
  - C. 데이터가 존재하는 테이블을 3개 이상 만들 것
- Spark 서비스 제공
- Zepplin notebook 서비스 제공

## Condition B
- 각 Host는 아래의 사양을 만족해야 한다.
  - A. 각 Host의 Disk Size는 48 ~ 64GB로 설정한다.
  - B. 각 Host의 CPU Core는 2~4개로 설정한다.
  - C. 각 Host의 RAM Size는 4.8GB 이상으로 설정한다.
- Root는 패스워드가 없어야 한다.
  - A. HDP 설치시 ssh private key 입력을 통한 인증(키교환)으로 Host를 등록해야 한다.
- 클러스터는 외부에서 접속 가능하도록 가상 브릿지 네트워크를 이용한 통신 구성을 해야한다.
  - A. 네트워크 대역은 상관 없음
- 방화벽 서비스는 disable
- 서비스 연결 시 host명 return 문제를 해결해야 한다.

## Condition C
- HDP에 포함된 service의 용도 및 역할을 설명한다.
- 시스템 구성도를 작성한다. (VM(Virtual Machine), 네트워크, service 구성 등 명시)
- 상기 조건들을 모두 확인할 수 있는 가이드를 제공해야 한다.
  - A. HDP 관리 페이지 접속 방법
  - B. Hive 접속 방법
  - C. Spark History 서버 접속 방법
  - D. Zeppelin notebook 접속 방법
  
## 환경
- OS : Linux (Ubuntu)
- Virtual Machine 4대
