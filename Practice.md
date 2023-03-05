## Query A1: Enter a function that calculates the total cost of all animal rescues in the PETRESCUE table.

### select SUM(COST) from PETRESCUE;

## Query A2: Enter a function that displays the total cost of all animal rescues in the PETRESCUE table in a column called SUM_OF_COST.

### select SUM(COST) AS SUM_OF_COST from PETRESCUE;

## Query A3: Enter a function that displays the maximum quantity of animals rescued.

### select MAX(QUANTITY) from PETRESCUE;

## Query A4: Enter a function that displays the average cost of animals rescued.

### select AVG(COST) from PETRESCUE;

## Query A5: Enter a function that displays the average cost of rescuing a dog.

#### Hint - Bear the cost of rescuing one dog on one day, which is different from another day. So you will have to use an average of averages.

### select AVG(COST/QUANTITY) from PETRESCUE where ANIMAL = 'Dog';

## Query B1: Enter a function that displays the rounded cost of each rescue.

### select ROUND(COST) from PETRESCUE;

## Query B2: Enter a function that displays the length of each animal name.

### select LENGTH(ANIMAL) from PETRESCUE;

## Query B3: Enter a function that displays the animal name in each rescue in uppercase.

### select UCASE(ANIMAL) from PETRESCUE;

## Query B4: Enter a function that displays the animal name in each rescue in uppercase without duplications.

### select DISTINCT(UCASE(ANIMAL)) from PETRESCUE;

## Query B5: Enter a query that displays all the columns from the PETRESCUE table, where the animal(s) rescued are cats. Use cat in lower case in the query.

### select * from PETRESCUE where LCASE(ANIMAL) = 'cat';
