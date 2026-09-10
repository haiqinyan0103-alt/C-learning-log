# WEEK 1





##### ![image-20260909191122052](F:/typoraimage/image-20260909191122052.png) 

#####   **KEY POINT:****Only one `int main()` is  allowed to exist in one  c program** (otherwise the program 'll fail to run)



##### ![image-20260909194054718](F:/typoraimage/image-20260909194054718.png) accordingly, the program will terminate at the `[return 0]`   ( in c program `return *<u>0</u>*:` the number means returning  normally )               The red `int` means the program will <u>end with an integer</u>



## HOW TO STEP THROUGH CODE LINE BY LINE:

In general situations, use the shortcut key *ctrl+f5* will run the whole c program,if we want to run the program code line by line

1: **set a breakpoint on the first line of  `main()`**  with *F9* or just click the left gutter (then a red dot will appear on the left gutter.)  

2:press *F5*  to start  debugging(the program will stop at the line of the breakpoint as it was launched and that line will become yellow )

3: Then press F10 consistently to make it run line by line. 

## <u>the mistake I made:</u> 

#### 1

only one debug file is allowed to be running at the same time,  ![image-20260910121945748](F:/typoraimage/image-20260910121945748.png)

in that situation    ![image-20260910122130118](F:/typoraimage/image-20260910122130118.png)

press *ctrl+shift+D*  opening the debug interface to stop the debug program ![image-20260910122400811](F:/typoraimage/image-20260910122400811.png)

and just restart another one is ok







#### 2       misunderstanding of concept ![image-20260910125204545](F:/typoraimage/image-20260910125204545.png)

the `int main()` doesn't mean make a box containing integer      (so this one means it will return or "deliver"  integer )

it actually means what type of result this *function* should return  

the "body"  of the *function* is  inside  `{}`      (what should it do )

the `return 0;` is a signal of "the program has done normally "
