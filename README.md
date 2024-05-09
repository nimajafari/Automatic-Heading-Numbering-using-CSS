# Automatic Heading Numbering in CSS
Using CSS to autonumbering heading elements


## Automatic heading numbering
Description


body.single-post{counter-reset:h1counter h2counter h3counter h4counter h5counter h6counter;}

.single-post h1 {counter-reset:h2counter;}
.single-post h2 {counter-reset:h3counter;}
.single-post h3 {counter-reset:h4counter;}
.single-post h4 {counter-reset:h5counter;}
.single-post h5 {counter-reset:h6counter;}
/* End Common */

## Automatic heading numbering without hierarchy
Description

```css
h2.h-num:before {
    counter-increment: h2counter;
    content: counter(h2counter) ".\0000a0\0000a0";
}
h3.h-num:before {
    counter-increment: h3counter;
    content: counter(h3counter) ".\0000a0\0000a0";
}
h4.h-num:before {
    counter-increment: h4counter;
    content: counter(h4counter) ".\0000a0\0000a0";
}
```

***

## Automatic heading numbering with hierarchy h2, h3, and h4
Description

```css
h2.h-num-234:before {
    counter-increment: h2counter;
    content: counter(h2counter) ".\0000a0\0000a0";
}

h3.h-num-234:before {
    counter-increment: h3counter;
    content: counter(h2counter) "." counter(h3counter) ".\0000a0\0000a0";
}

h4.h-num-234:before {
    counter-increment: h4counter;
    content: counter(h2counter) "." counter(h3counter) "." counter(h4counter) ".\0000a0\0000a0";
}
```

***

## Automatic heading numbering with hierarchy h3 and h4
Description

```css
h2.h-num-34:before {
    counter-increment: h2counter;
    content: counter(h2counter) ".\0000a0\0000a0";
}
h3.h-num-34:before {
    counter-increment: h3counter;
    content: counter(h3counter) ".\0000a0\0000a0";
}

h4.h-num-34:before {
    counter-increment: h4counter;
    content: counter(h3counter) "." counter(h4counter) ".\0000a0\0000a0";
}
```

***
