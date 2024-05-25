# Silk.NET.SDL

[Simple DirectMedia Layer](https://www.libsdl.org) is a cross-platform
development library designed to provide low level access to audio, keyboard,
mouse, joystick, and graphics hardware via OpenGL and Direct3D.

Silk.NET provides bindings for SDL2 with its Silk.NET.SDL packages. The
packages allow you to do cross platform window and input handling, and access
to audio and graphics hardware, with C# code in .NET and Mono.

## Quickstart

SDL package
SDL Native package

### Native libraries in separate package

Silk.NET provides pre-compiled native libraries in its "Native" packages.
These packages contain builds for all supported platforms and will be used
automatically if they are referenced in your project.
For SDL, the native package is called Ultz.Native.SDL, and is referenced
automatically.

## Usage of unmanaged pointers

Most raw bindings in Silk.NET are unsafe, as they directly map on the
pointer logic and structures of the bound APIs. These raw bindings are
the most performant but require diligence in their use.

To use pointers, an unsafe context is required. Pointers are unmanaged: make sure objects are released
or disposed at appropriate times.
See the [C# specification](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/unsafe-code)
for more information about unsafe code.

## Basic windowing example

```csharp
Console.WriteLine("Hello");
```
