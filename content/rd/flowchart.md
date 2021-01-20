---
title: "Regression Discontinuity Flowchart"
date: '2020-11-17'
diagram: yes
diagram_parallax: yes
image_size: contain
---

Most of the nodes in the diagram below are clickable, which will take you to another page with much more detail on that specific issue. Remember, in practice, empirical work is not as neat as this flowchart. You might find that your discontinuity isn't as clean as you had anticipated, maybe you have heterogeneous effects and need to use multiple cutoffs, or maybe you find that your working with a fuzzy discontinuity and you actually need to implement an IV estimator. That's totally fine.  Empirical work is messy, but by understanding and implementing sound statistical and econometric techniques, we can produce quality analyses. 


If you're accessing this on an android mobile device, the flowcharts are going to look a little odd (probably huge). This is a known issue in rendering these types of diagrams. See this closed [issue on GitHub](https://github.com/mermaid-js/mermaid/issues/816) and these unanswered [posts on StackOverflow](https://stackoverflow.com/search?q=%5Bmermaid%5D+chrome). If anyone has any suggestions for how to have this render on an android mobile browser, please let me know. Otherwise, good luck!


{{< diagram >}}
graph TD;
    linkStyle default interpolate basis
    A(["Considering RD?"]) --> B(["Can RD Help?"])
    B --> |"no"| Leave(["Try Something Else!"])
    B --> |"yes!"| C(["How does RD look?"])
    subgraph one ["Step 1: Basic RD Requirements"]
    C --> D1(["running variable"])
    C --> D2(["manipulation"])
    C --> D3(["covariate balance"])
    D1 --> E(["evaluate"])
    end
    D2 --> E
    D3 --> E
    E --> |"Fuzzy"| F2(["You have IV"])
    F2 --> Leave
    subgraph two ["Step 1b: "]
    E --> |"Strict"| F1(["Okay, but how many cutoffs?"])
    F1 --> G1(["one/pooled"])
    F1 --> G2(["multiple"])
    F1 --> G3(["multiple RVs"])
    end
    G1 --> H(["Implement"])
    subgraph three ["Step 2: Put it to work"]
    H --> I1(["Graph"])
    H --> I2(["Band/Bin Width"])
    H --> I3(["Specification"])
    I1 --> J(["Sensitivity"])
    I2 --> J
    I3 --> J
    end
    J --> |"Looks good?"| K(["Go forth and write!"])
    
   click Leave "/" "Try something else"
   click F2 "/iv/problem"
   click B "/rd/problem"
   click C "/rd/step1_overall"
   click D1 "/rd/step1_rv"
   click D2 "/rd/step1_manipulation"
   click D3 "/rd/step1_covarbal"
   click E "/rd/step1_evaluate"
   click F1 "/rd/step1b_overview"
   click G1 "/rd/step1b_one"
   click G2 "/rd/step1b_mult"
   click G3 "/rd/step1b_multrv"
   click H "/rd/step2_overview"
   click I1 "/rd/step2_graph"
   click I2 "/rd/step2_bin"
   click I3 "/rd/step2_specification"
   click J "/rd/step2_sensitivity"

{{< /diagram >}}

<img src="https://media.giphy.com/media/3oKIPuBx0SDOhdISAw/giphy.gif#center" alt="neato">

 
