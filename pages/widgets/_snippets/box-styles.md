| Property           | Type                                                       | Description                                                                                                                                         |
|:-------------------|:-----------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------|
| margin             | integer/string                                             | Margin with CSS-style notation (1 to 4 integers) e.g. margin: 5 20 5                                                                                |
| padding            | integer/string                                             | Padding with CSS-style notation (1 to 4 integers) e.g. padding: 5 20 5                                                                              |
| backgroundColor    | [Color](/widgets/types#Color)                     | The background color of this widget.                                                                                                                |
| backgroundImage    | [BackgroundImage](/widgets/types#BackgroundImage) | The background image of this widget.                                                                                                                |
| backgroundGradient | [Gradient](/widgets/types#Gradient)               | The background gradient of this widget.                                                                                                             |
| border             | [Border](/widgets/types#Border)                   | The border of this widget.                                                                                                                          |
| shadow             | [Shadow](/widgets/types#Shadow)                   | The shadow of this widget                                                                                                                           |
| clipContent        | boolean                                                    | Some widgets (such as Image) may bleed through the container when borderRadius is set. Use this to apply a clipping to ensure this does not happen. |
| width              | integer                                                    | The width of this widget.                                                                                                                           |
| height             | integer                                                    | The height of this widget.                                                                                                                          |
| borderRadius   | string or integer | The border radius of the widget. This can be specified using CSS-like notation with 1 to 4 integers. Minimum value: 0.                                                               |
| borderColor    | integer or string | Sets the border color, starting with '0xFF' for full opacity. Possible values: transparent, black, blue, white, red, grey, teal, amber, pink, purple, yellow, green, brown, cyan, indigo, lime, orange. |
| borderWidth    | integer           | Thickness of the border. Minimum value should be 0.                                                                                                                                  |
| shadowColor    | integer or string | Sets the box shadow color starting with '0xFF' for full opacity. Possible values: transparent, black, blue, white, red, grey, teal, amber, pink, purple, yellow, green, brown, cyan, indigo, lime, orange. |
| shadowOffset   | array             | The values in the array define the horizontal and vertical offset of the shadow. Example: if the shadowOffset is set to [2, 4], the shadow will be offset by 2 pixels horizontally and 4 pixels vertically from its original position.                   |
| shadowRadius   | string or integer | The border radius of the widget. This can be specified using CSS-like notation with 1 to 4 integers. Minimum value: 0.                                                               |
| shadowStyle    | string            | The blur style to apply on the shadow: normal, solid, outer, inner.                                                                                                                   |
