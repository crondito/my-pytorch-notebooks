### **Multimedia Engineering**  
#### **2. Introduction to Python Programming**  

---

### **Slide Contents**  
#### **Part 1: Python Programming Basics**  
- Syntax and simple programming exercises.  
#### **Part 2: Useful Python Modules/Libraries**  
- Introduction and practical use of key modules.  
#### **Part 3: Data Science Basics**  
- Processing Excel files and performing simple statistical operations.  

---

### **Python Programming Basics**  
#### **Features of Python**  
- **Scripting Language**: No compilation needed (unlike C/C++).  
- **Interactive**: Runs line-by-line, ideal for learning.  
- **Easy to Understand**: No explicit type declarations, simple syntax.  
- **Object-Oriented**: Supports classes and objects.  
- **Rich Libraries**: Extensive modules for math, science, and more (e.g., NumPy for matrix operations).  
- **Versatile**: Used in research, education, web development (e.g., YouTube, Instagram), and hardware control (e.g., Raspberry Pi).  

#### **Python Environments**  
1. **Local Installation**:  
   - Works on Windows, macOS, Linux.  
   - Tutorial: [Python Installation Guide for Windows](https://www.youtube.com/watch?v=Cs7friXdqdM).  
2. **Cloud Services (Recommended for this course)**:  
   - **Google Colaboratory**: Browser-based, no setup required.  
     - Access: [Colab](https://colab.research.google.com/).  

#### **Executing Python Code**  
1. **Script Files**: Save as `.py` and run via command line.  
2. **Interactive Shell**: Execute line-by-line.  
3. **Jupyter Notebook**: Block-wise execution (used in Colab).  

---

### **Google Colab Setup**  
1. **Connect to Runtime**:  
   - Automatic by default.  
   - Enable GPU for heavy computations: `Runtime` → `Change runtime type` → Select `GPU`.  
2. **Coding**:  
   - Write code in "Code Cells" and execute.  
3. **File Handling**:  
   - Upload files via the sidebar or mount Google Drive for persistent storage.  

#### **Colab Tips**  
- Sessions disconnect after inactivity. Save code frequently!  
- Maximum runtime: ~12 hours (shorter for free users).  

---

### **Python Syntax Basics**  
#### **Hello World**  
```python
print('Hello, Python!')  # Single or double quotes work.
```

#### **PEP 8 Coding Standards**  
- Follow [PEP 8](https://www.python.org/dev/peps/pep-0008/) for readability.  
- Use UTF-8 encoding (default on macOS/Linux; set explicitly on Windows).  

#### **Comments**  
```python
# Single-line comment.  
"""
Multi-line comment (docstring).
"""
```

#### **Indentation**  
- Python uses indentation (4 spaces) instead of braces (`{}`).  
- Example:  
  ```python
  for i in range(10):
      if i % 2 == 0:
          print(f'{i}: Even')
      else:
          print(f'{i}: Odd')
  ```

---

### **Variables and Data Types**  
- **Dynamic Typing**: No explicit type declarations.  
  ```python
  a = 10          # Integer  
  b = 3.14        # Float  
  c = 'Hello'     # String  
  ```
- **Type Conversion**:  
  ```python
  int(3.6) → 3  
  str(5) → '5'  
  ```

#### **Lists**  
- Flexible arrays with mixed data types.  
  ```python
  my_list = [1, 'apple', 3.14]  
  my_list.append(10)      # Add element.  
  my_list[0]             # Access first element (index 0).  
  ```

#### **Tuples**  
- Immutable lists.  
  ```python
  my_tuple = (1, 'apple', 3.14)  
  ```

#### **Dictionaries**  
- Key-value pairs.  
  ```python
  my_dict = {'apple': 5, 'banana': 3}  
  my_dict['orange'] = 1  # Add new key-value pair.  
  ```

---

### **Control Structures**  
#### **Loops**  
- `for` Loop:  
  ```python
  for i in range(5):  # 0 to 4.
      print(i)
  ```
- `while` Loop:  
  ```python
  while condition:
      # Code block.
  ```

#### **Conditionals**  
```python
if x > 0:
    print("Positive")
elif x == 0:
    print("Zero")
else:
    print("Negative")
```

#### **Ternary Operator**  
```python
result = 'Even' if x % 2 == 0 else 'Odd'
```

---

### **Functions**  
```python
def greet(name="World"):
    return f"Hello, {name}!"

print(greet("Alice"))  # Output: Hello, Alice!
```

#### **Main Function**  
```python
if __name__ == '__main__':
    main()  # Ensures code runs only when executed directly.
```

---

### **File Handling**  
#### **Reading Files**  
```python
with open('data.txt', 'r') as f:
    lines = f.readlines()  # List of lines.
```

#### **Writing Files**  
```python
with open('output.txt', 'w') as f:
    f.write("Hello, Python!")
```

---

### **Modules and Libraries**  
#### **Common Modules**  
- **NumPy**: Numerical operations (e.g., `np.array([1, 2, 3])`).  
- **Matplotlib**: Plotting graphs.  
- **Pandas**: Data analysis (e.g., Excel processing).  

#### **Installing Modules**  
```python
!pip install numpy  # In Colab.
```

---

### **Exercises**  
1. **Sum of Numbers**: Calculate `1 + 2 + ... + N` using `input()`.  
2. **Bank Account Class**: Implement `deposit()`, `withdraw()`, and `get_balance()`.  
3. **Word Frequency**: Count top 10 words in `words.txt`.  
4. **Matrix Operations**: Compute mean, standard deviation, and inverse of a 4x4 matrix.  
5. **Data Visualization**: Plot Nikkei 225 trends from `nikkei.xlsx`.  

---

### **Key Takeaways**  
- Python is versatile for AI, data science, and automation.  
- Practice with Colab and local environments.  
- Master basics before diving into advanced topics like deep learning.  
