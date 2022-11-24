# Excel
 Cool stuff in excel :wink: 

## Gantt Example

### What is a **Gantt chart**? :chart:

It´s is a very common type of chart that depicts how a process is being executed. Quite the common tool in Project Managment of any  kind (usually to compare the expected/budgeted
timings Vs the actual timings), as it depicts Time in  columns and each row is a task or process that 
has an assinged time frame in mind. 

### What is in this example?
In this example i took the gantt formulas needed to buildit in a way to track credit card expenses.

### Guiding questions :
1. "When will this purchse be 'fully paid'?"		
2. "How much money will be  charged in each month per credit card?"
3. "Who made the purchase?"   
4. "Is the bill total going  up or down?" 
5. "What will be the remaining purchase limit?" (pending)

### What is the core functionality?
The "core" for this chart is applying correctly "dinamyc formating".
Each Cell from **J6** to **AA:30**, has the same relative formula:
```
	(=+IF(AND(J$5>=$F6;J$5<=$G6);$H6;0)
```
This formula will conditionally check if the value of **J5(our month label)** is within 
our  start and end  purchase date (hidden in **H6 and F6**).If this is true it will return us **H6 (purchase amount)**.
In this version we are just mirroring with the + the source table. We could feed into the model a whole dynamic table for it to load  more dynamically and use Slicers and timelines to filtermore optimally.  in this Version (1.0) we  only have  column filters. They will dinamically change when we apply other filters of the other columns.

### Aggregatin values in the top columns.
While we are sourcing the valeus on exact dates **(dd/mm/yyyy)**. Gannt columns havec been formatted as **MM** to show only the month and on top it´s Formated as **YYY** to show only the year. If we need a more detailed(let´s say daily or weekly) we need to do 2 things:
1. Change the **Cell formatting** from  MM to D or DD or DDD or DDDD for Days, depending on what format is better  to offer.
Date example 01/05/2019
	D 	= 1
	DD 	=01
	DDD	= Wed
	DDDD= Wednesday
	
2. Change the 30 to 1 for days or 7 for weeks, on all our date dynamic values. this way they will dynamicalyy show  +1 days from  the  starting date,  +7 days (1 week) or +30(1 month).
 
	A.	On the Core Cell in yellow **E1**, which indicates the starting  value of our chartt. it´s currently seet as monthly therefore :
	```
	=+MIN(F6:G29)-30	
	```
	B. On *J5* 5 we have to start our gantt 
	```
	=+E1+(Show.Sem*30)
	```
	C. on all other rows 5 cells, which mirror the previous colum +30.