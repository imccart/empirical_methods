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
    subgraph one ["Stage 1: Requirements for any IV"]
    A(["Are your instruments<br> any good?"]) --> B1(["first-stage"])
    A --> B2(["exogeneity"])
    A --> B3(["exclusion"])
    B1 --> C(["assess instruments"])
    B2 --> C
    B3 --> C
    end
    subgraph two ["Stage 1b: Something is better than nothing"]
    C --> |"kind of ok"| d1(["Some violations"])
    d1 --> e1(["first-stage"])
    d1 --> e2(["exogeneity/exclusion"])
    e1 --> f(["pick something"])
    e2 --> f
    end
    subgraph three ["Stage 2: Still not in the clear"]
    C --> |"so far so good!"| D1(["How sensitive are<br> the results?"])
    f --> D1
    D1 --> E1(["IV is biased!"])
    D1 --> E2(["what about outliers?"])
    E1 --> F(["assess sensitivity"])
    E2 --> F
    end
    C --> |"ouch, no bueno"| C2(["Nevermind:<br> Try something else"])
    F --> |"um, define sensitive"| C2
    F --> |"not too bad!"| G(["What am I<br> estimating, again?"])
    G --> |"can I be done?"| H(["Go forth and write<br> that appendix!"])
    click A "/iv/step1_overall" "Stage 1"
    click B1 "/iv/step1_firststage" "Testing the first stage"
    click B2 "/iv/step1_exog" "Testing the exogeneity assumption"
    click B3 "/iv/step1_exclude" "Testing the exclusion assumption"
    click C "/iv/step1_assess" "Assessing your instrument tests"
    click d1 "/iv/step1b_overall" "IVs are OK, but not great"
    click e1 "/iv/step1b_firststage" "Weak IV Robust Inference"
    click e2 "/iv/step1b_exog_excl" "Invalid IVs"
    click C2 "/" "Try something else"
    click H "https://davidcard.berkeley.edu/papers/card-dellavigna-pagelimits.pdf" "Page limits are non-binding."
{{< /diagram >}}

