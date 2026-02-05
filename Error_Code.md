## 🧠 Linux / Shell Exit Codes – Quick Reference

Exit codes are numeric values returned by commands, scripts, or programs to indicate **how a process ended**.
Understanding them is critical for **shell scripting, CI/CD pipelines, debugging, and production monitoring**.

### 🔢 Common Exit Codes

|  Code | Meaning                        | When You’ll See It                                             |
| ----: | ------------------------------ | -------------------------------------------------------------- |
|   `0` | **Success**                    | Command executed successfully with no errors                   |
|   `1` | **General Error**              | Generic failure (logic error, missing file, invalid operation) |
|   `2` | **Misuse of shell builtins**   | Incorrect syntax or invalid shell command usage                |
| `126` | **Command cannot execute**     | File exists but lacks execute permission                       |
| `127` | **Command not found**          | Command doesn’t exist or is not in `$PATH`                     |
| `128` | **Invalid exit argument**      | Exit code outside valid range                                  |
| `130` | **Terminated by Ctrl+C**       | Process interrupted by user (`SIGINT`)                         |
| `137` | **Killed (SIGKILL / OOM)**     | Process force-killed (often due to Out Of Memory)              |
| `139` | **Segmentation fault**         | Program tried to access invalid memory (`SIGSEGV`)             |
| `255` | **Fatal error / Out of range** | Application-defined critical failure                           |

---

### ⚙️ Why Exit Codes Matter

* **Shell scripting** → Conditional logic (`if`, `&&`, `||`)
* **CI/CD pipelines** → Job success/failure detection
* **Docker & Kubernetes** → Container restart behavior
* **Production debugging** → Faster root cause analysis

---

### 🔍 Check the Exit Code of the Last Command

```bash
echo $?
```

Example:

```bash
ls /not-exist
echo $?   # Output: 2
```

---

### 🛠️ Real-World DevOps Insight

* `127` → PATH issues in Docker images
* `137` → Container killed due to memory limits
* `130` → Interrupted Jenkins job
* `126` → Script copied without `chmod +x`

---

### 📌 Pro Tip

> Exit codes **128 + signal number** usually indicate termination by a Unix signal
> Example:
> `137 = 128 + 9 (SIGKILL)`

---
