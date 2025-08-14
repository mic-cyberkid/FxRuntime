# FxRuntime

Custom, self-contained JavaFX runtimes for running JavaFX applications without requiring a full JDK installation.

## Overview

**FxRuntime** provides prebuilt Java runtimes that bundle:
- The full Java Development Kit (JDK)
- All JavaFX modules (JavaFX SDK & JMODs)
- Ready-to-run `bin/java` executable
- Optimized size (stripped debug info, man pages, and headers)

These runtimes are created with [`jlink`](https://docs.oracle.com/en/java/javase/21/core/jlink.html), ensuring they are portable and only include the modules needed to run JavaFX applications.

---

## Available Platforms

| Platform | JDK Version | JavaFX Version | Status | Link |
|----------|------------|---------------|--------|-----------|
| **Linux (x64)**   | 24 | 24.0.2 | ✅ Ready | [`Download`](https://drive.google.com/file/d/1QldcFL9CoiUBJBR6DVIlTCrFXLQ_eXA_/view?usp=drivesdk)|
| **Windows (x64)** | 24 | 24.0.2 | 🚧 Coming Soon | Coming soon|
| **macOS (x64/arm64)** | 24 | 24.0.2 | 🚧 Coming Soon | Coming soon|

---

## Usage

### 1. Download the Runtime
Clone this repository or download the release for your OS:
```bash
git clone https://github.com/mic-cyberkid/FxRuntime.git
```


### 2. Run a JavaFX Application

**Linux example:**

```bash
cd javafx-runtime-24-linux
./bin/java --module-path lib --add-modules ALL-MODULE-PATH -jar /path/to/YourJavaFXApp.jar
```

If your application is modular, adjust `--module-path` and `--add-modules` accordingly.

---

## How It’s Built

The runtimes are built in Google Colab using:

1. **Download JDK 24 (Linux/Windows/macOS)**
2. **Download JavaFX SDK & JMODs 24.0.2**
3. Use `jlink` to merge both:

   ```bash
   $JAVA_HOME/bin/jlink \
     --module-path $JAVA_HOME/jmods:/path/to/javafx-jmods \
     --add-modules ALL-MODULE-PATH \
     --output javafx-runtime-24-linux \
     --strip-debug \
     --compress=2 \
     --no-header-files \
     --no-man-pages
   ```

---

## License

These runtimes are built from:

* [OpenJDK](https://jdk.java.net/) — GPLv2 with Classpath Exception
* [OpenJFX](https://openjfx.io/) — GPLv2 with Classpath Exception

This repository only packages official builds without modifications.

---

## Roadmap

* [x] Linux runtime build (Java 24 + JavaFX 24.0.2)
* [ ] Windows runtime build
* [ ] macOS runtime build
* [ ] CI/CD to auto-build new versions

---
