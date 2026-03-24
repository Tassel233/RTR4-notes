## Directional Lights

* simplest model
* $l$ and $c_{light}$ are both constant
* have no location
* work well when the distance to the light is large relative to the scene size



## Punctual Lights

A punctual light is not one that is on time for its appointments, but rather a light that has a location, unlike directional lights.



### Point / Omni Lights

Point lights(omni light) uniformly emit light in all directions, while $c_{light}$ varies as a function of the distance $r$.

<img src="C:\Users\jinkail\AppData\Roaming\Typora\typora-user-images\image-20260313182637701.png" alt="image-20260313182637701" style="zoom: 67%;" />

We can infer that

<img src="C:\Users\jinkail\AppData\Roaming\Typora\typora-user-images\image-20260313183724053.png" alt="image-20260313183724053" style="zoom:50%;" />

Although technically the correct distance attenuation for a point light, there are some issues that make this equation less than ideal for practical shading use.









### Spot Lights





