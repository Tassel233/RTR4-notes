Pipeline optimization is a process in which we first maximize the rendering speed, then allow the stages that are not bottlenecks to consume as much time as the bottleneck.



## Locating the Bottleneck

Two ways to find:

1. Set up several tests, where each test decreases work of a particular stage. If one of these tests causes the frames per second to increase, the bottleneck stage has been found.
2. Reduce the workload on the other stages without reducing the workload on the stage being tested. If performance does not change, the bottleneck is the stage where the workload was not altered.



### Application Stage

1. Send low data that causes the GPU to do little or no work, using a null driver. Thus, the app on the CPU is always the bottleneck.

2. Underclock or overclock the CPU to see if performance change in proprotion to the CPU rate.



### Geometry Processing Stage

This stage is the most difficult stage to test.

There are two main areas where a bottleneck can occur in the geometry stage: **vertex fetching** and **processing**.

1. Increase the size of the vertex format to see if the bottleneck is due to **object data transfer**. For example, send several extra texture coordinates per vertex.
2. For vertex processing testing, we can make the shader program longer



*TODO: geometry shader & tessellation shader...*



### Rasterization Stage

To find if rasterization is truly the bottleneck, increase the execution time of both the vertex and pixel shaders by increasing their program sizes. If the render time per frame does not increase, then the bottleneck is in the rasterization stage.





### Pixel Processing Stage

* Change the screen resolution(also affects other stages).
* Add more instructions on pixel shaders. Be aware of the compiler optimization.
* Replace a texture with a 1 * 1 resolution to test texture cache missing bottleneckl.



### Merging Stage

Changing the output bit depth for buffers is one way to vary the bandwidth costs for this stage and see if it could be the bottleneck.

