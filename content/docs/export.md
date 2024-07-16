## sablepy.Export

- [Parameters](#export)
- Examples:
  - [Basic Usage](#basic-usage)
  - [Defining filename](#new_filename)
  - [Defining export path](#export_path)
  - [Defining format](#format)

<strong id='export'>export</strong>(<b>data</b><i>=\_NoDefault.no_default</i>, <b>new_filename</b><i>=\_NoDefault.no_default</i>, <b>export_path</b><i>=\_NoDefault.no_default</i>, <b>format</b><i>=\_NoDefault.no_default</i>)

Export dataframes or plots to csv files or png files, respectively.

> Parameters

<ul style='list-style: none'>
	<li id='export-data'>
		<b>data : <i>Data | DataFrame | TimeSeries | BarPlot | Figure, optional</i></b>
		<ul style='list-style: none'>
			<li id='export-data-description'>Data object to export. Accepted formats include: [sablepy.Data, pandas.DataFrame, sablepy.TimeSeries, sablepy.BarPlot, plotly.Figure]</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='export-new_filename'>
		<b>new_filename : <i>str, optional</i></b>
		<ul style='list-style: none'>
			<li id='export-new_filename-description'>String expression representing new filename. If <code>new_filename=None</code>, a generic filename is created.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='export-export_path'>
		<b>export_path : <i>Path | str, optional</i></b>
		<ul style='list-style: none'>
			<li id='export-export_path-description'>String expression or Path object representing destination to export file to. If <code>export_path=None</code>, the file is exported to the current working directory.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='export-format'>
		<b>format : <i>str, optional</i></b>
		<ul style='list-style: none'>
			<li id='export-format-description'>String expression to define how sablepy.Data or pandas.DataFrame are exported. If <code>format='calr</code>, the expected columns for CalR are inserted.</li>
		</ul>
	</li>
</ul>

<hr>

### Examples

#### Basic usage:

- CSV file generated and saved to current directory as `data_{datetime}.csv`:

  ```
  data = Data('example.csv')

  export(data)
  ```

- PNG file generated and saved to current directory as `plot_{datetime}.png`:

  ```
  vo2_df = data.get_channel_data('vo2')
  plot = TimeSeries(vo2_df)

  export(plot)
  ```

- #### `new_filename`:

  ```
  export(plot, new_filename='vo2_plot')
  ```

  - PNG file generated and saved to current directory as `vo2_plot.png`

- #### `export_path`:

  ```
  export(plot, new_filename='vo2_plot', export_path='~/USER/Downloads')
  ```

  - PNG file generated and saved to `~/USER/Downloads/vo2_plot.png`

- #### `format`:

  - If exporting `sablepy.Data` to use in CalR, additional columns may be required. Setting `format='calr'` will ensure the CSV file generated is properly formatted:

  ```
  data = Data('example.csv').resample_data('2h')
  export(data, new_filename='example_2h', export_path='~/USER/Downloads', format='calr')
  ```

  - CSV file generated and saved to `~/USER/Downloads/example_2h.csv`
