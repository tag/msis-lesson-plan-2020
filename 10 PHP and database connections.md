# Environment variables

* What are "environment variables"
  - The most common is PATH
  ```terminal
  # TAG: On windows, try just `path`?
  # Windows
  echo %Path%

  # Windows, since Windows 10 Insider Build 14971 (Powershell is now the default)
  $Env:Path

  # MacOS, Linux, Unix
  echo $PATH
  ```
* Add `env` to `.gitignore`
