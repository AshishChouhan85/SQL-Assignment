## Dhruv's approach:

1. Q1:
    * He  made a  join operation to get the count of male and female employees in each department. 
    * Since MySQL does not have a full join, he used a union of a left join and a right join to achieve the desired result. 
    * The first select statement gets the count of male employees by department, while the second select statement gets the count of female employees by department. He used left join to combine the above tables. 
    * He applied a similar approach with right join.
    * Finally, he applied union on results of left join and right join. The final output displays the department name, the number of male employees, and the number of female employees for each department.

2. Q2:
    * He made a table consisting of three columns using union of Candidate name, Candidate Salary and Month name for each month.
    * The table looked like this:
    ```
    Name    Value   Month
     X      5200    Jan
     Y      9023    Jan
     Z      9834    Jan
     W      3244    Jan
     X      9093    Feb
     Y      8942    Feb
     Z      8197    Feb
     W      4321    Feb
     X      3832    Mar
     .        .      .
     .        .      .
     ```
    * Then he selected all those records from this table when Name matched Name from Name of original table and Value matched with ```GREATEST(Jan, Feb, Mar)``` from original table.
    * As a correlated query was used for matching, this approach will be slow for tables with large number of records.

3. Q3:
    * He used ```GROUP_CONCAT()``` on Candidate ID and grouped them by marks.
    * He also used a variable ```rk``` to rank these records.

4. Q4:
    * First he wrote a subquery in which he selected email ID and Candidate ID where Candidate ID is minimum for that email ID. He named this table as Temp.
    * Then he extracted the list of Candidate ID from Temp table and deleted all those records from the main table whose Candidate ID were not present in this list.
    * As he used ```DELETE``` and outer table and subquery table were same, giving an alias to subquery table was necessary.

## Shubham's code

1. Q1:
    * He use ```SUM()`` function to count number of males and females and then grouped them by department.

2. Q2:
    * He first made a table named data using union of three months. This table was similar to Dhruv's table.
    * Then he selected the maximum salary for each candidate using correlated subquery.

3. Q3:
    * He used ```GROUP_CONCAT()``` on Candidate ID and grouped them by marks.
    * He also used ```ROW_NUMBER()``` to rank these.

4. Q4:
    * First he duplicated the original table and named the new table as old_candidates.
    * Then he made a list of Candidated IDs using ```MIN()``` and ```GROUP BY()```. This list consisted of minimum Cabdidate ID corresponding to each mail ID.
    * Finally, he deleted all those records from original table whose Candidate ID were not present in this list.