*"A chain is no stronger than its weakest link."*

![image-20251114231112044](assets/image-20251114231112044.png)

## Application

The developer has full control over what happens in the **application stage** since it executes on the CPU

Some of the tasks **traditionally** performed on the CPU include *collision detection, global acceleration algorithms, animation, physics simulation,* and many others, depending on the type of application.



## Geometry Processing

![image-20251115230846341](assets/image-20251115230846341.png)



### Clipping

A primitive that lies fully inside the view volume will be passed on to the next stage as is. Primitives entirely outside the view volume are not passed on further, since they are not rendered. It is the primitives that are partially inside the view volume that require clipping.























