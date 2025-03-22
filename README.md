# 🔧 Custom PyTorch 2.6.0a0 (CUDA 12.8 + cuDNN 9.8)

This repository provides a custom-built PyTorch 2.6.0a0 package for Windows 11 with:

- ✅ CUDA 12.8 support  
- ✅ cuDNN 9.8 support  
- ✅ MSVC 14.38 (Visual Studio 2022)  
- ✅ Python 3.10.16 (Anaconda)  
- ✅ TorchExtensions compatibility patch

---

## ✅ Post-Build Test Checklist

| No. | Test Item                         | Result   | Note |
|-----|----------------------------------|----------|------|
| 1️⃣ | `import torch`, version check     | ✅ Passed | `2.6.0a0+git1eba9b3` |
| 2️⃣ | CUDA available                    | ✅ Passed | `torch.cuda.is_available()` → `True` |
| 3️⃣ | cuDNN version check              | ✅ Passed | `90800 (cuDNN 9.8)` |
| 4️⃣ | GPU info                         | ✅ Passed | RTX 5070 Ti |
| 5️⃣ | Basic ops test (Conv2D)         | ✅ Passed | Shape output checked |
| 6️⃣ | `torch.compile()` usage          | ⚠️ Failed | Triton not installed properly |
| 7️⃣ | C++ Extension (cpp_extension)    | ❌ Failed | `cl.exe` conflict / multiple definitions |
| 8️⃣ | `torch.distributed` available    | ✅ Passed | `dist.is_available()` → `True` |
| 9️⃣ | `init_process_group()` test     | ❌ Failed | `libuv` missing (USE_LIBUV=0) |
| 🔟 | AMP test (`autocast`)             | ✅ Passed | Mixed precision working |
| 1️⃣1️⃣ | TF32 check                      | ✅ Passed | TF32 config verified |
| 1️⃣2️⃣ | Inference benchmark (100x loop) | ✅ Passed | Fast speed confirmed |
| 1️⃣3️⃣ | Torch Compile speedup test      | ⚠️ Failed | Triton missing |

---

## 📦 Wheel File

The prebuilt `.whl` file is available under the **Releases** section.

> Compatible with:
> - Python 3.10.16
> - Windows 11 x64
> - CUDA 12.8
> - cuDNN 9.8

---

## ⚠️ Known Issues

- ❌ **C++ Extensions** are currently unavailable due to `cl.exe` conflicts.
- ⚠️ **Torch Compile** may not accelerate as expected because **Triton** is not fully functional in Windows builds.

---

## 🛠️ Maintenance Notice

This project was built as a one-time custom build for personal use.  
The author has less than 2 months of experience with coding and does **not plan to actively maintain or update** this repository.

Feel free to fork, customize, or rebuild it for your own purposes.

---

Thank you for visiting! 🚀
