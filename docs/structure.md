# Directory Structure

GitBook uses a simple directory structure. All Markdown/Asciidoc files listed in the [SUMMARY](pages.md) will be transformed as HTML. Multi-Lingual books have a slightly [different structure](languages.md).

A basic GitBook usually looks something like this:

```text
.
├── book.json
├── README.md
├── SUMMARY.md
├── chapter-1/
|   ├── README.md
|   └── something.md
└── chapter-2/
    ├── README.md
    └── something.md
```

An overview of what each of these does:

| File | Description |
| :--- | :--- |
| `book.json` | Stores [configuration](config.md) data \(**optional**\) |
| `README.md` | Preface / Introduction for your book \(**required**\) |
| `SUMMARY.md` | Table of Contents \(See [Pages](pages.md)\) \(**optional**\) |
| `GLOSSARY.md` | Lexicon / List of terms to annotate \(See [Glossary](lexicon.md)\) \(**optional**\) |

## Static files and Images

A static file is a file that is not listed in the `SUMMARY.md`. All static files, unless [ignored](structure.md#ignore), are copied to the output.

## Ignoring files & folders <a id="ignore"></a>

GitBook will read the `.gitignore`, `.bookignore` and `.ignore` files to get a list of files and folders to skip. The format inside those files, follows the same convention as `.gitignore`:

```text
# This is a comment

# Ignore the file test.md
test.md

# Ignore everything in the directory "bin"
bin/*
```

## Project integration with subdirectory <a id="subdirectory"></a>

For software projects, you can use a subdirectory \(like `docs/`\) to store the book for the project's documentation. You can configure the [`root` option](config.md) to indicate the folder where GitBook can find the book's files:

```text
.
├── book.json
└── docs/
    ├── README.md
    └── SUMMARY.md
```

With `book.json` containing:

```text
{
    "root": "./docs"
}
```

