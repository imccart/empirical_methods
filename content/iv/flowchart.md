---
title: Instrumental Variables Flowchart
date: '2020-07-30'
diagram: true
diagram_parallax: yes
image_size: contain
---


Most of the nodes in the diagram below are clickable, which will take you to another page with much more detail on that specific issue. In practice, empirical work is not so linear, and there is typically a lot of recirculation among these steps. For example, you may have 2 endogenous variables and 4 instruments. You may find that 1 or 2 of those instruments are weak, and as you learn this information, you are constantly recirculating in stage 1. You may settle on 3 instruments that seem to work well. Then, in Stage 2, you may find that your results are very sensitive with those instruments, but less sensitive when relying on only 2 of those 3 instruments. So now you go back to step 1, evaluate just those 2 instruments, etc.

![](https://media.giphy.com/media/l0IylOPCNkiqOgMyA/giphy.gif)

The point is that empirical work in practice is messy. Ideally, we could set out our plan in advance and proceed accordingly, but there are some things we just can't know until we see the data. All we can do is work through the process in good faith, assessing the quality of our empirical work based on sound statistics and econometrics. 

One final note. If you're accessing this on an android mobile device, the flowcharts are going to look a little odd (probably huge). This is a known issue in rendering these types of diagrams. See this closed [issue on GitHub](https://github.com/mermaid-js/mermaid/issues/816) and these unanswered [posts on StackOverflow](https://stackoverflow.com/search?q=%5Bmermaid%5D+chrome). If anyone has any suggestions for how to have this render on an android mobile browser, please let me know. Otherwise, happy instrumenting!


{{< diagram >}}
graph TD;
    linkStyle default interpolate basis
    A(["Thinking of IV?"]) --> B(["How big is<br> the problem?"])
    B --> |"it's big"| C1(["Are your instruments<br> any good?"])
    B --> |"no biggie"| C2(["Nevermind:<br> try something else"])
    subgraph one ["Stage 1: Requirements for any IV"]
    C1 --> D1(["first-stage"])
    C1 --> D2(["exogeneity"])
    C1 --> D3(["exclusion"])
    D1 --> E(["assess instruments"])
    D2 --> E
    D3 --> E
    end
    subgraph two ["Stage 1b: Something is better than nothing"]
    E --> |"kind of ok"| e1(["Some violations"])
    e1 --> f1(["first-stage"])
    e1 --> f2(["exogeneity"])
    e1 --> f3(["exclusion"])
    f1 --> g(["pick something"])
    f2 --> g
    f3 --> g
    end
    subgraph three ["Stage 2: Still not in the clear"]
    E --> |"so far so good!"| E1(["How sensitive are<br> the results?"])
    g --> E1
    E1 --> F1(["IV is biased!"])
    E1 --> F2(["what about outliers?"])
    F1 --> G(["assess sensitivity"])
    F2 --> G
    end
    E --> |"ouch, no bueno"| C2
    G --> |"um, define sensitive"| C2
    G --> |"not too bad!"| H(["What am I<br> estimating, again?"])
    H --> |"can I be done?"| I(["Go forth and write<br> that appendix!"])
    click B "/iv/problem" "Pre-testing"
    click C1 "/iv/step1_overall" "Stage 1"
    click f1 "/iv/step1_firststage" "Testing the first stage"
    click C2 "/" "Try something else"
    click I "https://davidcard.berkeley.edu/papers/card-dellavigna-pagelimits.pdf" "Page limits are non-binding."
{{< /diagram >}}

