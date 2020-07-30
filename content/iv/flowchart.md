---
title: Instrumental Variables Flowchart
author: 'Last updated:'
date: '2020-07-30'
diagram: true
---

Here's a very broad workflow for instrumental variables in practice. I'm assuming you have some instrument(s) in mind already, at least as many as you have endogenous variables. Now, the goal with all of this is **NOT** to teach the statistics of an instrumental variable (IV) or two stage least squares (2SLS) estimator. The goal is to navigate all of the other stuff that you have to do before you can even rely on the results of such an estimation. Estimating something with instrumental variables is one thing, but providing convincing evidence of a causal effect using instrumental variables is a much bigger question (and, I would argue, is the implicit goal of anyone using IV or 2SLS anyway).

Most of the nodes in the diagram below are clickable, which will take you to another page with much more detail on that specific issue. In practice


{{< diagram >}}
graph TD;
    linkStyle default interpolate basis
    A(["Thinking of IV?"]) --> B(["How big is the<br> problem?"]);
    B --> |"it's big"| C1(["Are your instruments<br> any good?"]);
    B --> |"no biggie"| C2(["Nevermind:<br> I'll try something else"]);
    subgraph one [Requirements for any IV]
    C1 --> D1(["first-stage"]);
    C1 --> D2(["exogeneity"]);
    C1 --> D3(["exclusion"]);
    D1 --> E(["assess instruments"]);
    D2 --> E;
    D3 --> E;
    end
    subgraph two ["Still not in the clear"]
    E --> |"lookin' good!"| E1(["How sensitive are<br> the results?"]);
    E1 --> F1(["IV is biased!"]);
    E1 --> F2(["what about outliers?"]);
    F1 --> G(["assess sensitivity"]);
    F2 --> G;
    end
    E --> |"ouch, no bueno"| C2;
    G --> |"um, define sensitive"| C2;
    G --> |"not too bad!"| H(["Go forth and write<br> that appendix!"]);
    click B "/iv/problem" "Pre-testing";
    click C2 "/" "Try something else"
    click H "https://davidcard.berkeley.edu/papers/card-dellavigna-pagelimits.pdf" "Page limits are non-binding."
{{< /diagram >}}
