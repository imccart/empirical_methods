---
title: Difference-in-Differences Flowchart
date: '2020-09-12'
diagram: true
diagram_parallax: yes
image_size: contain
---


Most of the nodes in the diagram below are clickable, which will take you to another page with much more detail on that specific issue. If you're accessing this on an android mobile device, the flowcharts are going to look a little odd (probably huge). This is a known issue in rendering these types of diagrams. See this closed [issue on GitHub](https://github.com/mermaid-js/mermaid/issues/816) and these unanswered [posts on StackOverflow](https://stackoverflow.com/search?q=%5Bmermaid%5D+chrome). If anyone has any suggestions for how to have this render on an android mobile browser, please let me know. Otherwise, happy DD-ing!


{{< diagram >}}
graph TD;
    linkStyle default interpolate basis
    A(["Thinking of DD?"]) --> B(["2 Groups, 2 Periods"])
    A --> C(["2 Groups, Many Periods"])
    A --> D(["Many Groups, Many Periods"])
    subgraph one ["Standard DD"]
    B --> b1([""])
    end
{{< /diagram >}}

