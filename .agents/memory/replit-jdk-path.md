---
name: JDK after Replit config changes
description: Keep Java system packages available after Replit configuration updates.
---

When `.replit` is replaced through configuration validation, a previously installed JDK may disappear from the active shell `PATH` even though its Nix store package remains. Reapply the Java system dependency after the final `.replit` update, then verify both `java` and `javac`.

**Why:** In this project, the Java binaries vanished from the shell after a `.replit` replacement and returned after reinstalling the system dependency.

**How to apply:** If toolchain setup and `.replit` updates happen in the same task, install system dependencies after the last `.replit` update and run the version checks again.
