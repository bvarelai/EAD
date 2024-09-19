# EAD (2023-2024)
## Practicas
### SQL Analitico
#### Grouping set
##### Ejemplos
```sql
SELECT job,deptno, count(*)
FROM emp 
GROUP BY GROUPING SETS (job,deptno);
```
- Seria como hacer dos consultas donde cada una hace un group by (una con job y otra con deptno)
seria hacer un count(*) con job y despues count(*) con deptno
```sql	
SELECT job,deptno, count(*)
FROM emp 
GROUP BY job,deptno
```
```sql
SELECT count(*)
FROM emp 
```
```
SELECT job,deptno, count(*)
FROM emp 
GROUP BY GROUPING SETS (job, deptno, (job, deptno), ());
```
- Este seria como:   
Agrupar mgr,job                          
         mgr,deptno    
   
```sql
SELECT mgr, job, deptno, count(*)
FROM emp 
GROUP BY GROUPING SETS mgr, (job, deptno, (job, deptno), ());
```
##### Especificaciones de Grouping sets
###### CUBE
```sql
SELECT job,deptno, count(*)
FROM emp 
GROUP BY CUBE (job,deptno)
```


