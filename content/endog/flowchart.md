---
title: Endogeneity Flowchart
date: '2020-08-21'
diagram: true
diagram_parallax: yes
image_size: contain
---

Most of the nodes in the diagram below are clickable, which will take you to another page with much more detail on that specific issue. If you're accessing this on an android mobile device, the flowcharts are going to look a little odd (probably huge). This is a known issue in rendering these types of diagrams. See this closed [issue on GitHub](https://github.com/mermaid-js/mermaid/issues/816) and these unanswered [posts on StackOverflow](https://stackoverflow.com/search?q=%5Bmermaid%5D+chrome). If anyone has any suggestions for how to have this render on an android mobile browser, please let me know. Otherwise, good luck!


{{< diagram >}}
graph TD;
    linkStyle default interpolate basis
    A(["How big is<br> the problem?"]) --> |"it's big"| B1
    A --> |"no biggie"| B2(["Proceed with caution"])
    B1 --> C1(["Impose assumptions"])
    B1 --> C2(["Bounded effects"])
    click A "/endog/problem" "Pre-testing"
{{< /diagram >}}

