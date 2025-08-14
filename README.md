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

| Platform | JDK Version | JavaFX Version | Status |
|----------|------------|---------------|--------|
| **Linux (x64)**   | 24 | 24.0.2 | ✅ Ready |
| **Windows (x64)** | 24 | 24.0.2 | 🚧 Coming Soon |
| **macOS (x64/arm64)** | 24 | 24.0.2 | 🚧 Coming Soon |

---

## Usage

### 1. Download the Runtime
Clone this repository or download the release for your OS:
```bash
git clone https://github.com/<your-username>/FxRuntime.git
