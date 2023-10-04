![image](https://github.com/pierodn/slang/assets/85252731/d52de734-6fd9-4595-8d34-1dc5c34a5fe0)
___
Slang is a **S**imple **L**inear **A**lgebra **N**otation library for **G**raphics programming in C++ based on the [OpenGL Shading Language (GLSL)](https://registry.khronos.org/OpenGL/specs/gl/GLSLangSpec.4.50.pdf).

The intent is to provide a single header file with the types and operators that enable you to write GLSL code like this in your C++ programs:
```C++
const mat2 M2 = mat2(0.8, -0.6, 0.6, 0.8);

float fbm(vec2 point, int octaves)
{
    float a = 0.0;
    float b = 1.0;
    vec2 d = vec2(0.0);
    for (int i = 0; i < octaves; i++)
    {
        vec3 n = noised(point);
        d += n.yz;
        a += b*n.x/(1.0 + dot(d,d));
	b *= 0.5;
        point = 2.0*M2*point;
    }
    return a;
}
```

Modern applications often comprise components that operate on both the CPU and GPU, frequently requiring interaction between them. Consequently, it is not uncommon to encounter a codebase written in both C++ and GLSL. Both languages derive from the C language but, given C++'s robust expressive capabilities, it is feasible to equip it with the same familiar types and operators that its counterpart, the GPU-centric C-like language GLSL, employs. This alignment not only fosters consistency but also promotes conciseness and a more aesthetically pleasing coding style. That's why Slang : )
