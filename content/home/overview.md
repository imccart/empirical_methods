+++
widget = "blank"  # See https://sourcethemes.com/academic/docs/page-builder/
headless = true  # This file represents a page section.
active = true  # Activate this widget? true/false
weight = 15  # Order that this section will appear.

title = "Overview"
subtitle = ""

[design]
  # Choose how many columns the section has. Valid values: 1 or 2.
  columns = "1"

[design.background]
  # Apply a background color, gradient, or image.
  #   Uncomment (by removing `#`) an option to apply it.
  #   Choose a light or dark text color by setting `text_color_light`.
  #   Any HTML color name or Hex value is valid.

  # Text color (true=light or false=dark).
  text_color_light = false

[design.spacing]
  # Customize the section spacing. Order is top, right, bottom, left.
  padding = ["20px", "0", "20px", "0"]

[advanced]
 # Custom CSS. 
 css_style = ""
 
 # CSS class.
 css_class = ""
+++

With all of the recent developments in methods for applied empirical micro, it can be difficult to keep everything organized. Should I try synthetic control? I have an instrument, but what tests should I run? How sensitive are my IV results to outliers or to weak instruments? What was the name of that RD test again, and why do some people bin the outcome first?

I put these diagrams and links together to help me keep some of this straight. These aren't comprehensive, but I think they serve as a decent reference for the key things to keep in mind, standard tests to consider, and alternative estimators (when relevant). I'm updating these things constantly as I find new information and correct my own misunderstanding. If you see something awry, please [let me know](#contact)!

Now, the goal with all of this is **NOT** to teach the statistics of any given estimator or research design. 

<center>
![](https://media.giphy.com/media/XyOrJljDNBEpa/giphy.gif)
</center>

The goal is to navigate all of the other stuff that you have to do before you can even rely on the results of such an estimation. Estimating something with RD, DD, or IV is one thing, but providing convincing evidence of a causal effect is a much bigger question (and, I would argue, is the implicit goal of anyone using these methods anyway).
