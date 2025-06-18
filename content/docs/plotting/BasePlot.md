# BasePlot

- [Class Documentation](#baseplot)
- [Class Methods](#class-methods)
  - [add_annotation](#add-annotation)
  - [add_hline](#add-hline)
  - [add_trace](#add-trace)
  - [add_vline](#add-vline)
  - [copy](#copy)
  - [rename_trace](#rename-trace)
  - [show](#show)
  - [update_axis](#update-axis)
  - [update_title](#update-title)
  - [update_trace](#update-trace)

<strong id='BasePlot'>BasePlot</strong>(<b>config</b>=<i>None</i>, <b>data</b>=<i>None</i>, <b>fig_type</b>=<i>None</i>)

Base class for all plots in SablePy.

> Parameters:

<ul>
    <li>
        <b id='BasePlot-config'>config : <i>Config, None</i></b>
        <ul style='list-style: none'>
            <li id='BasePlot-config-description'>The configuration object for the plot. If not provided, it is obtained from the global config using <code>sablepy.config.get_config()</code>.</li>
        </ul>
    </li>
    <li>
        <b id='BasePlot-data'>data : <i>DataFrame | Data | Series, None</i></b>
        <ul style='list-style: none'>
            <li id='BasePlot-data-description'>The data to plot. This can be a Pandas DataFrame, a Data object, or a Series.</li>
        </ul>
    </li>
    <li>
        <b id='BasePlot-fig_type'>fig_type : <i>str, None</i></b>
        <ul style='list-style: none'>
            <li id='BasePlot-fig_type-description'>The type of figure to create. Provided by the class</li>
        </ul>
    </li>
</ul>

## Class Methods

<strong id='add-annotation'>add_annotation</strong>(<b>text</b>=<i>None</i>, <b>x</b>=<i>None</i>, <b>y</b>=<i>1 (top of the plot)</i>, <b>xref</b>=<i>"x"</i>, <b>yref</b>=<i>"paper"</i>, <b>showarrow</b>=<i>True</i>, <b>xshift</b>=<i>None (no shift)</i>, <b>yshift</b>=<i>None (no shift)</i>, <b>textcolor</b>=<i>None</i>, <b>arrowcolor</b>=<i>None ("black")</i>, <b>arrowwidth</b>=<i>1</i>, <b>trace</b>=<i>None</i>, <b>font</b>=<i>None</i>)

Add an annotation to a plot.

> Parameters:

<ul>
    <li>
        <b id='add_annotation-text'>text : <i>str, None</i></b>
        <ul style='list-style: none'>
            <li id='add_annotation-text-description'>The annotation text to display.</li>
        </ul>
    </li>
    <li>
        <b id='add_annotation-x'>x : <i>Optional[StrIntType], None</i></b>
        <ul style='list-style: none'>
            <li id='add_annotation-x-description'>The x coordinate for the annotation. This can be an integer index or a string label that matches the data index. If <code>x=None</code>, <code>trace</code> must be provided to determine the x coordinate. If <code>trace</code> is provided, <code>x</code> is ignored. Defaults to None.</li>
        </ul>
    </li>
    <li>
        <b id='add_annotation-y'>y : <i>int, optional, 1 (top of the plot)</i></b>
        <ul style='list-style: none'>
            <li id='add_annotation-y-description'>The y coordinate for the annotation. If <code>yref='paper'</code>, this is a relative value on the y-axis, where 0 is the bottom and 1 is the top. If <code>yref='x'</code>, this is an absolute value on the y-axis. Defaults to 1 (top of the plot).</li>
        </ul>
    </li>
    <li>
        <b id='add_annotation-xref'>xref : <i>str, "x"</i></b>
        <ul style='list-style: none'>
            <li id='add_annotation-xref-description'>The reference for the x coordinate. Can be "x" for data coordinates or "paper" for relative coordinates. Defaults to "x".</li>
        </ul>
    </li>
    <li>
        <b id='add_annotation-yref'>yref : <i>str, "paper"</i></b>
        <ul style='list-style: none'>
            <li id='add_annotation-yref-description'>The reference for the x coordinate. Defaults to "paper".</li>
        </ul>
    </li>
    <li>
        <b id='add_annotation-showarrow'>showarrow : <i>bool, optional, True</i></b>
        <ul style='list-style: none'>
            <li id='add_annotation-showarrow-description'>Whether the annotation should have an arrow. Defaults to True.</li>
        </ul>
    </li>
    <li>
        <b id='add_annotation-xshift'>xshift : <i>Optional[int], None (no shift)</i></b>
        <ul style='list-style: none'>
            <li id='add_annotation-xshift-description'>The x-axis shift for the annotation in pixels. Defaults to None (no shift).</li>
        </ul>
    </li>
    <li>
        <b id='add_annotation-yshift'>yshift : <i>Optional[int], None (no shift)</i></b>
        <ul style='list-style: none'>
            <li id='add_annotation-yshift-description'>The y-axis shift for the annotation in pixels. Defaults to None (no shift).</li>
        </ul>
    </li>
    <li>
        <b id='add_annotation-textcolor'>textcolor : <i>Optional[str], None</i></b>
        <ul style='list-style: none'>
            <li id='add_annotation-textcolor-description'>The color of the annotation text. This can be any valid CSS color string (e.g., "red"), hex code (e.g., "#FF0000"), or RGB string (e.g., "rgb(255,0,0)"). Defaults to</li>
        </ul>
    </li>
    <li>
        <b id='add_annotation-arrowcolor'>arrowcolor : <i>Optional[str], None ("black")</i></b>
        <ul style='list-style: none'>
            <li id='add_annotation-arrowcolor-description'>The color of the annotation arrow if <code>showarrow=True</code>. This can be any valid CSS color string (e.g., "red"), hex code (e.g., "#FF0000"), or RGB string (e.g., "rgb(255,0,0)"). Defaults to None ("black").</li>
        </ul>
    </li>
    <li>
        <b id='add_annotation-arrowwidth'>arrowwidth : <i>Optional[NumberType], 1</i></b>
        <ul style='list-style: none'>
            <li id='add_annotation-arrowwidth-description'>The width of the annotation arrow if <code>showarrow=True</code>. Defaults to 1.</li>
        </ul>
    </li>
    <li>
        <b id='add_annotation-trace'>trace : <i>Optional[str|BaseTrace], None</i></b>
        <ul style='list-style: none'>
            <li id='add_annotation-trace-description'>The string name of the marker, or a BaseTrace object, to annotate directly. This is only supported in 'bar' and 'regresion' plots.</li>
        </ul>
    </li>
    <li>
        <b id='add_annotation-font'>font : <i>Optional[FontType], None</i></b>
        <ul style='list-style: none'>
            <li id='add_annotation-font-description'>Font properties for the annotation text. This can be a Font dataclass or a dictionary with font</li>
        </ul>
    </li>
</ul>

<hr>
<strong id='add-hline'>add_hline</strong>(<b>x</b>=<i>0.0</i>, <b>label</b>=<i>None</i>, <b>line_color</b>=<i>"black"</i>, <b>line_dash</b>=<i>"solid"</i>, <b>line_opacity</b>=<i>1.0</i>, <b>line_width</b>=<i>1</i>, <b>showarrow</b>=<i>False</i>, <b>xshift</b>=<i>0</i>, <b>yshift</b>=<i>10</i>, <b>textcolor</b>=<i>None</i>)

Adds a horizontal line to the figure, optionally with a label.

> Parameters:

<ul>
    <li>
        <b id='add_hline-x'>x : <i>NumberType, optional, 0.0</i></b>
        <ul style='list-style: none'>
            <li id='add_hline-x-description'>Integer or float representation of label's x position. If <code>x=0</code> the label is placed on the left. If <code>x=1</code> the label is placed on the right of the plot. Defaults to 0.0.</li>
        </ul>
    </li>
    <li>
        <b id='add_hline-label'>label : <i>str, optional, None</i></b>
        <ul style='list-style: none'>
            <li id='add_hline-label-description'>The label for the horizontal line. If provided, an annotation will be added to the plot at the specified <code>x</code> and <code>y</code> coordinates. If <code>label</code> is None, the line will be added without a label. Defaults to None.</li>
        </ul>
    </li>
    <li>
        <b id='add_hline-line_color'>line_color : <i>str, optional, "black"</i></b>
        <ul style='list-style: none'>
            <li id='add_hline-line_color-description'>The color of the horizontal line. This can be any valid CSS color string (e.g., "red"), hex code (e.g., "#FF0000"), or RGB string (e.g., "rgb(255,0,0)"). Defaults to "black".</li>
        </ul>
    </li>
    <li>
        <b id='add_hline-line_dash'>line_dash : <i>str, optional, "solid"</i></b>
        <ul style='list-style: none'>
            <li id='add_hline-line_dash-description'>The dash style of the horizontal line. Accepted arguments include 'solid', 'dash', or 'dashdot'. Defaults to "solid".</li>
        </ul>
    </li>
    <li>
        <b id='add_hline-line_opacity'>line_opacity : <i>float, optional, 1.0</i></b>
        <ul style='list-style: none'>
            <li id='add_hline-line_opacity-description'>The opacity of the horizontal line. This should be a float between 0 and 1, where 0 is fully transparent and 1 is fully opaque. Defaults to 1.0.</li>
        </ul>
    </li>
    <li>
        <b id='add_hline-line_width'>line_width : <i>NumberType, optional, 1</i></b>
        <ul style='list-style: none'>
            <li id='add_hline-line_width-description'>The width of the horizontal line. This can be an integer or float value. Defaults to 1.</li>
        </ul>
    </li>
    <li>
        <b id='add_hline-showarrow'>showarrow : <i>bool, optional, False</i></b>
        <ul style='list-style: none'>
            <li id='add_hline-showarrow-description'>Whether to show an arrow pointing to the position given by <code>x</code> and <code>y</code>. Defaults to False.</li>
        </ul>
    </li>
    <li>
        <b id='add_hline-xshift'>xshift : <i>NumberType, optional, 0</i></b>
        <ul style='list-style: none'>
            <li id='add_hline-xshift-description'>The horizontal offset applied to the annotation label in pixels. Defaults to 0.</li>
        </ul>
    </li>
    <li>
        <b id='add_hline-yshift'>yshift : <i>NumberType, optional, 10</i></b>
        <ul style='list-style: none'>
            <li id='add_hline-yshift-description'>The vertical offset applied to the annotation label in pixels. Defaults to 10.</li>
        </ul>
    </li>
    <li>
        <b id='add_hline-textcolor'>textcolor : <i>Optional[str], optional, None</i></b>
        <ul style='list-style: none'>
            <li id='add_hline-textcolor-description'>The color of the annotation text. This can be any valid CSS color string (e.g., "red"), hex</li>
        </ul>
    </li>
</ul>

<hr>
<strong id='add-trace'>add_trace</strong>(<b>trace</b>=<i>None</i>)

Adds a trace to the plot.

> Parameters:

<ul>
    <li>
        <b id='add_trace-trace'>trace : <i>Trace, None</i></b>
        <ul style='list-style: none'>
            <li id='add_trace-trace-description'>A Plotly trace object to add to the figure. This can be any valid Plotly trace type, such as Scatter, Bar, etc.</li>
        </ul>
    </li>
</ul>

<hr>
<strong id='add-vline'>add_vline</strong>(<b>x</b>=<i>None</i>, <b>label</b>=<i>None (no label)</i>, <b>line_color</b>=<i>"black"</i>, <b>line_dash</b>=<i>"solid"</i>, <b>line_opacity</b>=<i>1.0</i>, <b>line_width</b>=<i>1</i>, <b>showarrow</b>=<i>False</i>, <b>xshift</b>=<i>0</i>, <b>yshift</b>=<i>0</i>, <b>textcolor</b>=<i>None</i>)

Adds a vertical line to the plot at the specified x-coordinate, optionally with a label.

> Parameters:

<ul>
    <li>
        <b id='add_vline-x'>x : <i>str | int, None</i></b>
        <ul style='list-style: none'>
            <li id='add_vline-x-description'>The x-coordinate for the vertical line. This can be an integer index or a string label that matches the data index. If <code>x</code> is a string, it must match one of the index values in the data. If <code>x</code> is an integer, it is treated as an index into the data index.</li>
        </ul>
    </li>
    <li>
        <b id='add_vline-label'>label : <i>str, optional, None (no label)</i></b>
        <ul style='list-style: none'>
            <li id='add_vline-label-description'>The label for the vertical line. If provided, an annotation will be added to the plot at the specified <code>x</code> coordinate. Defaults to None (no label).</li>
        </ul>
    </li>
    <li>
        <b id='add_vline-line_color'>line_color : <i>str, optional, "black"</i></b>
        <ul style='list-style: none'>
            <li id='add_vline-line_color-description'>The color of the vertical line. This can be any valid CSS color string (e.g., "red"), hex code (e.g., "#FF0000"), or RGB string (e.g., "rgb(255,0,0)"). Defaults to "black".</li>
        </ul>
    </li>
    <li>
        <b id='add_vline-line_dash'>line_dash : <i>str, optional, "solid"</i></b>
        <ul style='list-style: none'>
            <li id='add_vline-line_dash-description'>The dash style of the vertical line. Accepted arguments include 'solid', 'dash', or 'dashdot'. Defaults to "solid".</li>
        </ul>
    </li>
    <li>
        <b id='add_vline-line_opacity'>line_opacity : <i>float, optional, 1.0</i></b>
        <ul style='list-style: none'>
            <li id='add_vline-line_opacity-description'>The opacity of the vertical line. This should be a float between 0 and 1, where 0 is fully transparent and 1 is fully opaque. Defaults to 1.0.</li>
        </ul>
    </li>
    <li>
        <b id='add_vline-line_width'>line_width : <i>NumberType, optional, 1</i></b>
        <ul style='list-style: none'>
            <li id='add_vline-line_width-description'>The width of the vertical line. This can be an integer or float value. Defaults to 1.</li>
        </ul>
    </li>
    <li>
        <b id='add_vline-showarrow'>showarrow : <i>bool, optional, False</i></b>
        <ul style='list-style: none'>
            <li id='add_vline-showarrow-description'>Whether to show an arrow pointing to the position given by <code>x</code>. Defaults to False.</li>
        </ul>
    </li>
    <li>
        <b id='add_vline-xshift'>xshift : <i>NumberType, optional, 0</i></b>
        <ul style='list-style: none'>
            <li id='add_vline-xshift-description'>The horizontal offset applied to the annotation label in pixels. Defaults to 0.</li>
        </ul>
    </li>
    <li>
        <b id='add_vline-yshift'>yshift : <i>NumberType, optional, 0</i></b>
        <ul style='list-style: none'>
            <li id='add_vline-yshift-description'>The vertical offset applied to the annotation label in pixels. Defaults to 0.</li>
        </ul>
    </li>
    <li>
        <b id='add_vline-textcolor'>textcolor : <i>Optional[str], optional, None</i></b>
        <ul style='list-style: none'>
            <li id='add_vline-textcolor-description'>The color of the annotation text. This can be any valid CSS color string (e.g., "red"), hex</li>
        </ul>
    </li>
</ul>

<hr>
<strong id='copy'>copy</strong>()

Exports the current plot to the clipboard.

<hr>
<strong id='rename-trace'>rename_trace</strong>(<b>old_name</b>=<i>None</i>, <b>new_name</b>=<i>None</i>)

Renames a trace in the plot.

> Parameters:

<ul>
    <li>
        <b id='rename_trace-old_name'>old_name : <i>str, None</i></b>
        <ul style='list-style: none'>
            <li id='rename_trace-old_name-description'>The current name of the trace to rename.</li>
        </ul>
    </li>
    <li>
        <b id='rename_trace-new_name'>new_name : <i>str, None</i></b>
        <ul style='list-style: none'>
            <li id='rename_trace-new_name-description'>The new name for the trace.</li>
        </ul>
    </li>
</ul>

<hr>
<strong id='show'>show</strong>()

<hr>
<strong id='update-axis'>update_axis</strong>(<b>patch</b>=<i>None</i>)

Updates the plot's x-axis.

> Parameters:

<ul>
    <li>
        <b id='update_axis-patch'>patch : <i>Optional[AxisType], None</i></b>
        <ul style='list-style: none'>
            <li id='update_axis-patch-description'>The patch to update the axis with. Can be a an Axis object or a dictionary. If <code>patch</code> is a dictionary, it must contain valid attributes for the Axis dataclass. See [Axis](https://github.com/aeazy/SablePy-docs/blob/main/content/docs/plotting/attributes.md#axis). **kwargs: Additional keyword arguments to update the axis with. Accepted kwargs are defined by the Axis dataclass. See [Axis](https://github.com/aeazy/SablePy-docs/blob/main/content/docs/plotting/attributes.md#axis).</li>
        </ul>
    </li>
</ul>

<hr>
<strong id='update-title'>update_title</strong>(<b>patch</b>=<i>None</i>, <b>how</b>=<i>"replace". **kwargs: Additional keyword arguments to update the title with. Accepted kwargs are defined by the Title dataclass. See [Title](https://github.com/aeazy/SablePy-docs/blob/main/content/docs/plotting/attributes.md#title)</i>)

Updates the plot's title.

> Parameters:

<ul>
    <li>
        <b id='update_title-patch'>patch : <i>Optional[StrTitleType], None</i></b>
        <ul style='list-style: none'>
            <li id='update_title-patch-description'>The patch to update the title with. Can be a string or a Title object. See [Title](https://github.com/aeazy/SablePy-docs/blob/main/content/docs/plotting/attributes.md#title).</li>
        </ul>
    </li>
    <li>
        <b id='update_title-how'>how : <i>Literal[str], "replace". **kwargs: Additional keyword arguments to update the title with. Accepted kwargs are defined by the Title dataclass. See [Title](https://github.com/aeazy/SablePy-docs/blob/main/content/docs/plotting/attributes.md#title)</i></b>
        <ul style='list-style: none'>
            <li id='update_title-how-description'>How the title is updated with the <code>text</code> argument. Accepts "prefix", "replace", or "suffix". Defaults to "replace". **kwargs: Additional keyword arguments to update the title with. Accepted kwargs are defined by the Title dataclass. See [Title](https://github.com/aeazy/SablePy-docs/blob/main/content/docs/plotting/attributes.md#title).</li>
        </ul>
    </li>
</ul>

<hr>
<strong id='update-trace'>update_trace</strong>(<b>trace_name</b>=<i>None</i>, <b>patch</b>=<i>None. **kwargs: Additional keyword arguments to update the trace with. If <code>patch!=None</code>, these kwargs are merged with the <code>patch</code> object</i>)

Updates a trace in the plot.

> Parameters:

<ul>
    <li>
        <b id='update_trace-trace_name'>trace_name : <i>str, None</i></b>
        <ul style='list-style: none'>
            <li id='update_trace-trace_name-description'>The name of the trace to update.</li>
        </ul>
    </li>
    <li>
        <b id='update_trace-patch'>patch : <i>Optional[Marker | Line | dict], None. **kwargs: Additional keyword arguments to update the trace with. If <code>patch!=None</code>, these kwargs are merged with the <code>patch</code> object</i></b>
        <ul style='list-style: none'>
            <li id='update_trace-patch-description'>The patch to apply to the Can be a Marker, Line, or a dictionary of attributes. If <code>patch=None</code>, kwargs are expected. Accepted kwargs are then defined by the trace type. See examples below. Defaults to None. **kwargs: Additional keyword arguments to update the trace with. If <code>patch!=None</code>, these kwargs are merged with the <code>patch</code> object.</li>
        </ul>
    </li>
</ul>

<hr>
