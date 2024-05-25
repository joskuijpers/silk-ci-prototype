# Silk.NET.WebGPU

WebGPU exposes an API for performing graphics and compute operations on GPUs.
It was primarily built as an API for web applications in browsers, but it can
also be used as a cross-platform graphics API for native applications.

Silk.NET.WebGPU provides a C# binding of the WebGPU API. Silk.NET also provides
cross-platform native builds of wgpu and dawn. With this package is easier to
make cross platform applications with GPU rendering and compute.

As WebGPU is a [standardized interface](https://www.w3.org/TR/webgpu/), it can
have different backing implementations. One of these implementations is called
wgpu, a Rust implementation of the WebGPU APIs used in browsers. This library
abstracts over Vulkan, DirectX and Metal to form a cross-platform GPU interface.

> It is currently not possible to use Silk.NET.WebGPU to build apps that run in
> a browser.

## Quickstart

WebGPU package
WGPU native as backend

> ### Native libraries in separate package
> Silk.NET provides pre-compiled native libraries in its "Native" packages.
> These packages contain builds for all supported platforms and will be used
> automatically if they are referenced in your project.
> Native cross-platform builds of the wgpu-rs project are provided in
> **Silk.NET.WebGPU.Native.WGPU**.

```csharp
// Retrieve the entrance to the API. This will look up a native implementation
// of WebGPU, such as WGPU.
var wgpu = WebGPU.GetApi();
if (wgpu == null)
    throw new Exception("Unable to load WebGPU api");

unsafe
{
    var instance = wgpu.CreateInstance(new InstanceDescriptor());
}
```

The C# API closely matches the standard API.
Read more about using WebGPU at [webgpufundamentals](https://webgpufundamentals.org) or [MDN](https://developer.mozilla.org/en-US/docs/Web/API/WebGPU_API).

## Usage of unmanaged pointers

Most raw bindings in Silk.NET are unsafe, as they directly map on the
pointer logic and structures of the bound APIs. These raw bindings are
the most performant but require diligence in their use.

To use pointers, an unsafe context is required. Pointers are unmanaged: make sure objects are released
or disposed at appropriate times.
See the [C# specification](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/language-specification/unsafe-code)
for more information about unsafe code.
