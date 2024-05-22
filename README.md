# Automatic Heading Numbering in CSS
Using CSS to autonumbering heading elements


## Common styles for all scenarios on this page
For the first step, we need to reset all `COUNTERS`. In the example below, we reset all h1 to h6. We use `.single-post h1` to `.single-post h6` as selectors. You can use your selector according to the pages' styles you are working on.

```css
body.single-post{counter-reset:h1counter h2counter h3counter h4counter h5counter h6counter;}

.single-post h1 {counter-reset:h2counter;}
.single-post h2 {counter-reset:h3counter;}
.single-post h3 {counter-reset:h4counter;}
.single-post h4 {counter-reset:h5counter;}
.single-post h5 {counter-reset:h6counter;}
```

***

## Scenario 1: Automatic heading numbering without hierarchy
In this scenario, all h2, h3, and h4 headings with `class="h-num"` will have automatic numbering `WITHOUT` hierarchy.

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

## Scenario 2: Automatic heading numbering with hierarchy h2, h3, and h4
In this scenario, all h2, h3, and h4 headings with `class="h-num234"` will have automatic numbering `WITH` hierarchy.


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

## Scenario 3: Automatic heading numbering with hierarchy h3 and h4
In this scenario, all h3, and h4 headings with `class="h-num34"` will have automatic numbering `WITHOUT` hierarchy for h2 and h3, and have automatic numbering `WITH` hierarchy for h3 and h4.


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
