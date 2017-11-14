# ORACLE语法技巧汇总

### 计算两个日期之间的时间单位（天、小时、分钟...）  
天：`ROUND(TO_NUMBER(END_DATE - START_DATE))`
