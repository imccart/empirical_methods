+++
widget = "blank"  # See https://sourcethemes.com/academic/docs/page-builder/
headless = true  # This file represents a page section.
active = true  # Activate this widget? true/false
weight = 30  # Order that this section will appear.

title = "Instrumental Variables"
subtitle = ""

[content]
  page_type = "iv"

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

Want to solve your endogeneity problem with with IV? Well, IV comes with its own problems too. For one, it's biased (although that can be fixed with some assumptions). It's also a very sensitive approach. IV used to be the darling of empirical work, but not so much anymore. 

I'm assuming you have some instrument(s) in mind already, at least as many as you have endogenous variables. 

<img src="https://media.giphy.com/media/fXtGlVSI2ZB2E1JO0b/giphy.gif#center" alt="neato">

With those potential instruments in hand, here's the [IV interactive flowchart]({{<ref "/iv/flowchart" >}}).

