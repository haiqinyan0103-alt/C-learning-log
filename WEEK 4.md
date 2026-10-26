## have learned

function

pointer

`struct\`

`void pointer`

reinterpretation

`const int *p`



## mistake I got

#### 1  `struct battery s1`   

Actually the `s1`is the true "address/house"

###### in that way : the wrong syntax:

`struct battery s1 = {3700, 60};`
`printf("%d\n", battery.percent); // ❌ ：'battery' undeclared`
`void *p = &battery;              // ❌ ：'battery' undeclared`

##### the right syntax:

`printf("%d\n", s1.percent); // ❌ ：'battery' undeclared`
`void *p = &s1;            

(2)

Do not missing Space between type and identifier  .

`struct batterybat = {3700, 60}; // ❌

(3)

``struct sensor s1{25, 60}; // ❌` 

`struct sensor s1 = {25, 60}; //Standard C requires the '=' assignment operator[cite: 1]`

remember to add ; by the end of }

### 2 pointer

`int *p;`
`*p = a; // ❌  (Segmentation Fault)`

###### the right syntax:

`int *p = &a; // 
`**int b = *p;  //**` 

##### (2)

`*p = &a; // ❌ `

right syntax:

int *p = &a; // Link p to a by storing its address
int b = *p;  //  b == a / Dereference to read the value; now b == a

### KEY:

##### label the * as the key to open the door of the"house/address " to get the content inside

(3)

redundant dereference when copying struct pointers

`struct sensor *sp = *p; // ❌ `

**the right syntax:**

`struct sensor *sp = p;  //Pass address directly between pointers without *`

# final task: charge the battery

`\#include <stdio.h>`

`struct battery`

`{`

 `int voltage;`

 `int percent;`

`};`

`void chargebattery(struct battery *p , int addpercent);`

`int main()`

`{`

 `struct battery s1 = {3700 , 60};`

 `chargebattery(&s1 , 25);`

 `printf("%d\n",s1.percent);`

 `void *p = &s1;`

 `printf("%d\n",*(int *)p);`

 `return 0;`

`}`

`void chargebattery(struct battery *p ,  int addpercent)`

`{`

 `p->percent = p->percent + addpercent;`

`}`











