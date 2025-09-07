# Dependency Walker Installer for Nuitka

GitHub Actions composite action that automatically installs Dependency Walker to enable Nuitka's onefile and standalone modes on Windows.

## Why This Action?

Nuitka requires Dependency Walker (`depends.exe`) to analyze DLL dependencies when compiling Python applications in onefile or standalone mode on Windows. This action automatically downloads and installs Dependency Walker to the correct location where Nuitka expects to find it.

## Usage

Simply add this action before running Nuitka in your GitHub Actions workflow:

```yaml
- name: Install Dependency Walker for Nuitka
  uses: onesoftqwq/dependency-walker-installer@v1

- name: Compile with Nuitka
  run: |
    python -m nuitka --onefile --windows-icon-from-ico=icon.ico your_script.py
```

## Action Details

- **Download URL**: https://dependencywalker.com/depends22_x64.zip
- **Install Path**: `$env:USERPROFILE\AppData\Local\Nuitka\Nuitka\Cache\downloads\depends\x86_64`
- **Platform**: Windows only (requires Windows runner)

## Features

- ✅ Automatically creates the required directory structure
- ✅ Downloads the official Dependency Walker from dependencywalker.com
- ✅ Extracts to the exact location Nuitka expects
- ✅ Handles errors gracefully with proper error messages
- ✅ Cleans up temporary files after installation
- ✅ No configuration needed - just use it before Nuitka

## License

MIT
