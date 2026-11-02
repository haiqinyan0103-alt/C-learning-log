## Have learned

###### 1 

#### double point `*pp/int **PP` with outside function

knowing the right concept ,eschew confusion

我的理解：为了方便我的理解,去掉”里面“这个概念 现在是如果    `int  *ptr = a`  那么 `ptr`    本身等于    `&a`   也就是    `ptr = &a`   （重点转变是这里 ptr 本身不等于 ptr 本身地址，本身地址这个词去掉，就叫 `p` 自己的地址，也可以理解成 `ptr` 指向 a的地址）然后代入形参是 `int **pp`     的函数，Ok这里    `pp = &ptr`     (二级指针 `pp` 本身等于 `ptr` 自己的地址，也可以叫 `pp` 指向 `ptr` 的地址）这个时候我  `*pp` 就代表着打开  `pp   ,  pp` 是一个指针，指针开不了，要开地址才行。 `pp=&ptr` 所以是打开了 `&ptr`  即   `\*pp = *(&ptr)  , ptr = &a   ptr`指向 `a` 的地址 ，所以如果写 `*pp = newtarget` ,  因为 `newtarget = &b` ,所以这里就是    *`ptr =  &b`,   对应着把   `&a`   替换成  `&b` 而不是把 a的值替换成 b 的值，（我觉得理解重点是*开的不是指针，而是开指针对应的地址）

`#include <stdio.h>`

`// 形参 pp 接收的是 ptr 自己的地址 (&ptr)`
`// 形参 new_target 接收的是 b 的地址 (&b)`
`void change_target(int **pp, int *new_target)`
`{`
    `// pp == &ptr`
    `// *pp 等价于 *(&ptr)，即直接代表 ptr`
    `// 这一步等价于：ptr = &b;`
    `*pp = new_target;`
`}`

`int main(void)`
`{`
    `int a = 10;`
    `int b = 20;`

    // 1. 初始化：ptr 存入 a 的地址
    int *ptr = &a; 
    printf("调用前 ptr 指向的值: %d\n", *ptr); // 输出 10
    
    // 2. 传参：将 ptr 自己的地址 (&ptr) 和目标 b 的地址 (&b) 传入
    change_target(&ptr, &b);
    
    // 3. 结果：ptr 内部存储的地址已被改写为 &b
    printf("调用后 ptr 指向的值: %d\n", *ptr); // 输出 20
    printf("验证原始变量 a 的值: %d\n", a);     // 输出 10 (a 毫无损伤)
    
    return 0;
`}`

**`void allocate_array(int **p, int n)；`**

**`createarray(&ptr , n);`**

**`p = &ptr *p = ptr     **p = *ptr`;**

#### 2: 

###  pointer array & array pointer

### 3

### void pointer

#### 4 

#### malloc pointer

`int *p = (int *)malloc(n * sizeof(int));`

# mistake I got

### 1

**Cause**: `[]` has higher precedence than `*`. `*p[i]` parses as `*(p[i])` (treats `p` as a pointer array to SegFault).

**Fix 1 (Parens)**:

C

```
(*p)[i] = 100;
```

**Fix 2 (Alias, Recommended)**:

C

```
int *arr = *p;
arr[i] = 100;
```

### 2

`const void *p`

`printf("[CHAR]:%c\n", const char *p);`     wrong



`printf("[CHAR]:%c\n", *(const char *)p);`     correct

3
