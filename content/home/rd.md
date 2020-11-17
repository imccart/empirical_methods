+++
widget = "blank"  # See https://sourcethemes.com/academic/docs/page-builder/
headless = true  # This file represents a page section.
active = true  # Activate this widget? true/false
weight = 40  # Order that this section will appear.

title = "Regression Discontinuity"
subtitle = ""

[content]
  page_type = "rd"

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

Interested in using RD? Well, you may be in luck.  RD's quasi-experimental design provides a compelling way to deal with that pesky endogeneity.  I'm assuming your setting has some sort of discontinuous treatment based on an observed underlying value.  

<img src="https://media.giphy.com/media/l0ErNdz1w5vt3YdZm/giphy.gif#center" alt="neato">

Don't despair, here's the [RD interactive flowchart]({{<ref "/rd/flowchart" >}}) to see if RD is well-suited for your context.
