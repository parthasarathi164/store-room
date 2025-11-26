## About the Solidworks API and connecting it to python
### Where the canonical documentation is

- Official SolidWorks API online help (the full programming guide and object model). This is the primary reference for all object interfaces and methods. [help.solidworks.com](https://help.solidworks.com/2023/english/api/sldworksapiprogguide/Welcome.htm?utm_source=chatgpt.com)
- The API contains specific methods for creating splines (e.g. `IModelDoc2::CreateSpline`, `ISketchManager::CreateSpline2` / `CreateSpline3`) — see the method pages in the official API docs for exact parameter lists and return types for your SolidWorks version. [help.solidworks.com+1](https://help.solidworks.com/2025/English/api/sldworksapi/SolidWorks.Interop.sldworks~SolidWorks.Interop.sldworks.IModelDoc2~CreateSpline.html?utm_source=chatgpt.com)

### Best community resources / Python examples / wrappers

- Official SolidWorks API also includes some Python sample pages (example: SolidWorks Electrical Python samples). Useful to see how SolidWorks itself documents Python usage in some contexts. [help.solidworks.com](https://help.solidworks.com/2024/English/api/sldworkselecapihelp/_sample_python.html?utm_source=chatgpt.com)
- GitHub projects that wrap the SolidWorks COM API for Python or show working examples (good starting points / reference code): `SolidProxy` and `pySldWrap`. These show pragmatic patterns (connect to COM, open docs, call methods, wrap objects). [GitHub+1](https://github.com/Gautreaux/SolidProxy?utm_source=chatgpt.com)
- Blogs / tutorials that show step-by-step Python + `pywin32` examples (quick, practical examples): e.g. Mason’s blog and other posts. These are useful for "how I did it" code. [mason-landry.hashnode.dev](https://mason-landry.hashnode.dev/automating-solidworks-using-python-492b15303db3?utm_source=chatgpt.com)
- Notes & tips on using `makepy` / type libraries so you can get typed constants and IntelliSense when using COM from Python (very helpful). [Stack Overflow](https://stackoverflow.com/questions/76410107/how-to-implement-makepy-with-com-based-solidworks-api?utm_source=chatgpt.com)

---

### Quick notes on approach (Python + SolidWorks)

1. **The SolidWorks API is COM-based** and the official docs are written with VB/C#/C++ signatures. Python works by calling COM objects (via `pywin32`/`win32com.client` or `comtypes`). So the primary documentation to learn exact method names/parameters is still the SolidWorks online API reference. [help.solidworks.com+1](https://help.solidworks.com/2023/english/api/sldworksapiprogguide/Welcome.htm?utm_source=chatgpt.com)
2. Community wrappers (SolidProxy / pySldWrap) and blog posts are the quickest way to see _how_ to translate those VB/C# calls into Python (how arrays/variants map, how to keep object refs, etc.). [GitHub+1](https://github.com/Gautreaux/SolidProxy?utm_source=chatgpt.com)
