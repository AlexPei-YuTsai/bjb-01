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
### 1.3 The World Wide Web
- Being an alumni of UCLA myself, I'm vaguely aware of the existence of ARPANET and the existence of the early internet in the 1960s.
- What I didn't know, however, was how the World Wide Web was, similar to Facebook, initially a smaller project deployed for the use of the local population.
  - Seems that the earliest projects of the company responsible for Java involved HotJava, a graphical browser for the WWW environment. HotJava didn't really take off, but the Java programming language did as Netscape implemented support for Java applets in WWW pages. Incidentally, HotJava is also fully written in Java.
  - Applet: Small bits of code (generally utility functions) to be embedded in larger applications. Similar to code libraries in that sense, perhaps. In terms of Java applets, it seems that these bits of code are small front-end modules that are portable and compatible on different machines.
- The point is, Java has a storied past and is greatly involved with the development and growth of the internet.

### 1.4 Introducing the Java Programming Language
- a

### 1.5 The Function "main"
- a

### 1.6 Method Calls
- a

### 1.7 A Word about Code Format
- a

## Book Notes
This section covers the notes I took for the first chapter of Herbert Schildt's [Java - A Beginner's Guide Ninth Edition](https://www.amazon.com/Java-Beginners-Guide-Herbert-Schildt/dp/1260463559), which covers an overview of Java, Object-Oriented Programming, the Java Development Kit, and the fundamentals of programming in Java. This book covers Java up to JDK 17 (Current version as of the writing of this README is Java SE 22), so hopefully the information I have here doesn't become outdated or deprecated too quickly.
### Java Origins
### Object-Oriented Programming (OOP)
### Installing Java For Real
- In order to compile and run Java stuff, you need a Java Development Kit (JDK). Following the guide this book provides, I downloaded JDK and Java SE 22 as that was the latest release at the time of accessing the [official Oracle Java Downloads page](https://www.oracle.com/java/technologies/downloads/#jdk22-windows) (I did look at the [archives](https://www.oracle.com/java/technologies/javase/jdk21-archive-downloads.html) for 17 and 21, but Oracle recommended against using older versions. The code in this book should still apply, though. Side note, I don't remember when I downloaded JDK 17, but hey version fidelity).
  - I downloaded the x64 MSI installer and allowed JDK to do its thing, following the [instructions here](https://docs.oracle.com/en/java/javase/22/install/installation-jdk-microsoft-windows-platforms.html#GUID-772189CD-74DA-448C-A693-E94FE5F83545) and letting the installation wizard handle what it needs to handle. Seems like it also handled all the binaries, so that's something I don't have to worry about.
  - ![A screenshot of me running --version on my terminal to confirm that, yes, I do indeed have JDK installed](https://github.com/user-attachments/assets/e85aeb60-a4e9-4533-ad26-b7236cfba3ae)
  - The `java` interpreter/application launcher and `javac` compiler as well as another other programs can be found in the `"C:\Program Files\Common Files\Oracle\Java"` path or the `"C:\Program Files\Java\jdk-22\bin"` path. Seems straightforward enough.
  - I also followed [Mosh's Java Tutorial](https://www.youtube.com/watch?v=eIrMbAQSU34) to make sure that I can edit and compile Java code on my machine.
- I personally have more experience doing stuff in VSCode. However, instead of downloading a bunch of plugins for Java development, it seemed more like standard practice to get a proper Java IDE like IntelliJ or NetBeans.
  - As I followed Mosh's tutorial, I downloaded and will be using [the community build of IntelliJ](https://www.jetbrains.com/idea/download/?section=windows) for the duration of this course. Don't forget to restart your machine after adding the necessary `bin` paths.
    - For the setup of IntelliJ, I checked the boxes that allowed it to update my context menu and PATH variables.
    - No other plugins are used, though I might've checked the box that allowed IntelliJ to copy my VSCode settings. Either way, I intend to play with vanilla Java and *an* IDE.
### Hello World'ing in Java
![A screenshot of the default code generated in IntelliJ when you first start a new Java project](https://github.com/user-attachments/assets/2f936e81-03c4-400f-878e-64926d52e8ff)
- Files can be run both inside the IntelliJ IDE or with `java [fileNamehere].java` on your command line interface.



