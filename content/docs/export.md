## sablepy.Export

- [Parameters](#export)
- [Methods](#methods)

  - [`export_to_prism`](#export-to-prism)

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

> Example Usage

- Create the dataframe:

  - **Note:** `export_to_prism` requires the data in the dataframe to be for the individual cages, not the group.

  ```
  from sablepy import *

  groups = [
      Group("Group 1", [1, 3, 9, 11]),
      Group("Group 2", [2, 4, 10, 12]),
  ]

  df = Data(file='example.csv', abs_path=filepath)

  vo2_individual_df = df.get_channel_data("vo2")
  ```

- Export to a csv file named `vo2_df`:

  ```
  export_to_prism(vo2_individual_df, groups, 'vo2_df')
  ```

  - This would generate a csv file in the current directory with the following format:

    ```
                vo2_1     vo2_3     vo2_9    vo2_11       NaN     vo2_2  \
    Days
    0.000000  0.017268  0.005734  0.013789  0.005263      NaN    0.015411
    0.041667  0.135587  0.104935  0.089224  0.014546      NaN    0.090681
    0.083333  2.224565  1.863155  2.137718  2.115085      NaN    1.912842
    0.125000  1.982361  1.743198  1.498956  1.818595      NaN    1.553493
    0.166667  1.436482  1.728926  2.024040  1.887813      NaN    1.601326

                vo2_4    vo2_10    vo2_12
    Days
    0.000000 -0.001023  0.002807  0.000081
    0.041667  0.102106  0.086710  0.010285
    0.083333  2.258372  1.915576  2.011720
    0.125000  1.995858  1.779801  1.905662
    0.166667  1.699485  1.908270  1.739236
    ```

    - Where columns are sorted by groups and an empty column separates each group.

- Optionally, you can provide a filepath to export the file to:

  ```
  export_to_prism(vo2_individual_df, groups, 'vo2_df', '~/USER/Downloads')
  ```

  - This would generate a csv file at `~/USER/Downloads/vo2_df.csv`

<hr>

### Methods

<strong id='export-to-prism'>export_to_prism</strong>(<b>data</b>, <b>groups</b><i>=\_NoDefault.no_default</i>, <b>filename</b><i>=\_NoDefault.no_default</i>, <b>export_path</b><i>=\_NoDefault.no_default</i>)

Format and export a <sablepy.Data> object for Prism.

> Parameters

<ul style='list-style: none'>
	<li id='export_to_prism-data'>
		<b>data : <i>Data</i></b>
		<ul style='list-style: none'>
			<li id='export_to_prism-data-description'>A <code>sablepy.Data</code> object.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='export_to_prism-groups'>
		<b>groups : <i>list[Group], optional</i></b>
		<ul style='list-style: none'>
			<li id='export_to_prism-groups-description'>List of <code>sablepy.dataclasses.Group</code> objects.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='export_to_prism-filename'>
		<b>filename : <i>str | None, optional</i></b>
		<ul style='list-style: none'>
			<li id='export_to_prism-filename-description'>String expression representing desired filename.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='export_to_prism-export_path'>
		<b>export_path : <i>Path | str | None, optional</i></b>
		<ul style='list-style: none'>
			<li id='export_to_prism-export_path-description'>String or Path object representing the directory to export the new file.</li>
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
