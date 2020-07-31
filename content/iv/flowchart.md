---
title: Instrumental Variables Flowchart
author: 'Last updated:'
date: '2020-07-30'
diagram: true
diagram_parallax: false
image_size: contain
---


Most of the nodes in the diagram below are clickable, which will take you to another page with much more detail on that specific issue. In practice, empirical work is not so linear, and there is typically a lot of recirculation among these steps. For example, you may have 2 endogenous variables and 4 instruments. You may find that 1 or 2 of those instruments are weak, and as you learn this information, you are constantly recirculating in stage 1. You may settle on 3 instruments that seem to work well. Then, in Stage 2, you may find that your results are very sensitive with those instruments, but less sensitive when relying on only 2 of those 3 instruments. So now you go back to step 1, evaluate just those 2 instruments, etc.

![](https://media.giphy.com/media/l0IylOPCNkiqOgMyA/giphy.gif)

The point is that empirical work in practice is messy. Ideally, we could set out our plan in advance and proceed accordingly, but there are some things we just can't know until we see the data. All we can do is work through the process in good faith, assessing the quality of our empirical work based on sound statistics and econometrics. Happy instrumenting!


{{< diagram >}}
graph TD;
    linkStyle default interpolate basis
    A(["Thinking of IV?"]) --> B(["How big is<br> the problem?"])
    B --> |"it's big"| C1(["Are your instruments<br> any good?"])
    B --> |"no biggie"| C2(["Nevermind:<br> I'll try something else"])
    subgraph one ["Stage 1: Requirements for any IV"]
    C1 --> D1(["first-stage"])
    C1 --> D2(["exogeneity"])
    C1 --> D3(["exclusion"])
    D1 --> E(["assess instruments"])
    D2 --> E
    D3 --> E
    end
    subgraph two ["Stage 2: Still not in the clear"]
    E --> |"lookin' good!"| E1(["How sensitive are<br> the results?"])
    E1 --> F1(["IV is biased!"])
    E1 --> F2(["what about outliers?"])
    F1 --> G(["assess sensitivity"])
    F2 --> G
    end
    E --> |"ouch, no bueno"| C2
    G --> |"um, define sensitive"| C2
    G --> |"not too bad!"| H(["Go forth and write<br> that appendix!"])
    click B "/iv/problem" "Pre-testing"
    click C2 "/" "Try something else"
    click H "https://davidcard.berkeley.edu/papers/card-dellavigna-pagelimits.pdf" "Page limits are non-binding."
{{< /diagram >}}


<script src="https://cdn.rawgit.com/knsv/mermaid/master/dist/mermaid.min.js"></script>
<link rel="stylesheet" href="https://cdn.rawgit.com/knsv/mermaid/master/dist/mermaid.css">