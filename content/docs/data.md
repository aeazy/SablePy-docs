## Data

- [Parameters](#Data)
- Methods:
	- [average_by_group](#average-by-group)
	- [exclude_cages](#exclude-cages)
	- [extract_time_period](#extract-time-period)
	- [get_channel_data](#get-channel-data)
	- [groupby](#groupby)
	- [remove_outliers](#remove-outliers)
	- [resample_data](#resample-data)
	- [to_csv](#to-csv)
	- [trim_data](#trim-data)

<strong id='Data'>Data</strong>(<b>file</b><i>=\_NoDefault.no_default</i>, <b>data</b><i>=\_NoDefault.no_default</i>, <b>data_type</b><i>="individual"</i>, <b>folder</b><i>=\_NoDefault.no_default</i>, <b>filepath</b><i>=\_NoDefault.no_default</i>, <b>abs_path</b><i>=\_NoDefault.no_default</i>)

> Parameters

<ul style='list-style: none'>
	<li id='Data-file'>
		<b>file : <i>str, optional</i></b>
		<ul style='list-style: none'>
			<li id='Data-file-description'>String expression of csv file name.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Data-data'>
		<b>data : <i>DataFrame, optional</i></b>
		<ul style='list-style: none'>
			<li id='Data-data-description'>If <code>file=None</code>, a pandas.DataFrame can be used to create a Data object.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Data-data_type'>
		<b>data_type : <i>str, default "individual"</i></b>
		<ul style='list-style: none'>
			<li id='Data-data_type-description'>String expression of how they data is assembled, which is used to determine how the columns are labelled. If <code>data_type='individual'</code>, the column titles are expected to be the {variable}_{cage_num}. If <code>data_type='group'</code>, the column titles are expected to be the {variable}_{group_name}.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Data-folder'>
		<b>folder : <i>str, optional</i></b>
		<ul style='list-style: none'>
			<li id='Data-folder-description'>String expression of folder where csv file is located in the <code>~/uploads</code> directory.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Data-filepath'>
		<b>filepath : <i>Path | str, optional</i></b>
		<ul style='list-style: none'>
			<li id='Data-filepath-description'>Relative path to <code>~/uploads</code> directory.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Data-abs_path'>
		<b>abs_path : <i>Path, optional</i></b>
		<ul style='list-style: none'>
			<li id='Data-abs_path-description'>Absolute path to the csv file.</li>
		</ul>
	</li>
</ul>

<hr>
<strong id='average-by-group'>average_by_group</strong>(<b>groups</b>)

> Parameters

<ul style='list-style: none'>
	<li id='average_by_group-groups'>
		<b>groups : <i>dict</i></b>
		<ul style='list-style: none'>
			<li id='average_by_group-groups-description'>List of Group objects. See dataclass 'Group' for formatting.</li>
		</ul>
	</li>
</ul>

<hr>
<strong id='exclude-cages'>exclude_cages</strong>(<b>cage_nums</b>)

> Parameters

<ul style='list-style: none'>
	<li id='exclude_cages-cage_nums'>
		<b>cage_nums : <i>int| list[int]</i></b>
		<ul style='list-style: none'>
			<li id='exclude_cages-cage_nums-description'>Integer, or list of integers, representing cage number(s) to exclude (e.g., [1,4,7])</li>
		</ul>
	</li>
</ul>

<hr>
<strong id='extract-time-period'>extract_time_period</strong>(<b>start_datetime</b>, <b>end_datetime</b>, <b>fmt</b><i>="%Y-%m-%d %H:%M:%S"</i>)

> Parameters

<ul style='list-style: none'>
	<li id='extract_time_period-start_datetime'>
		<b>start_datetime : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='extract_time_period-start_datetime-description'>Start datetime of new dataframe. Accepts date ("%Y-%m-%d") or datetime ("%Y-%m-%d %H:%M:%S").</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='extract_time_period-end_datetime'>
		<b>end_datetime : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='extract_time_period-end_datetime-description'>End datetime of new dataframe. Accepts date ("%Y-%m-%d") or datetime ("%Y-%m-%d %H:%M:%S").</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='extract_time_period-fmt'>
		<b>fmt : <i>str, default "%Y-%m-%d %H:%M:%S"</i></b>
		<ul style='list-style: none'>
			<li id='extract_time_period-fmt-description'>Format of start_datetime/end_datetime parameter.</li>
		</ul>
	</li>
</ul>

<hr>
<strong id='get-channel-data'>get_channel_data</strong>(<b>channel</b>, <b>average_by_group</b><i>=False</i>, <b>groups</b><i>=_NoDefault.no_default</i>)

> Parameters

<ul style='list-style: none'>
	<li id='get_channel_data-channel'>
		<b>channel : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='get_channel_data-channel-description'>Desired channel. Use self.channel to determine accepted arguments.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='get_channel_data-average_by_group'>
		<b>average_by_group : <i>bool, default False</i></b>
		<ul style='list-style: none'>
			<li id='get_channel_data-average_by_group-description'>If true, averages cages by group.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='get_channel_data-groups'>
		<b>groups : <i>dict[str, list[int]], optional</i></b>
		<ul style='list-style: none'>
			<li id='get_channel_data-groups-description'>If average_by_group is true, averages by cages.</li>
		</ul>
	</li>
</ul>

<hr>
<strong id='read-csv'>read_csv</strong>(<b>file</b>)

> Parameters

<ul style='list-style: none'>
	<li id='read_csv-file'>
		<b>file : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='read_csv-file-description'>_description_</li>
		</ul>
	</li>
</ul>

<hr>
<strong id='remove-outliers'>remove_outliers</strong>(<b>df</b>)

> Parameters

<ul style='list-style: none'>
	<li id='remove_outliers-df'>
		<b>df : <i>pd.Dataframe</i></b>
		<ul style='list-style: none'>
			<li id='remove_outliers-df-description'>Pandas dataframe with outliers removed</li>
		</ul>
	</li>
</ul>

<hr>
<strong id='resample-data'>resample_data</strong>(<b>frequency</b>)

> Parameters

<ul style='list-style: none'>
	<li id='resample_data-frequency'>
		<b>frequency : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='resample_data-frequency-description'>Desired size of the new slice. For more info on frequencies, see <code><https://pandas.pydata.org/pandas-docs/stable/user_guide/timeseries.html#offset-aliases></code>.</li>
		</ul>
	</li>
</ul>

<hr>
<strong id='to-csv'>to_csv</strong>(<b>filename</b>, <b>export_path</b><i>=_NoDefault.no_default</i>)

> Parameters

<ul style='list-style: none'>
	<li id='to_csv-filename'>
		<b>filename : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='to_csv-filename-description'>String expression representing filename of csv file.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='to_csv-export_path'>
		<b>export_path : <i>str | Path, optional</i></b>
		<ul style='list-style: none'>
			<li id='to_csv-export_path-description'>String or Path object representing file path to export csv to.</li>
		</ul>
	</li>
</ul>

<hr>
<strong id='trim-data'>trim_data</strong>(<b>from_start_or_end</b>, <b>duration</b>, <b>fmt</b><i>="%Y-%m-%d %H:%M:%S"</i>)

> Parameters

<ul style='list-style: none'>
	<li id='trim_data-from_start_or_end'>
		<b>from_start_or_end : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='trim_data-from_start_or_end-description'>Where to trim from. Accepts "start" or "end".</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='trim_data-duration'>
		<b>duration : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='trim_data-duration-description'>Duration to trim from dataframe. For more info on frequencies, see <code><https://pandas.pydata.org/pandas-docs/stable/user_guide/timeseries.html#offset-aliases></code>.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='trim_data-fmt'>
		<b>fmt : <i>str, default "%Y-%m-%d %H:%M:%S"</i></b>
		<ul style='list-style: none'>
			<li id='trim_data-fmt-description'>Datetime format of dataframe index.</li>
		</ul>
	</li>
</ul>

<hr>
