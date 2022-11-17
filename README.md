# Excel
 Cool stuff in excel :wink: 

## Gantt Example

### * *What  is a **Gantt**? :chart: *  *

Gantt is a very common type of chart that depicts how a process is being executed.
It´s a very common tool in Project Managment of any  kind (usually to compare the expected/budgeted
timings Vs the actual timings), as it depicts Time in  columns and each row is a task or process that 
has an assinged time frame in mind. 

###What is in this example?
In this example i took the gantt formulas needed to buildit in a way to track credit card expenses.

###*Guiding questions :
1 "When will this purchse be 'fully paid'?"
2 "How much money will be  charged in each month per credit card?"
3 "Who made the purchase?"
4 "Is the bill total going  up or down?"
5 "What will be the remaining purchase limit?" (pending)

###*What is the core functionality?
The "core" for this chart is applying correctly "dinamyc formating".
Each Cell from **J6** to **AA:30**, has the same relative formula:
	* *(=+IF(AND(J$5>=$F6;J$5<=$G6);$H6;0)* *
This formula will conditionally check if the value of **J5(our month label)** is within 
our  start and end  purchase date (hidden in **H6 and F6**).If this is true it will 
return us **H6 (purchase amount)**.
