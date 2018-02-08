# ORACLE日期处理语法汇总

### 1、计算两个日期之间的时间单位（天、小时、分钟...）  
天：`ROUND(TO_NUMBER(END_DATE - START_DATE))`或者`FLOOR(TO_NUMBER(END_DATE - START_DATE))`  
小时：`ROUND(TO_NUMBER(END_DATE - START_DATE) * 24)`或者`FLOOR(TO_NUMBER(END_DATE - START_DATE) * 24)`  
......  
注意具体的需求，来选择是天还是小时

### 2、获取两个日期之间的年列表
`SELECT TO_CHAR(ADD_MONTHS(TO_DATE('2014', 'yyyy'), (ROWNUM - 1) * 12),'yyyy') as yearlist
  FROM DUAL
CONNECT BY ROWNUM <=
           months_between(to_date('2015', 'yyyy'), to_date('2014', 'yyyy')) / 12 + 1`
           
### 3、获取两个日期之间的年月列表
`SELECT TO_CHAR(ADD_MONTHS(TO_DATE('2014-10', 'yyyy-MM'), ROWNUM - 1),'yyyy-MM') as monthlist
  FROM DUAL
CONNECT BY ROWNUM <=
           months_between(to_date('2015-06', 'yyyy-MM'), to_date('2014-10', 'yyyy-MM')) + 1`
### 4、获取两个日期之间的日期列表
`SELECT TO_CHAR(TO_DATE('2018-02-01', 'yyyy-MM-dd') + ROWNUM - 1, 'yyyy-MM-dd') as daylist
  FROM DUAL
CONNECT BY ROWNUM <=
           trunc(to_date('2018-02-28', 'yyyy-MM-dd') - to_date('2018-02-01', 'yyyy-MM-dd')) + 1`
