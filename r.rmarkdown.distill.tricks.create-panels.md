---
id: 5jvvc50l2m9s9l3wave6s45
title: Create Panels
desc: ''
updated: 1656914145913
created: 1656913961973
---
To create panels in distill projects/pages/posts use `panelset`


    ```{r panelset, echo=FALSE}
    xaringanExtra::use_panelset()
    ```

    ::::: {.panelset}

    ::: {.panel}

    ## Tab One {.panel-name}

    Amet enim aptent molestie vulputate pharetra
    vulputate primis et vivamus semper.

    :::

    ::: {.panel}

    ## Tab Two {.panel-name}

    ### Sub heading one

    Sit etiam malesuada arcu fusce ullamcorper
    interdum proin tincidunt curabitur felis?

    :::

    ::: {.panel}

    ## Tab Three {.panel-name}

    Adipiscing mauris egestas vitae pretium 
    ad dignissim dictumst platea!

    :::

    :::::

Sources: 
- https://github.com/rstudio/distill/issues/11#issuecomment-692142414
- https://github.com/rstudio/distill/issues/11