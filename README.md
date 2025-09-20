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

---

## 🔹 Installation and build

1. **Clone the repository:**  

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
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

