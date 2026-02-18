# zip — Official Wyn Package

Read/write ZIP archives. Wraps miniz (single C file).

## Install

```bash
wyn pkg install github.com/wynlang/zip
```

## Usage

```wyn
var z = Zip_open("archive.zip")
var files = Zip_list(z)
var content = Zip_read(z, "readme.txt")
Zip_close(z)
```

No system dependency — miniz is bundled.
