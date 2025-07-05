---
title: "Language Conversion with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 3.5.3. </b> "
---

Amazon Q Developer can help you modernize legacy code by converting it from one programming language to another. This is especially useful for migrating from older languages (like COBOL) to modern languages (like Python, Java, or C#).

#### Example: Convert from COBOL

**Step 1:** Create a new file called `program.cbl` in VSCode and paste in your COBOL code.

```cobol
       IDENTIFICATION DIVISION.
       PROGRAM-ID. HELLO.
       PROCEDURE DIVISION.
           DISPLAY 'Hello, world!'.
           STOP RUN.
```

**Step 2:** Highlight the COBOL code, right-click, and choose `Amazon Q Developer > Convert Language`.

**Step 3:** Review the generated code in your target language (e.g., Python, Java, C#).

#### Best Practices
- Review and test the converted code for correctness
- Refactor as needed to follow modern coding standards
- Update documentation to reflect the new language
