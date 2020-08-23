+++
widget = "blank"  # See https://sourcethemes.com/academic/docs/page-builder/
headless = true  # This file represents a page section.
active = true  # Activate this widget? true/false
weight = 20  # Order that this section will appear.

title = "Endogeneity"
subtitle = ""

[content]
  page_type = "endog"

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

So you think you have an endogeneity problem? Well, you're not alone. But if the question is important enough, surely there's something we can do. Right?

In this section, I'm assuming that you have an endogeneity problem without any obvious solution. No instruments, no policy "shock", no discontinuity, no "quasi" or "natural" experiment. Basically, you're stuck with a problem and without any clear strategy to point identify the casual effect of interest.

<img src="https://media.giphy.com/media/3orieLeZL5kyNqiLfO/giphy.gif#center" alt="neato">

All hope is not lost. You can essentially start making some more assumptions and/or test how sensitive your results are to selection on unobservables. Take a look at the [endogeneity flowchart]({{<ref "/endog/flowchart" >}}) to help navigate this type of situation.
