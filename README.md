# Dump Lexical Extents of Class Definitions(LLVM/Clang) 🖥️

![LLVM Logo](https://llvm.org/favicon.ico)

**Extract C++ class boundaries automatically using Clang/LLVM.**

---

## 🔹 Overview

This project extends the **Clang/LLVM frontend** to extract **C++ class lexical extents**, enabling developers and researchers to analyze class boundaries in source code efficiently.  

**Key Features:**

- Integrates `-fdump-class-extents` for dumping class extents  
- Implements **AST traversal** for precise lexical extraction  
- Supports automated code analysis pipelines  

---

## 🔹 Features

- Extracts start and end lines of C++ classes  
- Compatible with modern C++ standards  
- Outputs in readable format for further tooling  
- Lightweight and easy to integrate  
<img width="708" height="354" alt="Image" src="https://github.com/user-attachments/assets/d27052b3-5dff-4530-bf5e-5adae8afb1eb" />

## 🔹 Installation and build

1. **Clone the repository:**  

```bash
https://github.com/llvm/llvm-project
```

2. **Install LLVM & Clang (Ubuntu):**  

```bash
sudo apt update
sudo apt install clang llvm
```

And similarly, for **Mac (Homebrew)**:  
3. **Install LLVM & Clang (Mac - Homebrew):**  

```bash
brew install llvm
```

And for **Build the project**:  
4. **Build the project:**  

```bash
mkdir build && cd build
cmake ..
make
```

## 🔹 Code Snippets

1. **AST Traversal Example:**  

```bash
for (const auto &D : ASTContext.getTranslationUnitDecl()->decls()) {
    if (const CXXRecordDecl *CXXDecl = dyn_cast<CXXRecordDecl>(D)) {
        llvm::outs() << "Class: " << CXXDecl->getNameAsString() << "\n";
        llvm::outs() << "Start Line: " << getStartLine(CXXDecl) << "\n";
        llvm::outs() << "End Line: " << getEndLine(CXXDecl) << "\n";
    }
}
```
## DumpClassExtents.cpp Source View
This screenshot shows the custom DumpClassExtents.cpp implementation inside Clang’s frontend, where class declaration ranges are extracted and printed with filename and line span.

<img width="1024" height="832" alt="Image" src="https://github.com/user-attachments/assets/3c1d1f0d-5711-405d-b06c-5ecb66c6dbc2" />

## DumpClassExtents.h Header File
This figure displays the declaration of the custom DumpClassExtentsAction, which extends Clang’s ASTFrontendAction 

<img width="1363" height="808" alt="Image" src="https://github.com/user-attachments/assets/21fee096-1923-44a6-9336-8e4c8f500d74" />

1. **Building Clang with CMake in WSL**
This screenshot shows the terminal command used to compile the modified Clang source using cmake --build . --target clang


```bash
cd llvm-project/build
cmake --build . --target clang
```






