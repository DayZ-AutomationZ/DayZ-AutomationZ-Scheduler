# Install Python on Windows, macOS, Linux, and Android (Termux)


> Goal: Install **Python 3**, verify it works, and create an isolated project environment with `venv`.

---

## Quick verify (all platforms)

After installation, run:

```bash
python --version
```

If that fails, try:

```bash
python3 --version
```

Also verify `pip`:

```bash
python -m pip --version
```

---

## Windows (10/11)

### Option A — Official installer (recommended)
1. Download Python from the official site: https://www.python.org/downloads/windows/
2. Run the installer.
3. **IMPORTANT:** On the first screen, tick:
   - ✅ **Add python.exe to PATH**
4. Choose:
   - **Install Now** (fine for most users), or
   - **Customize installation** if you want to change install location.

### Verify
Open **PowerShell** (or CMD) and run:

```powershell
python --version
py --version
python -m pip --version
```

> Tip: Windows often includes the `py` launcher. `py -3` forces Python 3.

### Create a virtual environment (venv)
Inside your project folder:

```powershell
python -m venv .venv
.venv\Scripts\activate
python -m pip install --upgrade pip
```

Deactivate:

```powershell
deactivate
```

### Common Windows fixes
- **“Python was not found; run without arguments…”**
  - You installed from Microsoft Store or PATH isn’t set.
  - Fix: reinstall from python.org and check **Add to PATH**, or run with `py`.
- **PATH not updated**
  - Close and reopen terminal, or reboot.

---

## macOS

### Option A — Homebrew (recommended)
1. Install Homebrew (if you don’t have it): https://brew.sh/
2. Install Python:

```bash
brew update
brew install python
```

### Verify
```bash
python3 --version
python3 -m pip --version
```

### Create a virtual environment (venv)
```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
```

Deactivate:
```bash
deactivate
```

### Option B — Official python.org installer
1. Download macOS installer: https://www.python.org/downloads/macos/
2. Run the `.pkg` installer.
3. Verify with `python3 --version`.

> Note: macOS may already ship with an older system Python. Prefer Homebrew or python.org and use `python3`.

---

## Linux (Ubuntu / Debian)

### Install via APT
```bash
sudo apt update
sudo apt install -y python3 python3-pip python3-venv
```

### Verify
```bash
python3 --version
python3 -m pip --version
```

### Create a virtual environment (venv)
```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
```

Deactivate:
```bash
deactivate
```

---

## Linux (Fedora)

```bash
sudo dnf install -y python3 python3-pip python3-virtualenv
python3 --version
```

For `venv`, many Fedora setups use:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

---

## Linux (Arch)

```bash
sudo pacman -Syu python python-pip
python --version
```

Create venv:
```bash
python -m venv .venv
source .venv/bin/activate
```

---

## Android (Termux)

### Install Termux
- Install **Termux** from **F-Droid** (recommended): https://f-droid.org/packages/com.termux/
  - The Play Store Termux version is often outdated.

### Install Python in Termux
Open Termux and run:

```bash
pkg update -y
pkg upgrade -y
pkg install -y python
python --version
python -m pip --version
```

### Virtual environment (venv) in Termux
```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
```

> Tip: Some Android storage locations need permission. To access shared storage:
```bash
termux-setup-storage
```

---

## Optional: IDEs / Editors

- **VS Code**: https://code.visualstudio.com/
  - Install the **Python** extension in VS Code.
- **PyCharm**: https://www.jetbrains.com/pycharm/

---

## Troubleshooting

### “pip: command not found”
Use pip via Python:

```bash
python -m pip install <package>
```

On macOS/Linux you may need `python3 -m pip ...`.

### “Permission denied” installing packages (Linux/macOS)
Use a virtual environment (`venv`) instead of system-wide installs.

### Multiple Python versions
- Prefer `python3` (macOS/Linux)
- On Windows use `py -3` if needed

---

## License / Usage
Use this README freely in your repo. No attribution required.

