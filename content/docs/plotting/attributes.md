# _sablepy.plotting.attributes_

- [`Annotation`](#annotation)
- [`Axis`](#axis)
- [`Font`](#font)
- [`Layout`](#layout)
- [`Legend`](#legend)
- [`Line`](#line)
- [`Marker`](#marker)
- [`Theme`](#theme)
- [`Title`](#title)

<strong id='annotation'>Annotation</strong>(<b>text</b>=<i>None</i>, <b>x</b>=<i>None</i>, <b>y</b>=<i>None</i>, <b>xref</b>=<i>None</i>, <b>yref</b>=<i>None</i>, <b>xshift</b>=<i>0</i>, <b>yshift</b>=<i>0</i>, <b>showarrow</b>=<i>True</i>, <b>arrowcolor</b>=<i>"black"</i>, <b>arrowwidth</b>=<i>None</i>, <b>textcolor</b>=<i>None</i>, <b>font</b>=<i>None</i>)

Dataclass representing an annotation for a Plotly figure.

> Parameters:

<ul>
    <li>
        <b id='annotation-text'>text : <i>Optional[str], None</i></b>
        <ul style='list-style: none'>
            <li id='annotation-text-description'>The text of the annotation.</li>
        </ul>
    </li>
    <li>
        <b id='annotation-x'>x : <i>Optional[NumberType], None</i></b>
        <ul style='list-style: none'>
            <li id='annotation-x-description'>The x-coordinate of the annotation.</li>
        </ul>
    </li>
    <li>
        <b id='annotation-y'>y : <i>Optional[NumberType], None</i></b>
        <ul style='list-style: none'>
            <li id='annotation-y-description'>The y-coordinate of the annotation.</li>
        </ul>
    </li>
    <li>
        <b id='annotation-xref'>xref : <i>Optional[str], None</i></b>
        <ul style='list-style: none'>
            <li id='annotation-xref-description'>Reference for the x-coordinate, defaults to "x".</li>
        </ul>
    </li>
    <li>
        <b id='annotation-yref'>yref : <i>Optional[str], None</i></b>
        <ul style='list-style: none'>
            <li id='annotation-yref-description'>Reference for the y-coordinate, defaults to "paper".</li>
        </ul>
    </li>
    <li>
        <b id='annotation-xshift'>xshift : <i>Optional[NumberType], 0</i></b>
        <ul style='list-style: none'>
            <li id='annotation-xshift-description'>Horizontal offset for the annotation. Defaults to 0.</li>
        </ul>
    </li>
    <li>
        <b id='annotation-yshift'>yshift : <i>Optional[NumberType], 0</i></b>
        <ul style='list-style: none'>
            <li id='annotation-yshift-description'>Vertical offset for the annotation. Defaults to 0.</li>
        </ul>
    </li>
    <li>
        <b id='annotation-showarrow'>showarrow : <i>bool, True</i></b>
        <ul style='list-style: none'>
            <li id='annotation-showarrow-description'>Whether to show an arrow pointing to the annotation. Defaults to True.</li>
        </ul>
    </li>
    <li>
        <b id='annotation-arrowcolor'>arrowcolor : <i>str, "black"</i></b>
        <ul style='list-style: none'>
            <li id='annotation-arrowcolor-description'>Color of the arrow pointing to the annotation. If <code>textcolor</code> is set, this will match the text color. Defaults to "black".</li>
        </ul>
    </li>
    <li>
        <b id='annotation-arrowwidth'>arrowwidth : <i>NumberType, None</i></b>
        <ul style='list-style: none'>
            <li id='annotation-arrowwidth-description'>Width of the arrow pointing to the annotation.</li>
        </ul>
    </li>
    <li>
        <b id='annotation-textcolor'>textcolor : <i>Optional[str], None</i></b>
        <ul style='list-style: none'>
            <li id='annotation-textcolor-description'>Color of the annotation text.</li>
        </ul>
    </li>
    <li>
        <b id='annotation-font'>font : <i>Font, None</i></b>
        <ul style='list-style: none'>
            <li id='annotation-font-description'>Font object defining the font properties for the annotation text. See <code>sablepy.plotting.layout.attributes.font.Font</code> for more details.</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='axis'>Axis</strong>(<b>label_start</b>=<i>False</i>, <b>range</b>=<i>None</i>, <b>showgrid</b>=<i>False</i>, <b>size</b>=<i>16</i>, <b>tick_type</b>=<i>"datetime"</i>, <b>title</b>=<i>None</i>)

Sablepy Axis dataclass. This class is used to create the X and Y axes of the figure.

> Parameters:

<ul>
    <li>
        <b id='axis-label_start'>label_start : <i>Optional[bool], False</i></b>
        <ul style='list-style: none'>
            <li id='axis-label_start-description'>Whether the axis label should start at the beginning of the range. Defaults to False.</li>
        </ul>
    </li>
    <li>
        <b id='axis-range'>range : <i>Optional[list[AxisValueType]], None</i></b>
        <ul style='list-style: none'>
            <li id='axis-range-description'>The range of the axis. This is a list of two values, where the first value is the minimum and the second value is the maximum. If not provided, the range will be determined automatically based on the data. Defaults to None.</li>
        </ul>
    </li>
    <li>
        <b id='axis-showgrid'>showgrid : <i>Optional[bool], False</i></b>
        <ul style='list-style: none'>
            <li id='axis-showgrid-description'>Whether to show the grid lines on the axis. Defaults to False.</li>
        </ul>
    </li>
    <li>
        <b id='axis-size'>size : <i>Optional[int], 16</i></b>
        <ul style='list-style: none'>
            <li id='axis-size-description'>The size of the title font. Defaults to 16.</li>
        </ul>
    </li>
    <li>
        <b id='axis-tick_type'>tick_type : <i>Optional[TickValueType], "datetime"</i></b>
        <ul style='list-style: none'>
            <li id='axis-tick_type-description'>The type of ticks to use on the axis. Accepted values are: ["datetime", "hours", "days"]. Defaults to "datetime".</li>
        </ul>
    </li>
    <li>
        <b id='axis-title'>title : <i>Optional[str], None</i></b>
        <ul style='list-style: none'>
            <li id='axis-title-description'>The title of the axis. Defaults to None.</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='font'>Font</strong>(<b>family</b>=<i>"Calibri"</i>, <b>size</b>=<i>12</i>, <b>color</b>=<i>"black"</i>)

Dataclass to represent font attributes for Plotly layout.

> Parameters:

<ul>
    <li>
        <b id='font-family'>family : <i>Optional[str], "Calibri"</i></b>
        <ul style='list-style: none'>
            <li id='font-family-description'>Font family name. Defaults to "Calibri".</li>
        </ul>
    </li>
    <li>
        <b id='font-size'>size : <i>int, 12</i></b>
        <ul style='list-style: none'>
            <li id='font-size-description'>Font size in points. Defaults to 12.</li>
        </ul>
    </li>
    <li>
        <b id='font-color'>color : <i>Optional[str], "black"</i></b>
        <ul style='list-style: none'>
            <li id='font-color-description'>Font color in hex or named color. Defaults to "black".</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='layout'>Layout</strong>(<b>error_bars</b>=<i>False</i>, <b>height</b>=<i>None (auto)</i>, <b>width</b>=<i>None (auto)</i>, <b>theme</b>=<i>"default"</i>, <b>marker_colors</b>=<i>None</i>)

Layout class for configuring plot layout attributes.

> Parameters:

<ul>
    <li>
        <b id='layout-error_bars'>error_bars : <i>Optional[bool], False</i></b>
        <ul style='list-style: none'>
            <li id='layout-error_bars-description'>Whether to show error bars on the plot. Defaults to False.</li>
        </ul>
    </li>
    <li>
        <b id='layout-height'>height : <i>Optional[NumberType], None (auto)</i></b>
        <ul style='list-style: none'>
            <li id='layout-height-description'>The height of the plot in pixels. Defaults to None (auto).</li>
        </ul>
    </li>
    <li>
        <b id='layout-width'>width : <i>Optional[NumberType], None (auto)</i></b>
        <ul style='list-style: none'>
            <li id='layout-width-description'>The width of the plot in pixels. Defaults to None (auto).</li>
        </ul>
    </li>
    <li>
        <b id='layout-theme'>theme : <i>Optional[ThemeType], "default".</b>
        <ul style='list-style: none'>
            <li id='layout-theme-description'>The theme for the plot layout. Defaults to "default". Can also be a <a href="#theme">Theme</a> object.</li>
        </ul>
    </li>
    <li>
        <b id='layout-marker_colors'>marker_colors : <i>Optional[list[str]], None</i></b>
        <ul style='list-style: none'>
            <li id='layout-marker_colors-description'>A list of colors to be used for plot markers. Colors can be in hex format (e.g., "#RRGGBB") a CSS named colors (e.g., "red"), or RGB format (e.g., "rgb(255,0,0)").</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='legend'>Legend</strong>(<b>title</b>=<i>None</i>, <b>title_position</b>=<i>"top"</i>, <b>title_size</b>=<i>None</i>, <b>size</b>=<i>None</i>, <b>x</b>=<i>None</i>, <b>y</b>=<i>None</i>)

Sablepy Legend class. This class is used to create a legend for the plot.

> Parameters:

<ul>
    <li>
        <b id='legend-title'>title : <i>Optional[str], None</i></b>
        <ul style='list-style: none'>
            <li id='legend-title-description'>The title of the legend. Default is None.</li>
        </ul>
    </li>
    <li>
        <b id='legend-title_position'>title_position : <i>Optional[str], "top"</i></b>
        <ul style='list-style: none'>
            <li id='legend-title_position-description'>The position of the title. Can be "top","top left", "top center", or "top right". Defaults to "top".</li>
        </ul>
    </li>
    <li>
        <b id='legend-title_size'>title_size : <i>Optional[int], None</i></b>
        <ul style='list-style: none'>
            <li id='legend-title_size-description'>The font size of the title. Default is 12.</li>
        </ul>
    </li>
    <li>
        <b id='legend-size'>size : <i>Optional[int], None</i></b>
        <ul style='list-style: none'>
            <li id='legend-size-description'>The font size of the legend. Default is 14.</li>
        </ul>
    </li>
    <li>
        <b id='legend-x'>x : <i>Optional[NumberType], None</i></b>
        <ul style='list-style: none'>
            <li id='legend-x-description'>The x position of the legend. Default is 1.0.</li>
        </ul>
    </li>
    <li>
        <b id='legend-y'>y : <i>Optional[NumberType], None</i></b>
        <ul style='list-style: none'>
            <li id='legend-y-description'>The y position of the legend. Default is 1.0.</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='line'>Line</strong>(<b>color</b>=<i>None</i>, <b>width</b>=<i>None</i>, <b>dash</b>=<i>None</i>)

A class for defining line attributes in Plotly. Lines are used in the <sablepy.plotting.plots.TimeSeries> class to customize the appearance of lines.

> Parameters:

<ul>
    <li>
        <b id='line-color'>color : <i>Optional[str], None</i></b>
        <ul style='list-style: none'>
            <li id='line-color-description'>The color of the line. Default is "black".</li>
        </ul>
    </li>
    <li>
        <b id='line-width'>width : <i>Optional[int], None</i></b>
        <ul style='list-style: none'>
            <li id='line-width-description'>The width of the line in pixels. Default is 2.</li>
        </ul>
    </li>
    <li>
        <b id='line-dash'>dash : <i>Optional[DashType], None</i></b>
        <ul style='list-style: none'>
            <li id='line-dash-description'>The dash style of the line. Can be "solid", "dot", "dash", "longdash", or "dashdot". Default is "solid".</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='marker'>Marker</strong>(<b>color</b>=<i>"black"</i>, <b>pattern_shape</b>=<i>None (no pattern)</i>)

A class for defining marker attributes in Plotly. Markers are used in the `sablepy.plotting.plots.BarPlot` class to customize the appearance of bars.

> Parameters:

<ul>
    <li>
        <b id='marker-color'>color : <i>Optional[str], "black"</i></b>
        <ul style='list-style: none'>
            <li id='marker-color-description'>The color of the marker. Defaults to "black".</li>
        </ul>
    </li>
    <li>
        <b id='marker-pattern_shape'>pattern_shape : <i>Optional[PatternShapeType], None (no pattern)</i></b>
        <ul style='list-style: none'>
            <li id='marker-pattern_shape-description'>The pattern shape of the marker. Can be ".", "+", or "x". Defaults to None (no pattern).</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='theme'>Theme</strong>(<b>name</b>=<i>"default"</i>, <b>bg_color</b>=<i>None</i>, <b>plot_bg_color</b>=<i>None</i>, <b>font</b>=<i>None</i>, <b>marker_colors</b>=<i>None</i>)

Theme class for managing plot appearance attributes.

> Parameters:

<ul>
    <li>
        <b id='theme-name'>name : <i>str, "default"</i></b>
        <ul style='list-style: none'>
            <li id='theme-name-description'>The name of the theme. Defaults to "default".</li>
        </ul>
    </li>
    <li>
        <b id='theme-bg_color'>bg_color : <i>str, None</i></b>
        <ul style='list-style: none'>
            <li id='theme-bg_color-description'>The background color of the plot area, derived from the selected theme.</li>
        </ul>
    </li>
    <li>
        <b id='theme-plot_bg_color'>plot_bg_color : <i>str, None</i></b>
        <ul style='list-style: none'>
            <li id='theme-plot_bg_color-description'>The background color of the plotting area, derived from the selected theme.</li>
        </ul>
    </li>
    <li>
        <b id='theme-font'>font : <i>dict[str, str], None</i></b>
        <ul style='list-style: none'>
            <li id='theme-font-description'>Font settings for the theme, such as
            family and size. See also: <a href="#font">Font</a>.
            </li>
        </ul>
    </li>
    
        <b id='theme-marker_colors'>marker_colors : <i>Optional[list[str]], None</i></b>
        <ul style='list-style: none'>
            <li id='theme-marker_colors-description'>A list of colors to be used for plot markers. Colors can be in hex format (e.g., "#RRGGBB") a CSS named colors (e.g., "red"), or RGB format (e.g., "rgb(255,0,0)").</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='title'>Title</strong>(<b>text</b>=<i>None</i>, <b>x</b>=<i>0.5</i>, <b>size</b>=<i>18</i>)

SablePy Title class.

> Parameters:

<ul>
    <li>
        <b id='_doc-text'>text : <i>Optional[str], None</i></b>
        <ul style='list-style: none'>
            <li id='_doc-text-description'>The title of the plot. Defaults to None.</li>
        </ul>
    </li>
    <li>
        <b id='title-x'>x : <i>Optional[NumberType], 0.5</i></b>
        <ul style='list-style: none'>
            <li id='title-x-description'>The x position of the title. Defaults to 0.5.</li>
        </ul>
    </li>
    <li>
        <b id='title-size'>size : <i>Optional[int], 18</i></b>
        <ul style='list-style: none'>
            <li id='title-size-description'>The size of the title font. Defaults to 18.</li>
        </ul>
    </li>
</ul>

<hr>
