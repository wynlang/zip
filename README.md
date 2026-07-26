# zip - Official Wyn Package

ZIP archive utilities for Wyn: archive detection, size estimation, and
formatting. Pure Wyn, no system dependency. (Create/extract via C bindings is
future work.)

## Install

```bash
wyn pkg install github.com/wynlang/zip
```

## Usage

```wyn
import zip

// Archive detection
print(zip.zip_is_archive("backup.zip"))          // true
print(zip.zip_is_archive("backup.tar"))          // false

// Rough entry count estimate from archive size
print(zip.zip_entry_count_estimate(524288))      // 512

// Compression ratio as a percentage (compressed/original)
print(zip.zip_compression_ratio(1000, 250))      // 25

// Human-readable sizes
print(zip.zip_human_size(512))                   // 512 B
print(zip.zip_human_size(2560))                  // 2.5 KB
```

## API

| Function | Description |
|----------|-------------|
| `zip_is_archive(path)` | True if the path ends in `.zip` |
| `zip_entry_count_estimate(file_size)` | Rough entry count (1 per KB) |
| `zip_compression_ratio(original, compressed)` | Compressed size as % of original |
| `zip_human_size(bytes)` | Format bytes as `"N B"` / `"N.M KB"` |
