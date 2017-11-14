# ORACLE语法技巧汇总

### 1、计算两个日期之间的时间单位（天、小时、分钟...）  
天：`ROUND(TO_NUMBER(END_DATE - START_DATE))`或者`FLOOR(TO_NUMBER(END_DATE - START_DATE))`
小时：`ROUND(TO_NUMBER(END_DATE - START_DATE) * 24)`或者`FLOOR(TO_NUMBER(END_DATE - START_DATE) * 24)`  
......
注意具体的需求，来选择是天还是小时
