# SLANG
Slang is a Simple Linear Algebra Notation library for Graphics programming in C++ based on the [OpenGL Shading Language (GLSL) specification](https://registry.khronos.org/OpenGL/specs/gl/GLSLangSpec.4.50.pdf).

The intent is to provide a single header file with the classes and operators that enable you to write GLSL code like this in your C++ programs:
```C++
const mat2 M2 = mat2(0.8, -0.6, 0.6, 0.8);

float fbm(vec2 p, int octaves)
{
    float a = 0.0;
    float b = 1.0;
    vec2 d = vec2(0.0);
    for (int i=0; i < octaves; i++)
    {
        vec3 n = noised(p);
        d += n.yz;
        a += b*n.x/(1.0 + dot(d,d));
	b *= 0.5;
        p = 2.0*M2*p;
    }
    return a;
}
```
