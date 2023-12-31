![image](https://github.com/pierodn/slang/assets/85252731/3a8c8b2b-cd6b-48c9-95a5-c597b036b8f5)

___
Slang is a **S**imple **L**inear **A**lgebra **N**otation for **G**raphics programming in C++ based on the [OpenGL Shading Language (GLSL)](https://registry.khronos.org/OpenGL/specs/gl/GLSLangSpec.4.50.pdf).

It was developed with the intent to provide C++ a linear algebra library in one single header while implementing the types, operators and functions that comply with the GLSL specification so to enable you to write GLSL code like this in your C++ programs:
```GLSL
vec3 rotate(vec3 position, vec3 axis, float angle)
{
    float h = 0.5 * angle * PI/180;
    vec4 q = vec4(axis * sin(h), cos(h)); 	
    return position + 2.0 * cross(q.xyz, cross(q.xyz, position) + q.w * position);
}
```
### Motivation
The motivation is twofold:
1. You may happen to write C++ applications in some domains like graphics programming, procedural generation, image processing, signal processing, search engine ranking, graph theory, electrical circuits, greedy algorithms, traffic flow, markov chain, leonteif economic model, community detection, linear regression, linear programming, error correcting codes, cryptography, artificial intelligence, quantum computing, genetics (the list goes on and on) and find out that linear algebra is basically your *swiss army knife* when it comes to these things. BUT it is not natively built-in in C++ 😲
2. You may happen to have in your application components in both CPU and GPU (likely interacting with each other) and realize that it would be nice to be allowed to use the same programming style to foster consistency, conciseness, readibility. And this is actually possible because C++'s robust expressive capabilities allows to equip it with the same types and operators that its counterpart, the GPU-centric GLSL, employs.

And here is why **Slang**. A *slang* of C++ that speaks linear algebra, mimes that same expressivity offered by GLSL (which is an OpenGL standard) and enables the programmer to write linear algebra code simply. 

### History
In 2008, I developed a terrain generator and a 3D rendering engine called [gdevice](https://github.com/pierodn/gdevice). While working on this project, I wanted to make the code more consistent and readable. This led me to consider bringing GLSL types into C++. Surprisingly, I couldn't find a suitable solution, so I decided to create my own GLSL types and operators for C++.

Despite the years that have passed and the new alternatives that have emerged, I am not satisfied with the neatness, leanness, and efficiency of these options. I have therefore decided to maintain and share this elegant solution, which still aligns with my vision.
