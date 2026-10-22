# Tinta 3.9.0 + Russian UI + deleted-file recovery

This custom build combines upstream 3.9.0 (9a6b209), Russian interface
translations and optional retention of deleted file tabs in memory.
The product version stays 3.9.0; the branch and package name identify the fork.

## Run

Use the portable tinta.exe supplied with this custom package.
No installer is required. The local package is generated in out/Tinta-custom-3.9.0/.
Existing out/Tinta/ files are not replaced.

Choose Settings → General → Language → Русский for Russian.
Enable Keep deleted files in memory in General before deleting a source file.
The option is off by default, uses extra RAM and saves no persistent viewer
cache. Close a tab or Tinta and its retained source is released.

If the original is deleted, Save / Ctrl+S opens Save As with the previous name
suggested. Confirm a destination to save, or cancel to keep editing.
Files that disappeared before being read cannot be recovered by this option.

## Validation

See tests/custom-build-validation.md for the checks performed on this combined build.
