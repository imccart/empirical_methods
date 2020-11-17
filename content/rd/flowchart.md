---
title: Regression Discontinuity Flowchart
date: '2020-11-17'
diagram: true
diagram_parallax: yes
image_size: contain
---

Most of the nodes in the diagram below are clickable, which will take you to another page with much more detail on that specific issue. If you're accessing this on an android mobile device, the flowcharts are going to look a little odd (probably huge). This is a known issue in rendering these types of diagrams. See this closed [issue on GitHub](https://github.com/mermaid-js/mermaid/issues/816) and these unanswered [posts on StackOverflow](https://stackoverflow.com/search?q=%5Bmermaid%5D+chrome). If anyone has any suggestions for how to have this render on an android mobile browser, please let me know. Otherwise, good luck!


{{< diagram >}}
graph TD;
    linkStyle default interpolate basis
    A(["Condisering RD?"]) --> B[("Can RD Help?")]
    B --> |"no"| Leave[("Try Something Else!")]
{{< /diagram >}}



{{< diagram >}}
graph TD;
    linkStyle default interpolate basis
    A(["Thinking of IV?"]) --> B(["Does it really matter?"])
    B --> |"yes!"| C1(["Are your instruments<br> any good?"])
    B --> |"I guess not"| C2(["Nevermind:<br> try something else"])
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
    e1 --> f2(["exogeneity/exclusion"])
    f1 --> g(["pick something"])
    f2 --> g
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
    click D1 "/iv/step1_firststage" "Testing the first stage"
    click D2 "/iv/step1_exog" "Testing the exogeneity assumption"
    click D3 "/iv/step1_exclude" "Testing the exclusion assumption"
    click E "/iv/step1_assess" "Assessing your instrument tests"
    click e1 "/iv/step1b_overall" "IVs are OK, but not great"
    click f1 "/iv/step1b_firststage" "Weak IV Robust Inference"
    click f2 "/iv/step1b_exog_excl" "Invalid IVs"
    click C2 "/" "Try something else"
    click I "https://davidcard.berkeley.edu/papers/card-dellavigna-pagelimits.pdf" "Page limits are non-binding."
{{< /diagram >}}