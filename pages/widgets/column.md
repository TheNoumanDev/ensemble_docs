# Column widget

Column is designed to arrange child widgets vertically, where the intrinsic sizes of child widgets dictate the layout's appearance.

## Best Practices

- If a single vertical scrollbar is needed for the entire screen, consider using `scrollableView: true` at the `View` level.
- If the entire screen's vertical space is used without a need for scrolling (or if the scrolling is inside some nested section), considered using FlexColumn](/widgets/flex-column.md) to fill the entire vertical space.
- Use Column to lay out the children vertically from top to bottom. Enable scrollable if the children might exceed the available space.
- **Avoid** using child widgets with no height constraint or sized itself to the parent inside the Column.
- **Avoid** using nested scrollable Column for better UX.

## Key Concepts
- **mainAxisSize**: By default the height of a Column is determined by its parent's height constraint (if available), otherwise it will be the combined height of its children. You may force the Column to do the later (size itself to the children's combined height) with `mainAxisSize=min`. Note that a Column does not pass a height constraint to its children, so a Column inside another Column will always size itself to its children. 
- **mainAxis**: This property controls the vertical alignment of the children within the Column. This property is useful only when the mainAxisSize is set to max (default) as there are available spaces to align the children.
- **crossAxis**: This property controls the horizontal alignment of the children within the Column.
- **scrollable**: Enable vertical scrolling when the child widgets grow wider than the available space.
- 
[Test in Kitchen Sink](https://studio.ensembleui.com/app/e24402cb-75e2-404c-866c-29e6c3dd7992/screen/90a8e4df-5eab-4473-ba10-2ecffc9596b0)

## Reference
#### Properties

| Property      | Type                                   | Description                                             |
| :------------ |:---------------------------------------|:--------------------------------------------------------|
| children      | [Widget[]](widgets/directory) | List of child widgets                                   |
| item-template | [ItemTemplate](#item-template)         | List of templated widgets, appearing after the children |
| styles        | object                                 | [See properties](#styles)                               |

#### item-template

| Property | Type   | Description                                                        |
| :------- | :----- | :----------------------------------------------------------------- |
| data     | string | Bind to an array of data from an API response or a variable        |
| name     | string | Set the name to reference as you iterate through the array of data |
| template | widget | The widget to render for each item                                 |

#### styles

| Property                     | Type                                                       | Description                                                                                                                                                                                                                                                                                                                       |
| :--------------------------- |:-----------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| mainAxisSize                 | integer                                                    | If 'max', stretch the Column to fill its parent's height. Otherwise (min) the column's height will be its children's combined. `min` `max`                                                                                                                                                                                        |
| mainAxis                     | string                                                     | Control our children's layout vertically. `start` `center` `end` `spaceBetween` `spaceAround` `spaceEvenly`                                                                                                                                                                                                                       |
| crossAxis                    | string                                                     | Control the horizontal alignment of the children. `start` `center` `end` `stretch` `baseline`                                                                                                                                                                                                                                     |
| fontSize                     | integer                                                    | Sets the size of the text.                                                                                                                                                                                                                                                                                                        |
| fontFamily                   | string                                                     | Set the font family applicable for all widgets inside this container, see the list of all available font families [here](https://github.com/material-foundation/flutter-packages/blob/main/packages/google_fonts/generator/families_supported).                                                                                   |
| gap                          | integer                                                    | The gap between the children in the main direction                                                                                                                                                                                                                                                                                |
| scrollable                   | boolean                                                    | Set to true so content can scroll vertically as needed                                                                                                                                                                                                                                                                            |
| autoFit                      | boolean                                                    | Explicitly make the column's width as wide as the largest child, but only if our column's parent does not already assign a width. This attribute is useful for sizing children who don't have a width (e.g Divider)                                                                                                               |
| borderRadius                 | string or integer                                          | The border radius of the widget.This can be specified using CSS-like notation with 1 to 4 integers. Minimum value: 0.                                                                                                                                                                                                             |
| borderColor                  | [Color](/widgets/types#Color)                     | Sets the border color, starting with '0xFF' for full opacity. `transparent` `black` `blue` `white` `red` `grey` `teal` `amber` `pink` `purple` `yellow` `green` `brown` `cyan` `indigo` `lime` `orange`                                                                                                                           |
| borderWidth                  | integer                                                    | Thickness of the border. Minimum value should be 0.                                                                                                                                                                                                                                                                               |
| shadowColor                  | integer or string                                          | Sets the box shadow color starting with '0xFF' for full opacity. `transparent` `black` `blue` `white` `red` `grey` `teal` `amber` `pink` `purple` `yellow` `green` `brown` `cyan` `indigo` `lime` `orange`                                                                                                                        |
| shadowOffset                 | array                                                      | The values in array define the horizontal and vertical offset of the shadow. Example: if the shadowOffset is set to [2, 4], the shadow will be offset by 2 pixels horizontally and 4 pixels vertically from its original position.                                                                                                |
| shadowRadius                 | string or integer                                          | The border radius of the widget.This can be specified using CSS-like notation with 1 to 4 integers. Minimum value: 0.                                                                                                                                                                                                             |
| shadowStyle                  | string                                                     | The blur style to apply on the shadow `normal`, `solid`, `outer`, `inner`                                                                                                                                                                                                                                                         |
| stackPositionTop             | integer                                                    | The distance of the child's top edge from the top of the stack. This is applicable only for Stack's children.                                                                                                                                                                                                                     |
| stackPositionBottom          | integer                                                    | The distance that the child's bottom edge from the bottom of the stack. This is applicable only for Stack's children.                                                                                                                                                                                                             |
| stackPositionLeft            | integer                                                    | The distance that the child's left edge from the left of the stack. This is applicable only for Stack's children.                                                                                                                                                                                                                 |
| stackPositionRight           | integer                                                    | The distance that the child's right edge from the right of the stack. This is applicable only for Stack's children.                                                                                                                                                                                                               |
| captureWebPointer            | boolean                                                    | Applicable for Web only. When overlaying widgets on top of certain HTML container (e.g. Maps), the mouse click is captured by the HTML container, causing issue interacting with the widget. Use this to capture and maintain the mouse pointer on your widget.                                                                   |
| margin                       | string or integer                                          | Margin with CSS-style notation                                                                                                                                                                                                                                                                                                    |
| padding                      | string or integer                                          | Padding with CSS-style value                                                                                                                                                                                                                                                                                                      |
| width                        | integer                                                    | The width property determines the horizontal size of an element, allowing control over its width dimension within the layout.                                                                                                                                                                                                     |
| height                       | integer                                                    | The height property determines the vertical size of an element, allowing control over its height dimension within the layout.                                                                                                                                                                                                     |
| backgroundImage              | [BackgroundImage](/widgets/types#BackgroundImage) | Background image of the box.                                                                                                                                                                                                                                                                                                      |
| backgroundGradient           | [Gradient](/widgets/types#Gradient)                                                      | Background gradient of the box                                                                                                                                                                                                                                                                                                    |
| backgroundColor              | [Color](/widgets/types#Color)                     | Background color of the box. which can be represented in different formats. It can be specified as a number, a predefined color name, or a hexadecimal value starting with '0x'. `transparent` `black` `blue` `white` `red` `grey` `teal` `amber` `pink` `purple` `yellow` `green` `brown` `cyan` `indigo` `lime` `orange`        |
| expanded                     | boolean                                                    | If the parent is a Row or Column, this flag will stretch this widget in the appropriate direction. (e.g. stretch horizontally for parent of type Row)                                                                                                                                                                             |
| visibilityTransitionDuration | number                                                     | Specify the duration in seconds when a widget animates between visible and not visible state. Note that setting this value will cause the widget to still occupy the UI space even when it is not visible.                                                                                                                        |
| elevation                    | integer                                                    | The z-coordinate at which to place this material relative to its parent. A non-zero value will show a shadow, with its size relative to the elevation value. Minimum value: 0, Maximum value: 24                                                                                                                                  |
| elevationShadowColor         | [Color](/widgets/types#Color)                     | The shadow color for the elevation, which can be represented in different formats. It can be specified as a number, a predefined color name, or a hexadecimal value starting with '0x'. `transparent` `black` `blue` `white` `red` `grey` `teal` `amber` `pink` `purple` `yellow` `green` `brown` `cyan` `indigo` `lime` `orange` |
| elevationBorderRadius        | string or integer                                          | The border radius of the widget.This can be specified using CSS-like notation with 1 to 4 integers. Minimum value: 0.                                                                                                                                                                                                             |
| alignment                    | string                                                     | The alignment of the widget relative to its parent. `topLeft`, `topCenter`, `topRight`, `centerLeft`, `center`, `centerRight`, `bottomLeft`, `bottomCenter`, `bottomRight`                                                                                                                                                        |
| visible                      | boolean                                                    | Toggle a widget visibility on/off. Note that an invisible widget will not occupy UI space, unless the visibilityTransitionDuration is specified.                                                                                                                                                                                  |

