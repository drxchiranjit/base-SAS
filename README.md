# Base-SAS

### Merge tables 
```
Standards syntax:
MERGE <table1> <table2>
BY <common_variable>;

Example: 
/* Create sample data */
data sales;
   input transaction_id customer_id sale_amount;
   datalines;
   1 101 100
   2 102 50
   3 103 75
   4 101 125
   5 104 90
   ;

data customers;
   input customer_id customer_name;
   datalines;
   101 John
   102 Jane
   103 Bob
   104 Alice
   ;

/* Merge the two tables */
data sales_and_customers;
   merge sales customers;
   by customer_id;
run;
```
