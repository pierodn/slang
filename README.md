![image](https://github.com/pierodn/slang/assets/85252731/3a8c8b2b-cd6b-48c9-95a5-c597b036b8f5)

___
Slang is a **S**imple **L**inear **A**lgebra **N**otation for **G**raphics programming in C++ based on the [OpenGL Shading Language (GLSL)](https://registry.khronos.org/OpenGL/specs/gl/GLSLangSpec.4.50.pdf).

The intent is to provide a single-header library with the types, operators and functions that enable you to write GLSL code like this in your C++ programs:
```GLSL
vec3 rotate(vec3 point, vec3 axis, float angle)
{
    float h = 0.5 * angle * PI/180;
    vec4 q = vec4(axis * sin(h), cos(h)); 	
    return point + 2.0 * cross(q.xyz, cross(q.xyz, point) + q.w * point);
}
```
### Motivation
Modern applications often comprise components that operate on both the CPU and GPU, also requiring interaction between them. Consequently, it is not uncommon to encounter a codebase written in both C++ and GLSL. Now, both languages derive from the C language but C++'s robust expressive capabilities makes it possible to equip it with the same familiar types and operators that its counterpart, the GPU-centric GLSL, employs. This alignment not only fosters consistency but also promotes conciseness and a more aesthetically pleasing coding style. That's why Slang.
### History
It all started on 2008 when I developed a LOD algorithm for terrains, a fractal terrain generator and a 3D engine to do the rendering. I thought it would have been nice having the same GLSL types also in C++, for conformity, consistency, pleasing coding style. But I couldn't find a valid alternative. So I started to write my own GLSL types and operators. On 2023, years have passed and some alternatives have come out. Still, I didn't feel like they are doing the job I wish for. 
