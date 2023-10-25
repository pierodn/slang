![image](https://github.com/pierodn/slang/assets/85252731/3a8c8b2b-cd6b-48c9-95a5-c597b036b8f5)

___
Slang is a **S**imple **L**inear **A**lgebra **N**otation for **G**raphics programming in C++ based on the [OpenGL Shading Language (GLSL)](https://registry.khronos.org/OpenGL/specs/gl/GLSLangSpec.4.50.pdf).

The intent is to provide a C++ linear algebra library in one single header that defines and implements the same types, operators and functions of the GLSL specification, so to enable you to write GLSL code like this in your C++ programs:
```GLSL
vec3 rotate(vec3 point, vec3 axis, float angle)
{
    float h = 0.5 * angle * PI/180;
    vec4 q = vec4(axis * sin(h), cos(h)); 	
    return point + 2.0 * cross(q.xyz, cross(q.xyz, point) + q.w * point);
}
```
### Motivation
The motivation is two folded:
1. You may happen to write a C++ application in some domains like graphics programming, image processing, search engine ranking, signal analysis, artificial intelligence, quantum computing, genetics, graph theory, electrical circuits, greedy algorithms, traffic flow, markov vhain, leonteif economic model, community detection, linear regression, linear programming, cryptography, error correcting codes (the list goes on) and find out that liner algebra is basically your *swiss army knife* when it comes to these things BUT is not built-in in C++ as it is in GLSL, for example.
2. You may happen to have in your application components in both CPU and GPU (likely interacting with each other) and find out that it would be nice to be allowed to use the same programming style to foster consistency, conciseness, readibility. And this is actually possible because C++'s robust expressive capabilities allows to equip it with the same types and operators that its counterpart, the GPU-centric GLSL, employs.

And here is why Slang.

### History
It all started in 2008 when I crafted a LOD algorithm for terrains, designed a fractal terrain generator, and developed a 3D engine for rendering. As I delved into this project, a desire for consistency and a pleasing coding style led me to contemplate the idea of having the same GLSL types available in C++. To my surprise, I couldn't find a suitable alternative, prompting me to embark on the journey of creating my own set of GLSL types and operators for C++.

Fast forward to 2023, several years have passed, and the landscape has evolved with the emergence of alternatives. Yet, despite these developments, I still find myself unsatisfied with the options available, yearning for a solution that truly aligns with my vision.
