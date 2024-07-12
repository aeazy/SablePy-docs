# _sablepy.common.dataclasses_

- [CircadianInfo](#circadianinfo)
- [CombineOptions](#combineoptions)
- [Config](#config)
- [Group](#group)
- [Legend](#legend)
- [Line](#line)
- [Options](#options)
- [Title](#title)
- [XAxis](#xaxis)
- [YAxis](#yaxis)

### CircadianInfo

<strong id="circadian-info">CircadianInfo</strong>(<b>highlight</b>=<i>True</i>, <b>light_start</b>=<i>6</i>, <b>dark_start</b>=<i>18</i>)

> Parameters

<ul style="list-style: none">
  <li>
    <b>highlight : <i> bool, default True</i></b>
    <ul style="list-style: none">
      <li>Highlight light/dark cycle on TimeSeries plot.</li>
    </ul>
  </li>

  <li>
    <b>light_start : <i> int, default 6</i></b>
    <ul style="list-style: none">
      <li>Time at which lights turn on.</li>
    </ul>
  </li>

  <li>
    <b>dark_start : <i> int, default 18</i></b>
    <ul style="list-style: none">
      <li>Time at which lights turn off.</li>
    </ul>
  </li>
</ul>
<hr>

### CombineOptions

<strong id="combine-options">CombineOptions</strong>(<b>resample_data</b>=<i>True</i>, <b>resample_frequency</b>=<i>"auto"</i>, <b>save_combined_file</b>=<i>False</i>, <b>new_filename</b>=<i>"combined.csv"</i>,
<b>export_dir</b>=<i>"uploads"</i>, <b>overwrite_existing</b>=<i>False</i>, <b>delete_original_files</b>=<i>False</i>)

> Parameters

<ul style="list-style: none">
  <li>
    <b>resample_data : <i> bool, default True</i></b>
    <ul style="list-style: none">
      <li>Resample data after combining. Resample frequency defined by <code>resample_frequency</code>.</li>
    </ul>
  </li>

  <li>
    <b>resample_frequency : <i> str, default 'auto'</i></b>
    <ul style="list-style: none">
      <li>Frequency at which to resample the combined dataframe. If <code>resample_frequency='auto'</code>, the greatest duration between two files rounded up to near half hour is used.</li>
    </ul>
  </li>

  <li>
    <b>save_combined_file : <i> bool, default False</i></b>
    <ul style="list-style: none">
      <li>Save combined file to csv. If <code>save_combined_file=True</code>, the csv file generated is saved as <code>new_filename</code>.</li>
    </ul>
  </li>

  <li>
    <b>new_filename : <i> str, default 'combined.csv'</i></b>
    <ul style="list-style: none">
      <li>Filename of combined file that is saved if <code>save_combined_file=True</code>.</li>
    </ul>
  </li>

  <li>
    <b>export_dir : <i> str, default 'uploads'</i></b>
    <ul style="list-style: none">
      <li>Directory the csv file is saved to if <code>save_combined_file=True</code>.</li>
    </ul>
  </li>

  <li>
    <b>overwrite_exisiting : <i> bool, default False</i></b>
    <ul style="list-style: none">
      <li>Overwrite existing file if <code>new_filename</code> already exists.</li>
    </ul>
  </li>

  <li>
    <b>delete_original_files : <i> bool, default False</i></b>
    <ul style="list-style: none">
      <li>Delete individual files after they are combined.</li>
    </ul>
  </li>
</ul>
<hr>

### Config

<strong id='config'>Config</strong>(<b>circadian_info=CircadianInfo(highlight=True, light_start=6, dark_start=18)</b>, <b>title=Title(text=None, size=18, visible=True)</b>, <b>xaxis=XAxis(showgrid=True, text=None, tickinterval=12, type='hour', visible=True)</b>, <b>yaxis=YAxis(showgrid=True, text=None, visible=True)</b>, <b>legend=Legend(title=None)</b>, <b>options=Options(error_bars=True, height=550, hovermode='x unified', line_style=None, showgrid=False, showlegend=True, width=1500)</b>, <b>config=Config(displayLogo=False)</b>)

> Description

- Simplifies overriding plot defaults when using a Jupyter notebook template. `Config` will accept any of the dataclasses as arguments and apply the changes to all plots in a template.

> Example

```
plot = TimeSeries(
        config=Config(xaxis=XAxis(type='days'), circadian_info=CircadianInfo(highlight=False))
        )
```

- Passing `xaxis=XAxis(type='days')` will set the x-axis labels for all plots to use the 'day' format
- Passing `circadian_info=CircadianInfo(highlight=False)` will remove circadian highlighting from all plots

<hr>

### Group

<strong id='group'>Group</strong>(<b>name</b>, <b>cage_nums</b>, <b>diet</b>=<i>3.56</i>)

> Parameters

<ul style="list-style: none">
  <li>
    <b>name : <i> str</i></b>
    <ul style="list-style: none">
      <li>String name of the group.</li>
    </ul>
  </li>

  <li>
    <b>cage_nums : <i> list[int]</i></b>
    <ul style="list-style: none">
      <li>Integer list of cage numbers in group.</li>
    </ul>
  </li>

  <li>
    <b>diet : <i> float, default 3.56</i></b>
    <ul style="list-style: none">
      <li>Energy value of group diet in kcal/g.</li>
    </ul>
  </li>
</ul>

### Legend

<strong id="legend">Legend</strong>(<b>title</b>)

> Parameters

<ul style="list-style: none">
  <li>
    <b>title : <i> str</i></b>
    <ul style="list-style: none">
      <li>Title of the plot's legend.</li>
    </ul>
  </li>
</ul>

### Line

<strong id="line">Line</strong>(<b>color</b>=<i>None</i>, <b>dash</b>=<i>'solid'</i>)

> Parameters

<ul style="list-style: none">
  <li>
    <b>color : <i> str, default None</i></b>
    <ul style="list-style: none">
      <li>Color of line used in a TimeSeries plot. If <code>color=None</code>, a default color is defined in <code>sablepy.plotting.plot</code>. Accepts color name (e.g., 'blue') or Hex color code (e.g., '#0000FF').</li>
    </ul>
  </li>

  <li>
    <b>dash : <i> str, default 'solid'</i></b>
    <ul style="list-style: none">
      <li>Style of line used in a TimeSeries plot. Use <code>dash='dashdot'</code> for a dashed line.</li>
    </ul>
  </li>
</ul>

### Options

<strong id="options">Options</strong>(<b>error_bars</b>=<i>True</i>, <b>height</b>=<i>550</i>, <b>hovermode</b>=<i>'x unified'</i>, <b>line_style</b>=<i>None</i>, <b>showgrid</b>=<i>False</i>, <b>showlegend</b>=<i>True</i>, <b>width</b>=<i>1500</i>)

> Parameters

<ul style="list-style: none">
  <li>
    <b>error_bars : <i> bool, default True</i></b>
    <ul style="list-style: none">
      <li>Display error bars.</li>
    </ul>
  </li>

  <li>
    <b>height : <i> int, default 550</i></b>
    <ul style="list-style: none">
      <li>Integer value of the height of the plot. Default <code>height=550</code> ensures all 16 lines are shown properly in the legend.</li>
    </ul>
  </li>

  <li>
    <b>hovermode : <i> str, default 'x unified'</i></b>
    <ul style="list-style: none">
      <li>Tooltip display when hovering over a plot. Other arguments include 'x' or False to disable the tooltip entirely.</li>
    </ul>
  </li>

  <li>
    <b>line_style : <i> dict[str, Line], default None</i></b>
    <ul style="list-style: none">
      <li>Dict where key is name of the data series and value is a <code>Line</code> object.</li>
    </ul>
  </li>

  <li>
    <b>showgrid : <i> bool, default False</i></b>
    <ul style="list-style: none">
      <li>Display gridlines on plot.</li>
    </ul>
  </li>

  <li>
    <b>showlegend : <i> bool, default True</i></b>
    <ul style="list-style: none">
      <li>Display plot's legend.</li>
    </ul>
  </li>

  <li>
    <b>width : <i> int, default 1500</i></b>
    <ul style="list-style: none">
      <li>Integer value of the width of the plot. If <code>width=None</code>, the width is automatically determined.</li>
    </ul>
  </li>
</ul>
<hr>

### Title

<strong id="title">Title</strong>(<b>text</b>=<i>None</i>, <b>size</b>=<i>18</i>, <b>visible</b>=<i>True</i>)

> Parameters

<ul style="list-style: none">
  <li>
    <b>text : <i> str, default None</i></b>
    <ul style="list-style: none">
      <li>Text of plot's title. If <code>text=None</code>, default value is determined by <code>sablepy.plotting.plot</code></li>
    </ul>
  </li>

  <li>
    <b>size : <i> int, default 18</i></b>
    <ul style="list-style: none">
      <li>Font size of plot's title.</li>
    </ul>
  </li>

  <li>
    <b>visible : <i> bool, default True</i></b>
    <ul style="list-style: none">
      <li>Show plot title.</li>
    </ul>
  </li>
</ul>
<hr>

### XAxis

<strong id="x-axis">XAxis</strong>(<b>showgrid</b>=<i>True</i>, <b>text</b>=<i>None</i>, <b>tickinterval</b>=<i>12</i>, <b>type</b>=<i>'hour'</i>, <b>visible</b>=<i>True</i>)

> Parameters

<ul style="list-style: none">
  <li>
    <b>showgrid : <i> bool, default True</i></b>
    <ul style="list-style: none">
      <li>Show X-axis gridline.</li>
    </ul>
  </li>

  <li>
    <b>text : <i> str, default None</i></b>
    <ul style="list-style: none">
      <li>X-axis title. If <code>text=None</code>, default value is determined by <code>sablepy.plotting.plot</code>.</li>
    </ul>
  </li>

  <li>
    <b>tickinterval : <i> int, default 12</i></b>
    <ul style="list-style: none">
      <li>Integer value of number of ticks to display.</li>
    </ul>
  </li>

  <li>
    <b>type : <i> str, default 'hours'</i></b>
    <ul style="list-style: none">
      <li>dtype of TimeSeries X-axis. Use <code>type='days'</code> to display day count or <code>type='timestamps'</code> to display datetime timestamp.</li>
    </ul>
  </li>

  <li>
    <b>visible : <i> bool, default True</i></b>
    <ul style="list-style: none">
      <li>Show X-axis labels.</li>
    </ul>
  </li>
</ul>
<hr>

### YAxis

<strong id="y-axis">YAxis</strong>(<b>showgrid</b>=<i>True</i>, <b>text</b>=<i>None</i>, <b>visible</b>=<i>True</i>)

> Parameters

<ul style="list-style: none">
  <li>
    <b>showgrid : <i> bool, default True</i></b>
    <ul style="list-style: none">
      <li>Show Y-axis gridline.</li>
    </ul>
  </li>

  <li>
    <b>text : <i> str, default None</i></b>
    <ul style="list-style: none">
      <li>Y-axis title. If <code>text=None</code>, default value is determined by <code>sablepy.plotting.plot</code>.</li>
    </ul>
  </li>

  <li>
    <b>visible : <i> bool, default True</i></b>
    <ul style="list-style: none">
      <li>Show Y-axis labels.</li>
    </ul>
  </li>
</ul>
<hr>
