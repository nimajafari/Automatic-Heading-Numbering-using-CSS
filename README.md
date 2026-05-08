
# Automatic Heading Numbering using CSS

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Status](https://img.shields.io/badge/status-active-brightgreen)

Easily add automatic numbering to your HTML heading elements (h1–h6) using only CSS. No JavaScript required! This project demonstrates several CSS-only techniques for autonumbering headings, with and without hierarchy.

---

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Features

- Pure CSS solution for heading numbering
- Supports hierarchical and non-hierarchical numbering
- Works with h1–h6 elements
- No JavaScript or external dependencies

---

## Installation

Copy the relevant CSS snippets from the examples below into your stylesheet. Adjust selectors as needed for your project.

---

## Usage

### 1. Common Styles (Resetting Counters)

Reset all heading counters at the start of your content. Adjust selectors as needed:

```css
body.single-post {
    counter-reset: h1counter h2counter h3counter h4counter h5counter h6counter;
}
.single-post h1 { counter-reset: h2counter; }
.single-post h2 { counter-reset: h3counter; }
.single-post h3 { counter-reset: h4counter; }
.single-post h4 { counter-reset: h5counter; }
.single-post h5 { counter-reset: h6counter; }
```

---

### 2. Numbering Scenarios

#### Scenario 1: Numbering Without Hierarchy
All h2, h3, and h4 headings with `class="h-num"` will have automatic numbering **without** hierarchy.

```css
h2.h-num:before {
    counter-increment: h2counter;
    content: counter(h2counter) ".\00a0\00a0";
}
h3.h-num:before {
    counter-increment: h3counter;
    content: counter(h3counter) ".\00a0\00a0";
}
h4.h-num:before {
    counter-increment: h4counter;
    content: counter(h4counter) ".\00a0\00a0";
}
```

#### Scenario 2: Numbering With Hierarchy (h2, h3, h4)
All h2, h3, and h4 headings with `class="h-num-234"` will have automatic numbering **with** hierarchy.

```css
h2.h-num-234:before {
    counter-increment: h2counter;
    content: counter(h2counter) ".\00a0\00a0";
}
h3.h-num-234:before {
    counter-increment: h3counter;
    content: counter(h2counter) "." counter(h3counter) ".\00a0\00a0";
}
h4.h-num-234:before {
    counter-increment: h4counter;
    content: counter(h2counter) "." counter(h3counter) "." counter(h4counter) ".\00a0\00a0";
}
```

#### Scenario 3: Numbering With Hierarchy (h3, h4)
All h3 and h4 headings with `class="h-num-34"` will have automatic numbering **without** hierarchy for h2 and h3, and **with** hierarchy for h3 and h4.

```css
h2.h-num-34:before {
    counter-increment: h2counter;
    content: counter(h2counter) ".\00a0\00a0";
}
h3.h-num-34:before {
    counter-increment: h3counter;
    content: counter(h3counter) ".\00a0\00a0";
}
h4.h-num-34:before {
    counter-increment: h4counter;
    content: counter(h3counter) "." counter(h4counter) ".\00a0\00a0";
}
```

---

## Examples

See the code snippets above for usage. You can also add screenshots or a live demo link here.

---

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for improvements or bug fixes.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Contact

Created by [Your Name]. For questions, open an issue or contact me via GitHub.
