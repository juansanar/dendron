---
id: 12yic01ebegapclq3yte51v
title: Spoiler Hover
desc: ''
updated: 1649138436403
created: 1649138436403
---
## Example for spoiler hover blockquote CSS class

```{css, echo=FALSE}
.spoiler {
  visibility: hidden;
}

.spoiler::before {
  visibility: visible;
  content: "Spoiler alert! Hover me to see the answer."
}

.spoiler:hover {
  visibility: visible;
}

.spoiler:hover::before {
  display: none;
}
```
## Uses

- HTML
- Rmarkdown
