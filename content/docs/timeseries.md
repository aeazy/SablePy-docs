## sablepy.TimeSeries

- [Parameters](#timeseries)
- [Individual Cage Data](#creating-plot-for-individual-cages)
- [Group Cage Data](#average-by-group-before-creating-plot)
- [Plot Customization](#customizing-the-plot)
  - [Circadian Highlights](#circadian-highlighting)
  - [Titles](#titles)
  - [Options](#options)
- [Export](#export)

<strong id='timeseries'>TimeSeries</strong>(<b>data</b>, <b>circadian_info=CircadianInfo(highlight=True, light_start=6, dark_start=18)</b>, <b>title=Title(text=None, size=18, visible=True)</b>, <b>xaxis=XAxis(showgrid=True, text=None, tickinterval=12, type='hour', visible=True)</b>, <b>yaxis=YAxis(showgrid=True, text=None, visible=True)</b>, <b>legend=Legend(title=None)</b>, <b>options=Options(error_bars=True, height=550, hovermode='x unified', line_style=None, showgrid=False, showlegend=True, width=1500)</b>, <b>config=Config(displayLogo=False)</b>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>data : <i>sablepy.core.data.Data | pandas.core.frame.DataFrame</i></b>
        <ul style='list-style: none'>
            <li>Accepts either a <code>sablepy.Data</code> or <code>pandas.DataFrame</code> object.</li>
        </ul>
    </li>
    <li>
        <b>circadian_info=CircadianInfo(highlight=True, light_start=6, dark_start=18) : <i>type</i></b>
        <ul style='list-style: none'>
            <li>Expects <code>sablepy.CircadianInfo</code> dataclass. See the <a href="https://github.com/aeazy/SablePy/blob/main/sablepy/content/docs/dataclasses.md#circadianinfo">CircadianInfo documentation</a> for more information.</li>
        </ul>
    </li>
    <li>
        <b>title : <i>Title, default Title(text=None, size=18, visible=True)</i></b>
        <ul style='list-style: none'>
            <li>Expects <code>sablepy.Title</code> dataclass. See the <a href="https://github.com/aeazy/SablePy/blob/main/sablepy/content/docs/dataclasses.md#title">Title documentation</a> for more information.</li>
        </ul>
    </li>
    <li>
        <b>xaxis : <i>XAxis, default XAxis(showgrid=True, text=None, tickinterval=12, type='hour', visible=True)</i></b>
        <ul style='list-style: none'>
            <li>Expects <code>sablepy.XAxis</code> dataclass. See the <a href="https://github.com/aeazy/SablePy/blob/main/sablepy/content/docs/dataclasses.md#xaxis"> documentation</a> for more information.</li>
        </ul>
    </li>
    <li>
        <b>yaxis : <i>YAxis, default YAxis(showgrid=True, text=None, visible=True)</i></b>
        <ul style='list-style: none'>
            <li>Expects <code>sablepy.YAxis</code> dataclass. See the <a href="https://github.com/aeazy/SablePy/blob/main/sablepy/content/docs/dataclasses.md#yaxis"> YAxis documentation</a> for more information.</li>
        </ul>
    </li>
    <li>
        <b>legend : <i>Legend, default Legend(title=None)</i></b>
        <ul style='list-style: none'>
            <li>Expects <code>sablepy.Legend</code> dataclass. See the <a href="https://github.com/aeazy/SablePy/blob/main/sablepy/content/docs/dataclasses.md#legend"> Legend documentation</a> for more information.</li>
        </ul>
    </li>
    <li>
        <b>options : <i>Options, default Options(error_bars=True, height=550, hovermode='x unified', line_style=None, showgrid=False, showlegend=True, width=1500)</i></b>
        <ul style='list-style: none'>
            <li>Expects <code>sablepy.Options</code> dataclass. See the <a href="https://github.com/aeazy/SablePy/blob/main/sablepy/content/docs/dataclasses.md#options"> Options documentation</a> for more information.</li>
        </ul>
    </li>
    <li>
        <b>config : <i>Config, default Config(displayLogo=False)</i></b>
        <ul style='list-style: none'>
            <li>Expects <code>sablepy.Config</code> dataclass. See the <a href="https://github.com/aeazy/SablePy/blob/main/sablepy/content/docs/dataclasses.md#config"> Config documentation</a> for more information.</li>
        </ul>
    </li>
</ul>

#### Creating plot for individual cages:

```
df = Data(data=df)
vo2_df = df.get_channel_data("vo2")

plot = TimeSeries(vo2_df)
plot.show()
```

![Timeseries-individual](../images/timeseries/timeseries-individual.png)

#### Average by group before creating plot:

```
df = Data(data=df)
groups = [Group("Control", [1, 2, 3, 4]), Group("G1", [5, 6, 7, 8]), Group("G2", [9, 10, 11, 12]), Group("G3", [13, 14, 15, 16])]
vo2_df = df.get_channel_data("vo2").average_by_group(groups)
plot = TimeSeries(vo2_df)

plot.show()
```

![Timeseries-group](../images/timeseries/timeseries-group.png)

#### Customizing the plot:

- ##### Circadian highlighting:

  - Specifying light and dark start times:

    ```
    plot = TimeSeries(vo2_df, circadian_info=CircadianInfo(light_start=8, dark_start=20))
    plot.show()
    ```

    ![Timeseries-custom-circadian](../images/timeseries/timeseries-custom-circadian.png)

  - Remove highlights:
    ```
    plot = TimeSeries(vo2_df, circadian_info=CircadianInfo(False))
    plot.show()
    ```
    ![Timeseries-no-circadian](../images/timeseries/timeseries-no-circadian.png)

- ##### Titles:

  - Modify plot title text and size, X/Y Axis text, and legend title
  - Specify X-Axis interval (default is 12), as well as switch to 'timestamps' for the X-Axis labels

  ```
  plot = TimeSeries(
  vo2_df,
  title=Title(text="Average Oxygen Consumed", size=24),
  xaxis=XAxis(tickinterval=5, type="timestamps"),
  yaxis=YAxis(text="Oxygen Consumption (ml/hr)"),
  legend=Legend(title="Group"),
  )
  ```

  ![timeseries-custom-titles](../images/timeseries/timeseries-custom-titles.png)

- ##### Options:
  - Disable error bars display
  - Modify color and style of lines in the plot
  ```
  plot = TimeSeries(
  vo2_df,
  options=Options(error_bars=False, line_style={'G3':Line(color='black', dash='dashdot')})
  )
  ```
  ![timeseries-custom-options](../images/timeseries/timeseries-custom-options.png)

#### Export

- All data and plots created using `sablepy` can easily be exported using `sablepy.export`:

  ```
  plot = TimeSeries(vo2_df)

  export(plot)
  ```

- See [the Export documentation](./export.md) for more information.
