# 데이터베이스

### 생각해봐야할 부분
+ 운영체제 캐시에 의존도가 높은 스토리지 엔진을 사용할 경우 쿼리를 최적화 하려면 어떻게 해야 하는지
+ performance, sys schema 분석을 통한 쿼리 효율 향상

#### SELECT 쿼리문에서의 실행순서?
+ FROM / JOIN → WHERE → GROUP BY → HAVING → ORDER BY → LIMIT

#### SQL 내장함수 - 그룹함수(aggregation)
