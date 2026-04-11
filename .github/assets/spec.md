# Specification of `lis`

The bold text in the following specification indicates the features that are unique to `lis` and not found in the traditional `ls` command.

- list the entries in the specified directory.
  If no directory is specified, the current directory is used.
- The output is sorted by name in ascending order in the default.
  By specifying `--sort` option and its argument, it can be sorted ascending by time, size, or extension.
  Also, by specifying `--reverse` option, the sort order can be reversed (descending).
- The output is displayed in columns by default.
  If `isatty` is false, the output is displayed in a single column.
- If the `-l`, or `--long` option is specified, the output is displayed in long format.
  The long format includes the following information for each entry:
  - File type and permissions
  - Number of hard links
  - Owner name
  - Group name
  - Size in bytes (by human-readable format)
  - Last modification time
  - **Git status (if the entry is tracked by Git)**
  - File name
- If the `-a`, or `--all` option is specified, all entries are listed, including hidden files (those starting with a dot), while respecting `.gitignore` (recursively search the parent directories).
  By specifying `-A`, or `—whole-all`, all hidden files are printed (does not respect `.gitignore`).
  By default, hidden files are not listed.
- `--icon` option is used to display icons for each entry.
  The icons are determined based on the file type and extension.
- `--format` option is used to specify the output format.
  The available formats are `plain`, `csv`, `json`, and `yaml`.
  The default format is `plain`.
- `--recursive` or `-R` option is used to list entries recursively.
  When this option is specified, the contents of all subdirectories are also listed.
- supporting `LS_COLORS` environment variable to colorize the output based on file types and extensions.
