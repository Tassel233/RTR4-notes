## Directional Lights

* simplest model
* $l$ and $c_{light}$ are both constant
* have no location
* work well when the distance to the light is large relative to the scene size



## Punctual Lights

A punctual light is not one that is on time for its appointments, but rather a light that has a location, unlike directional lights.



### Point / Omni Lights

Point lights(omni light) uniformly emit light in all directions, while $c_{light}$ varies as a function of the distance $r$.

<img src="D:\notes\RTR4\RTR4-notes\Chapter5 Shading Basics\assets\image-20260324213533989.png" alt="image-20260324213533989" style="zoom:67%;" />

We can infer that

<img src="D:\notes\RTR4\RTR4-notes\Chapter5 Shading Basics\assets\image-20260324213552109.png" alt="image-20260324213552109" style="zoom:67%;" />

Although technically the correct distance attenuation for a point light, there are some issues that make this equation less than ideal for practical shading use.

1. As the value of $r$ tends to 0, the value of $c_{light}$ appears to be infinite. To address this, a small modification $\epsilon$ can be added to the denominator( The Unreal game engines uses $\epsilon$ = 1 cm ).

   <img src="D:\notes\RTR4\RTR4-notes\Chapter5 Shading Basics\assets\image-20260324213607027.png" alt="image-20260324213607027" style="zoom:67%;" />

   Alternatively, we can clamp $r$ to a minimum value $r_{min}$.

   <img src="D:\notes\RTR4\RTR4-notes\Chapter5 Shading Basics\assets\image-20260324213624082.png" alt="image-20260324213624082" style="zoom:67%;" />

2. For efficient rendering, it is desirable for lights to reach 0 intensity at some distance, while it keeps decreasing and it never goes to 0

   One solution is to multiply the **inverse-square equation** by a **windowing function**.

   

   One such function is like this:

   <img src="C:\Users\jinkail\AppData\Roaming\Typora\typora-user-images\image-20260324211937860.png" alt="image-20260324211937860" style="zoom:67%;" />

   (The +2 means to clamp the value, if negative, to 0 before squaring it.)

   <img src="D:\notes\RTR4\RTR4-notes\Chapter5 Shading Basics\assets\image-20260324213638949.png" alt="image-20260324213638949" style="zoom:50%;" />

   In fact, the choice of falloff function may be driven by creative considerations. 

   For example, the Unreal Engine has two modes for light falloff: an inverse-square mode and an exponential falloff mode that can be tweaked to create a variety of attenuation curves

   

### Spot Lights





