**JLECmd** is a command-line tool from Eric Zimmerman's suite, designed to parse Jump Lists for forensic purposes. Jump Lists store recently accessed files and apps in Windows, and analyzing them can reveal valuable evidence.

## Example questions:

**A text file was created in the Desktop folder. How many times was this file opened?**
**When was the text file from the previous question last modified? (MM/DD/YYYY HH:MM)**

### **Download and Extract**

1. Download **JLECmd** from [Eric Zimmerman's GitHub](https://github.com/EricZimmerman/).
2. Extract the downloaded `.zip` file to a folder (e.g., `C:\Tools\JLECmd`).

### **Prepare Input Files**

Jump Lists are located here:

- **Automatic Jump Lists**:
    
    `C:\Users\<Username>\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations`
    
- **Custom Jump Lists**:
    
    `C:\Users\<Username>\AppData\Roaming\Microsoft\Windows\Recent\CustomDestinations`
    

Copy these `.automaticDestinations-ms` and `.customDestinations-ms` files to a working directory.

---

### **Run JLECmd**

1. Open **Command Prompt** or **PowerShell**.
2. Navigate to the folder where `JLECmd.exe` is located:
    
    `cd C:\Tools\JLECmd`
    
3. Execute the tool with basic options:

    `JLECmd.exe -d "C:\Path\To\JumpLists" -o "C:\Path\To\Output"`
    
    - `-d` specifies the input directory containing Jump List files.
    - `-o` specifies the output directory for parsed results.

---

### **Analyze Output**

- **Output Format**:  
    The tool generates `.csv` files for each Jump List file.
- **Content**:
    - **Target Path**: Files or programs accessed.
    - **Timestamps**: Last accessed, created, or modified.
    - **App ID**: The application that created the Jump List.

---

### **Key Commands**

- Parse a single Jump List file:
    
    `JLECmd.exe -f "C:\Path\To\File.automaticDestinations-ms" -o "C:\Path\To\Output"`
    
- Include detailed JSON output:

    `JLECmd.exe -d "C:\Path\To\JumpLists" -o "C:\Path\To\Output" --json`
    
- Display help menu:

    `JLECmd.exe --help`