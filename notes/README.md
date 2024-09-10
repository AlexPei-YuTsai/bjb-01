# Java Module 1 - Introduction to the Java Programming Language - NOTES

### Contents
- [Lecture Commentary Notes](#Lecture-Commentary-Notes)
- [Book Notes](#Book-Notes)
- [Additional Reading Notes](#Additional-Reading-Notes)

## Lecture Commentary Notes
### 1.1 Prologue
- Keys to a successful program:
  - Platform and version compatibility (e.g.: [Javascript implementation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map#browser_compatibility))
    - C code made to compile for Unix will not work for Windows. Therefore, extra effort and time is required to make that program compatible with other operating systems.
  - Crash-free implementation
    - Lack of robustness and bugs can sometimes cause real damage. For example, [Crowdstrike](https://en.wikipedia.org/wiki/2024_CrowdStrike_incident) suffered a bad, international multi-billion dollar crash because of bad pointer allocation.
    - Data loss can be permanent especially with pointer bugs in C and C++.
  - Sufficient security control
    - Programs may have unauthorized access to certain levels of the machine it's running on. Without proper restrictions, viruses and malware can easily jeopardize a user's safety.
- With all this trashtalking about C, this is where Java comes in.
### 1.2 Enter Oak
- Main programming problems: Portability, maintainability, safety, security.
- [Oak](https://en.wikipedia.org/wiki/Oak_(programming_language)) (What later becomes Java) and how it addresses each problem:
  - **Portability**:
    - C++ is dependent on the 8-bit ASCII character set, which becomes a problem when you need to handle hardware running locales outside of standard English. Oak uses UTF-16, which covers most human languages out there.
    - Oak code compiles not into hardware-specific machine code but instructions for a virtual machine. The same environment can somehow be simulated across platforms using different hardware and make Oak portable by making Oak code usable on all platforms via that virtual machine environment.
  - **Maintainability**:
    - Strong typing: Each given variable can only hold one kind of information so there's less data ambiguity and room for error in that regard.
    - Encapsulation: Functions don't do arbitrary, inappropriate tasks. Functions only work within the data defined in an object -> More predictable code with less side effects.
      - "C makes it easy to shoot yourself in the foot; C++ makes it harder, but when you do it blows your whole leg off," says the [creator of C++](https://www.stroustrup.com/quotes.html). The creator of Java advertised Java by saying that it's "C++ without guns or knives" and suggesting that it's harder for users of Java to hurt themselves.
  - **Safety**:
    - Though data referencing still seems to be possible, Java, unlike C++, [does not offer access to pointer arithmetic](https://www.oracle.com/java/technologies/simple-familiar.html) or references to specific memory addresses.
    - Other dangerous elements of C++ are also cleaned up with many language ambiguities cleaned up. Oak doesn't leave anything to be "implementation dependent" or "undefined", in contrast with C and C++.
  - **Security**:
    - The Oak virtual machine can also be edited to restrict program access to certain levels of your computer. For example, the access code to your computer's hard disk or network card can be replaced with an error message to veto any dangerous code you're not comfortable running. Custom permissions can also be configured on a case-by-base basis with the right implementation.
    - Java also does a lot of checks to make sure users don't screw themselves over.

## Book Notes


## Additional Reading Notes

