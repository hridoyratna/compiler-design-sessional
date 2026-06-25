# 📚 Compiler Design Sessional

A collection of C++ programs covering core algorithms and concepts practiced during the Compiler Design Sessional course. Each algorithm is organized as a **separate project inside one shared Code::Blocks Workspace** to avoid build conflicts and enable independent debugging.

---

## 🗂️ Workspace Structure

```
CompilerDesign.workspace
│
├── BinarySearch/
│   └── main.cpp
│
├── SelectionSort/
│   ├──  main.cpp
│
├── MatrixMultiplication/
│   ├──  main.cpp
│
├── CheckComment/
│   ├──  main.cpp
|
|
|
└── ... (more projects)
```

Each folder is a **standalone Code::Blocks project** with its own `main()` function — zero conflicts, full debug support.

---

## 📋 Programs List

| # | Program | Description |
|---|---------|-------------|
| 1 | Binary Search | Search element in sorted array using O(log n) approach |
| 2 | Selection Sort | Sort array by repeatedly selecting the minimum element |
| 3 | Matrix Multiplication | Multiply two two-dimentional array |
| 4 | Check Comment | Check the string, it is a single line or multiple line comment |
| 5 | *(more coming)* | ... |

---

## 🛠️ Setup Guide — Separate Projects in One Workspace

This is the **recommended approach** for managing multiple C++ programs without `main()` conflicts.

### Step 1 — Create the First Project

1. Open **Code::Blocks**
2. Go to **File → New → Project**
3. Choose **Console Application** → Click **Go**
4. Select **C++** → Click **Next**
5. Set **Project Title** (e.g., `BinarySearch`)
6. Choose your folder path → Click **Finish**

This creates your first `.cbp` project file with a default `main.cpp`.

---

### Step 2 — Save as a Workspace

1. Go to **File → Save Workspace As**
2. Name it `CompilerDesign.workspace`
3. Save it in your **root project folder**

Now all future projects will be added to this single workspace.

---

### Step 3 — Add More Projects to the Same Workspace

For each new algorithm (e.g., SelectionSort):

1. Go to **File → New → Project**
2. Choose **Console Application** → **C++**
3. Give it a new name (e.g., `SelectionSort`)
4. Click **Finish**

It automatically gets added to the **existing workspace** — visible in the left panel under **Management → Projects**.

---

### Step 4 — Write Your Code

Each project has its own `main.cpp`. Write your algorithm code there with its own `main()` function — no conflicts since they are separate projects.

**Example — BinarySearch.cpp:**
```cpp
#include <iostream>
using namespace std;

int binarySearch(int arr[], int size, int target) {
    int left = 0, right = size - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return -1;
}

int main() {
    int arr[] = {2, 5, 8, 12, 16, 23, 38, 45};
    int size = sizeof(arr) / sizeof(arr[0]);
    int result = binarySearch(arr, size, 23);
    if (result != -1)
        cout << "Found at index: " << result << endl;
    else
        cout << "Not found!" << endl;
    return 0;
}
```

---

### Step 5 — Switch Between Projects

To run or debug a specific project:

1. In the **left panel (Management)**, find the project you want
2. **Right-click** on it → Select **"Set as Active Project"**
3. It becomes **bold** — now it's the active one
4. Press **F9** to build & run, or **F8** to debug

```
Management Panel
├── BinarySearch   ← (bold = active, will build & debug this one)
├── SelectionSort
├── MartrixMultiplication
└── CheckComment
```

---

### Step 6 — Debug a Project

1. Set the target project as active (Step 5)
2. Click on the **grey gutter** next to a line → Red dot (breakpoint) appears
3. Press **F8** to start debugging
4. Use these keys to step through:

| Key | Action |
|-----|--------|
| `F7` | Next line (Step Over) |
| `Shift+F7` | Step Into a function |
| `Ctrl+F7` | Step Out of a function |
| `F8` | Continue to next breakpoint |
| `Shift+F8` | Stop debugging |

5. Open **Debug → Debugging Windows → Watches** to monitor variable values live

---

## 🔄 Alternative Method — Exclude Files from Build

> This is a **quicker but manual** alternative when all files are inside **one single project**.

If you have `BinarySearch.cpp`, `SelectionSort.cpp`, and `MergeSort.cpp` all under one project, only **one** can be active at a time (only one `main()` allowed).

**How to exclude a file:**

1. In the **Management panel**, right-click the file you want to **exclude**
2. Click **Properties**
3. In the dialog, **uncheck both Debug and Release** targets
4. Click **OK**

The file stays in the project but is **skipped during compilation**.

**To switch to a different file:**

- Exclude the current active file the same way
- Then go to the new file → Properties → **check both Debug and Release** again

> ⚠️ **Downside:** You must manually exclude/include files every time you switch. It becomes tedious with many files. The **separate projects approach** above is much cleaner.

---

## 🚀 How to Clone and Use This Repo

```bash
# Clone the repository
git clone https://github.com/your-username/Compiler-Design-Sessional.git

# Open Code::Blocks
# File → Open → select CompilerDesign.workspace
# Right-click any project → Set as Active Project
# Press F8 to debug
```

---

## 💻 Requirements

- [Code::Blocks](https://www.codeblocks.org/downloads/) with **MinGW GCC compiler**
- C++11 or later
- Windows / Linux / macOS

---

## 👤 Author

**Hridoy Ratna**,
Department of Computer Science & Engineering,
Jamalpur Science & Technology University

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
