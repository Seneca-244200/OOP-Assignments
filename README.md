# OOP244 Assignments

## Submission Policy and Instructions

Assignments are divided into two required parts: a coding part and a reflection.

A DIY section may also be provided at the end of an assignment. Complete the DIY section on your own for practice. DIY work is not submitted or marked unless your professor gives different instructions.

- Part 1, **Development (DEV)**: A step-by-step guided assignment worth 100% of the assignment mark.

> Part 1 is **not** meant to be started during your scheduled lab session. You should begin it on your own before your lab, then attend the scheduled lab session to seek assistance and complete your work if needed. To receive 100% of the mark, the coding part must be submitted during the lab session from a lab computer.

- Part 2, **Reflection**: A non-coding part submitted a few days later. The due date is set by your professor. The reflection does not add marks, but an insufficient reflection may result in a penalty of up to 40% of the whole assignment mark.

- **DIY**: A Do It Yourself practice section that is more open-ended. DIY work does not need to be submitted to your professor and is not marked. However, you may test your program using the automated submitter program, or ask your professor for help or feedback.

## Understanding Academic Integrity Violations

Please read the following document to understand what constitutes an academic integrity violation and to make sure your work follows Seneca Polytechnic's requirements:

[Seneca Polytechnic Academic Integrity Violation Policy](Academic_Integrity_Violations_Seneca.md)

## Due Dates

### Coding

Part 1 coding is due by the end of your scheduled lab session and must be submitted from one of the desktop computers in the lab to receive 100% of the mark. If you submit your code after the lab session but before midnight on the same day, you will receive 60% of the mark. No submissions are accepted after midnight.

> You must submit your code using an SSH terminal client logged into the Matrix cluster from one of the desktop computers in the lab. We recommend using [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). You must have only one active Matrix connection. Before logging into Matrix to submit your lab, make sure you are logged off all other terminal client sessions.

## Late Penalties

You may submit your assignment by midnight on the same day as your scheduled lab session with a 40% penalty. No submissions are accepted after midnight.

## Citation Policy

Every submitted source file must begin with a citation comment that includes:

- Your full name
- Seneca email address
- Seneca student ID
- Subject and section
- Dates of changes, debugging, and commits

**Assignments that include a submitted file without a citation will not be marked and will receive a grade of zero.**

> Do not copy and paste blindly. Read this policy, understand it, and update the citation in every submitted file so it accurately describes your work.

Citation is required whenever you receive permitted help or use permitted external material, but citation does **not** automatically make copied code or unauthorized collaboration acceptable. You may only use code, examples, or help that is allowed by your professor, the assignment instructions, and Seneca Polytechnic's academic integrity policy. If you are unsure whether something is allowed, ask your professor before using it.

---

### If the Code Is Entirely Yours

If the file contains only your own work and/or code provided by your professor, add the following statement:

> I have done all the coding by myself and only copied the code that my professor provided to complete my assignment.

---

### If the Code Includes Permitted External Help

If your professor or the assignment instructions allow you to use a specific kind of external help, and you use it, you must clearly state:

- Which part was not entirely your own
- Who provided the help, or the source it came from
- How the help was used

Also, in your `reflect.txt` file, list exactly what was added or changed, in which file, and where or from whom the help was received.

> Clearly citing permitted help allows your professor to evaluate your work accurately. It does not excuse unauthorized copying, sharing, or collaboration.

---

### If You Helped Someone

If you shared any part of your code with someone else, notify them of this policy. In your own `reflect.txt`, state:

- Which part of your code was shared
- The name of the recipient

> Sharing code may still be considered unauthorized collaboration unless your professor has allowed it. Citation records what happened, but it does not automatically make the sharing acceptable.

---

> **Important:** Assignments are not group work unless your professor explicitly states otherwise. Submitting identical or substantially similar work, or citing the work as a group effort when group work was not authorized, may result in academic integrity penalties. If your professor permits shared work in a specific situation, follow their instructions exactly.

---

### Citation Examples

### Code Done by You

> Replace each `?` with the proper value.

```cpp
/* Citation and Sources...
-----------------------------------------------------------
Assignment ??
Module: Whatever
Filename: Whatever.cpp
-----------------------------------------------------------
Author: John Doe
Student number: 999,999,999
Email: jdoe@myseneca.ca
Subject: ABC123NAA
-----------------------------------------------------------
Revision History
------- --------- ------------------------------------------
Version Date      Reason
V0.7    2025/?/?  Completing whatever
V0.8    2025/?/?  Debugged DMA
V0.9    2025/?/?  Asked professor for help with XYZ
V1.0    2025/?/?  Ready for submission
-----------------------------------------------------------
I have done all the coding by myself and only copied the code
that my professor provided to complete my work for function whatever.
-----------------------------------------------------------
*/
```

---

### Code Done with Permitted Help

```cpp
/* Citation and Sources...
-----------------------------------------------------------
Assignment ??
Module: Whatever
Filename: Whatever.cpp
-----------------------------------------------------------
Author: John Doe
Student number: 999,999,999
Email: jdoe@myseneca.ca
Subject: ABC123NAA
-----------------------------------------------------------
Revision History
------- --------- ------------------------------------------
Version Date      Reason
V0.7    2025/?/?  Completing whatever
V0.8    2025/?/?  Debugged DMA
V0.9    2025/?/?  Used permitted help from Jane Doe for function XYZ
V1.0    2025/?/?  Ready for submission
-----------------------------------------------------------
I have done all the work by myself except for function XYZ.
Function XYZ includes permitted help provided by Jane Doe.
This help is also described in reflect.txt.
-----------------------------------------------------------
*/
```

## Compiling and Testing Your Program

All your code should be compiled using this command on `matrix`:

```bash
g++ -Wall -std=c++11 -g -o prg file1.cpp file2.cpp ...
```

- `-Wall`: reports compiler warnings
- `-std=c++11`: compiles the code using the C++11 standard
- `-g`: includes debugging symbols so `valgrind` can provide more useful reports
- `-o prg`: names the compiled application `prg`

After compiling and testing your code, run your program as follows to check for possible memory leaks:

```bash
valgrind --show-error-list=yes --leak-check=full --show-leak-kinds=all --track-origins=yes ./prg
```

- `--show-error-list=yes`: shows the list of detected errors
- `--leak-check=full`: checks for all types of memory problems
- `--show-leak-kinds=all`: shows all types of memory leaks identified
- `--track-origins=yes`: tracks the origin of uninitialized values. The `g++` command must include the `-g` flag for this information to be meaningful.

To check your program output, use a program that compares text files. Search online for an appropriate program for your platform, or use `diff` on `matrix`.

> Note: All code written in assignments and the project must be implemented in the **seneca** namespace unless instructed otherwise.

## Submission

1. Commit and push your code to your GitHub repository.
2. SSH into Matrix.
3. Pull your work from GitHub to your Matrix account.
4. Follow the lab submission instructions to submit your work to your professor.

### Assignment Submission

```bash
~profname.proflastname/submit 2??/aX/dev_sss <ENTER>
```

- Replace **??** with your subject code (`00` or `44`).
- Replace **X** with the assignment number (`1` to `10`).
- Replace **sss** with the section (`naa`, `nbb`, `nra`, `zaa`, etc.).

### Reflection Submission

```bash
~profname.proflastname/submit 2??/aX/ref_sss <ENTER>
```

- Replace **??** with your subject code (`00` or `44`).
- Replace **X** with the assignment number (`1` to `10`).
- Replace **sss** with the section (`naa`, `nbb`, `nra`, `zaa`, etc.).

### DIY Testing Only

DIY work does not need to be submitted and is for practice only. However, if you want to test your solution, you may use the submit command as follows.

> This will not submit anything. It only tests your program.

```bash
~profname.proflastname/submit 2??/wX/diy_sss <ENTER>
```

- Replace **??** with your subject code (`00` or `44`).
- Replace **X** with the workshop number (`1` to `10`).
- Replace **sss** with the section (`naa`, `nbb`, `nra`, `zaa`, etc.).

### Custom Code Submission

If you have additional custom code, such as reusable functions or classes, save it in a module called `Utils` using the files `utils.cpp` and `utils.h`. Submit these files with your assignment using the following instructions.

To have your custom `Utils` module compiled with your assignment, add a **u** to the submission name of your assignment, such as **udev_sss** or **udiy_sss**.

Example:

```bash
~profname.proflastname/submit 2??/aX/udev_sss <ENTER>
~profname.proflastname/submit 2??/aX/udiy_sss <ENTER>
```

- Replace **??** with your subject code (`00` or `44`).
- Replace **X** with the assignment or workshop number (`1` to `10`).
- Replace **sss** with the section (`naa`, `nbb`, `nra`, `zaa`, etc.).

### Testing Your Assignment Before Submission Opens

You can test your code before submission opens, if your professor has made testing available, and after submission closes by using the `-feedback` option.

Example:

```bash
~profname.proflastname/submit 2??/aX/dev_sss -feedback <ENTER>
~profname.proflastname/submit 2??/aX/udev_sss -feedback <ENTER>
```

### Submission Options

To see all available submission options, issue the submit command with no arguments.

Example:

```bash
~profname.proflastname/submit <ENTER>
```

---

# Coding Style

You must follow a consistent and readable coding style throughout your assignment. This includes:

- Use a consistent number of spaces or tabs for indentation. Four spaces are recommended. The indentation size must remain uniform across your entire codebase.
- Use a consistent block style for opening and closing braces `{}`. You may choose any of the common styles below, but you must use the same style throughout your code.

### Common Brace Styles

**K&R Style (Kernighan and Ritchie) - Recommended**

Opening brace on the same line as the control statement or function declaration:

```cpp
int main() {
    if (condition) {
        doSomething();
    }
    else {
        doSomethingElse();
    }
}
```

**Allman Style**

Opening brace on a new line:

```cpp
int main()
{
    if (condition)
    {
        doSomething();
    }
    else
    {
        doSomethingElse();
    }
}
```

**Whitesmiths Style**

Opening brace is indented to align with the block:

```cpp
int main()
    {
    if (condition)
        {
        doSomething();
        }
    else
        {
        doSomethingElse();
        }
    }
```

---

### Naming Conventions

- **Structure and Class Names**

  Start with a capital letter and use CamelCase notation.

  Example: `ClassNameIsLikeThis`

- **Attributes (Structure and Class Member Variables)**

  Begin with `m_`, followed by a lowercase letter and then camelCase notation.

  Example: `m_memberVariableLikeThis`

- **Local Variables, Function Names, Parameters, and Others**

  Start with a lowercase letter and use camelCase notation. All names must be meaningful.

  Examples:

  - Variable: `orderCount`
  - Function: `calculateTotal()`
  - Parameter: `inputValue`
