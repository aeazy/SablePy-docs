<strong id='read-xl'>read_xl</strong>(<b>file</b>, <b>sheet_name</b><i>=0</i>)

_summary_

> Parameters

<ul style='list-style: none'>
	<li id='read_xl-file'>
		<b>file : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='read_xl-file-description'>str or path object. A file-like object with a path to a .xlsx file.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='read_xl-sheet_name'>
		<b>sheet_name : <i>str | int | None, default 0</i></b>
		<ul style='list-style: none'>
			<li id='read_xl-sheet_name-description'>Strings are used for sheet names. Integers are used in zero-indexed sheet positions. If <code>sheet_names=None</code>, all sheets are parsed.</li>
		</ul>
	</li>
</ul>

<hr>

<strong id='combine-xl-sheets'>combine_xl_sheets</strong>(<b>files</b>, <b>sheet_name</b>, <b>export</b><i>=False</i>, <b>new_filename</b><i>=\_NoDefault.no_default</i>, <b>export_path</b><i>=\_NoDefault.no_default</i>)

Combine sheets from multiple Excel files.

> Parameters

<ul style='list-style: none'>
	<li id='combine_xl_sheets-files'>
		<b>files : <i>list[str  |  Path]</i></b>
		<ul style='list-style: none'>
			<li id='combine_xl_sheets-files-description'>List of str or path objects. A file-like object with a path to a .xlsx file.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='combine_xl_sheets-sheet_name'>
		<b>sheet_name : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='combine_xl_sheets-sheet_name-description'>String expression of sheet to combine.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='combine_xl_sheets-export'>
		<b>export : <i>bool, default False</i></b>
		<ul style='list-style: none'>
			<li id='combine_xl_sheets-export-description'>Export combined dataframe to an Excel file.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='combine_xl_sheets-new_filename'>
		<b>new_filename : <i>str, optional</i></b>
		<ul style='list-style: none'>
			<li id='combine_xl_sheets-new_filename-description'>String expression of the new Excel filename if <code>export=True</code>.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='combine_xl_sheets-export_path'>
		<b>export_path : <i>str | Path, optional</i></b>
		<ul style='list-style: none'>
			<li id='combine_xl_sheets-export_path-description'>Str or path object defining where to export the new Excel file if <code>export=True</code>.</li>
		</ul>
	</li>
</ul>

<hr>
