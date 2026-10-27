# Compiler Design Labs

Compiler Design — Faculty of Computers and Information, Menoufia University

Teaching Assistant: Eng. Mohamed Shehab

## About the Project

This repository contains the lab work for the Compiler Design course. The project is divided into several parts, with each part covering a different stage of building a compiler.

| Lab | Topic |
|---|---|
| 01 | Lexer |
| 02 | Symbol Table |
| 03 | Grammar |
| 04 | Parser |
| 05 | Intermediate Code (Atoms) |
| 06 | Execution |

Currently, Lab 01 (Lexer) is available in this repository. The other parts will be added as the course progresses.

## Requirements

- JDK 21
- JavaCC (`javacc.jar` is included in the project root)

Download the JDK from [Adoptium](https://adoptium.net/).

After installing it, open a new terminal and check that Java is available:

```bash
java -version
javac -version
```

## Running the Lexer

Navigate to the lexer folder:

```bash
cd 01-lexer
```

On macOS or Linux, run:

```bash
chmod +x run.sh
./run.sh
```

The script generates the Java files, compiles them, and runs the lexer on `test.txt`.

## Files

Inside `01-lexer`:

- `Lexer.jj` — contains the lexer rules written in JavaCC.
- `test.txt` — the input file used for testing.
- `run.sh` — runs the lexer on macOS and Linux.
- `build/` — contains the generated files and compiled classes.

The project may also include `run.bat` for Windows.

## Testing

The lexer reads Java code from `test.txt` and identifies tokens based on the rules defined in `Lexer.jj`.

For example:

```java
int x = 42;
float rate = 3.14;
String msg = "Hello World";
```

You can change the input file to test different cases, then run the script again.

## How It Works

The script runs these commands:

```bash
java -cp ../javacc.jar javacc -OUTPUT_DIRECTORY=build Lexer.jj
javac -d build build/*.java
java -cp build Lexer test.txt
```

1. JavaCC reads `Lexer.jj` and generates Java source files.
2. `javac` compiles the generated files.
3. Java runs the lexer using `test.txt` as input.

## Notes

- Make changes to `Lexer.jj`, not the generated files inside `build/`.
- Use `test.txt` to check your lexer rules.
- Follow the instructions for each lab when preparing submissions.
- Check the requirements for each lab, as the submission files may differ.

