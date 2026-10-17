# WEEK 3 FINAL PRACTICE:  2D Array Temperature Analysis & Peak Tracking

### Goal:

#### Implement a C program utilizing a 3×2 `float` array to record 3 days of morning and evening temperatures. Compute and display daily averages using nested loops with proper accumulator resetting, and locate the global peak temperature alongside its matrix coordinates. 

#### my result:

`\#include<stdio.h>`

 `int main()`

`{`

 `float tem[3][2];// 2D array :3 days (rows) x 2 readings per day (columns)`

 `int row;`     

 `int col;`

 `float temsum = 0;  //Daily accumulator for computing averages`

 `for (row = 0; row < 3; row++) //Input loop: populate the 2D array`

 `{`

  `for (col = 0; col < 2; col++)`

  `{`

   `scanf("%f", &tem[row][col]);  //`

  `}`

``  

 `}`

 `float temmax = tem[0][0];  //Initialize maximum temperature tracker with the first reading`

 `int maxindexcol;`  

 `int maxindexrow;`

 `for ( row = 0; row < 3; row++)  //Processing loop: display readings, calculate daily averages, and track global max`

 `{`

  `printf("today is day%d\n", row + 1);  // display day-number base on 1`

  `temsum = 0;  //important: Reset accumulator at the start of each day to prevent cross-day pollution`

  `for ( col = 0; col < 2; col++)   `

  `{`

   `printf("%.2f\n", tem[row][col]);`

   `temsum = temsum + tem[row][col];` 

   `if (temmax <= tem[row][col])  // Update maximum value and store its coordinates`

   `{`

​    `temmax = tem[row][col];`

​    `maxindexrow = row;`       

​    `maxindexcol = col;`

``    

   `}`

``   

  `}`

  `printf("today's tem average is %.2f\n", temsum / 2); //show the average per day`

 `}`

 `printf("the maxtem is: %.2f\n", temmax);  //show the maximum of tem`

 `printf("manxindex is tem[%d][%d]",maxindexrow , maxindexcol); // show which is the max tem .`

 `return 0;`

`}`