---
title: Regression Discontinuity Flowchart
date: '2020-11-17'
diagram: true
diagram_parallax: yes
image_size: contain
---

Most of the nodes in the diagram below are clickable, which will take you to another page with much more detail on that specific issue. Remember, in practice, empirical work is not as neat as this flowchart. 


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
{{< /diagram >}}

<img src="https://media.giphy.com/media/3oKIPuBx0SDOhdISAw/giphy.gif#center" alt="neato">



    # click B "/iv/problem" "Pre-testing"
    # click C1 "/iv/step1_overall" "Stage 1"
    # click D1 "/iv/step1_firststage" "Testing the first stage"
    # click D2 "/iv/step1_exog" "Testing the exogeneity assumption"
    # click D3 "/iv/step1_exclude" "Testing the exclusion assumption"
    # click E "/iv/step1_assess" "Assessing your instrument tests"
    # click e1 "/iv/step1b_overall" "IVs are OK, but not great"
    # click f1 "/iv/step1b_firststage" "Weak IV Robust Inference"
    # click f2 "/iv/step1b_exog_excl" "Invalid IVs"
   
 
