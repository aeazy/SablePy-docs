## sablepy.Subplots

- Methods:
  - [`make_subplot`](#make-subplot)
  - [`set_subplot_title`](#set-subplot-title)
  - [`set_subplot_xaxis`](#set-subplot-xaxis)
  - [`set_subplot_yaxis`](#set-subplot-yaxis)
- Examples: - [Basic Usage](#basic-usage)
<hr>

<strong id='make-subplot'>make_subplot</strong>(<b>plots</b>, <b>rows</b><i>=\_NoDefault.no_default</i>, <b>cols</b><i>=\_NoDefault.no_default</i>, <b>plot_title</b><i>=\_NoDefault.no_default</i>, <b>subplot_titles</b><i>=\_NoDefault.no_default</i>, <b>title_first_subplot</b><i>=False</i>, <b>shared_xaxes</b><i>=True</i>, <b>shared_yaxes</b><i>=False</i>, <b>show_grid</b><i>=False</i>, <b>plot_width</b><i>=1400</i>, <b>plot_height</b><i>=600</i>, <b>vertical_spacing</b><i>=0.1</i>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>plots : <i>list[sablepy.plotting.bar_plot.BarPlot | plotly.graph_objs._figure.Figure | sablepy.plotting.time_series.TimeSeries]</i></b>
        <ul style='list-style: none'>
            <li>List of objects representing the subplots to create.</li>
        </ul>
    </li>
    <li>
        <b>rows : <i>int, optional</i></b>
        <ul style='list-style: none'>
            <li>Number of rows the plot will have. Defaults to None. If <code>rows=None</code>, the number of rows generated is determined by the objects passed to the <code>plots</code> argument. 
                <ul style='list-style: none'>
                    <li>sablepy.TimeSeries | plotly.Figure - one subplot per row.</li>
                    <li>sablepy.BarPlot - two subplots per row.</li>
                </ul>
            </li>
        </ul>
    </li>
    <li>
        <b>cols : <i>int, optional</i></b>
        <ul style='list-style: none'>
            <li>Number of cols the plot will have. Defaults to None. If <code>cols=None</code>, the number of cols is determined using the logic defined in <code>rows</code> parameter.</li>
        </ul>
    </li>
    <li>
        <b>plot_title : <i>str, optional</i></b>
        <ul style='list-style: none'>
            <li>String expression representing the plot title. Defaults to None.</li>
        </ul>
    </li>
    <li>
        <b>subplot_titles : <i>list[str], optional</i></b>
        <ul style='list-style: none'>
            <li>Subplot titles. Defaults to None.</li>
                <ul style='list-style: none'>
                    <li>This assumes the first subplot is not labelled unless defined otherwise by <code>title_first_subplot</code>.</li>
                </ul>
        </ul>
    </li>
    <li>
        <b>title_first_subplot : <i>bool, default False</i></b>
        <ul style='list-style: none'>
            <li>Whether or not the first subplot is titled with the argument provided to <code>subplot_titles</code>. Defaults to False.</li>
        </ul>
    </li>
    <li>
        <b>shared_xaxes : <i>bool, default True</i></b>
        <ul style='list-style: none'>
            <li>Whether or not the subplots all have the same x-axis. Defaults to True.</li>
        </ul>
    </li>
    <li>
        <b>shared_yaxes : <i>bool, default False</i></b>
        <ul style='list-style: none'>
            <li>Whether or not the subplots all have the same y-axis. Defaults to False.</li>
        </ul>
    </li>
    <li>
        <b>show_grid : <i>bool, default False</i></b>
        <ul style='list-style: none'>
            <li>Whether or not the subplots have grids visible. Defaults to False.</li>
        </ul>
    </li>
    <li>
        <b>plot_width : <i>int, default 1400</i></b>
        <ul style='list-style: none'>
            <li>The overall plot width. Defaults to 1400.</li>
        </ul>
    </li>
    <li>
        <b>plot_height : <i>int, default 600</i></b>
        <ul style='list-style: none'>
            <li>The overall plot height. Defaults to 600.</li>
        </ul>
    </li>
    <li>
        <b>vertical_spacing : <i>float, default 0.1</i></b>
        <ul style='list-style: none'>
            <li>The spacing between subplots. Defaults to 0.1.</li>
        </ul>
    </li>
</ul>
<hr>

<strong id='set-subplot-title'>set_subplot_title</strong>(<b>plot_num</b>, <b>text</b>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>plot_num : <i>int</i></b>
        <ul style='list-style: none'>
            <li>Integer representing subplot title to change.</li>
        </ul>
    </li>
    <li>
        <b>text : <i>str</i></b>
        <ul style='list-style: none'>
            <li>String expression of subplot title text.</li>
        </ul>
    </li>
</ul>
<hr>

<strong id='set-subplot-xaxis'>set_subplot_xaxis</strong>(<b>plot_num</b>, <b>text</b>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>plot_num : <i>int</i></b>
        <ul style='list-style: none'>
            <li>Integer representing subplot x-axis text to change.</li>
        </ul>
    </li>
    <li>
        <b>text : <i>str</i></b>
        <ul style='list-style: none'>
            <li>String expression of subplot x-axis text.</li>
        </ul>
    </li>
</ul><hr>
<strong id='set-subplot-yaxis'>set_subplot_yaxis</strong>(<b>plot_num</b>, <b>text</b>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>plot_num : <i>int</i></b>
        <ul style='list-style: none'>
            <li>Integer representing subplot y-axis text to change.</li>
        </ul>
    </li>
    <li>
        <b>text : <i>str</i></b>
        <ul style='list-style: none'>
            <li>String expression of subplot y-axis text.</li>
        </ul>
    </li>
</ul>
<hr>

> Examples

#### Basic Usage

<div style="display:flex">

```
d = Data("example")

vo2 = d.get_channel_data("vo2")
vo2_plot = TimeSeries(vo2)

vco2 = d.get_channel_data("vco2")
vco2_plot = TimeSeries(vco2)

sp = make_subplot([vo2_plot, vco2_plot])
```

</div>
<div style="display:flex">

![subplot-basic](../images/subplot/subplot-basic.png)

</div>
