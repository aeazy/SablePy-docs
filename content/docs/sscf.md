# sablepy.SSCF

The `sablepy.SSCF` module provides `.exp` file support for Sable Systems' data
acquisition systems.

It includes a `Reader` class that allows users to read and
parse SSCF files, extracting metadata and data in a structured format (see
[Reader](#Reader)). It also includes a `Writer` class for creating SSCF files
from pandas DataFrames (see [Writer](#Writer)). The `ExpFile` class provides a
easy interface for reading SSCF files, allowing users to access data and
metadata without needing to directly interact with the `Reader` class (see [ExpFile](#ExpFile)).

#### Table of Contents

- [Usage](#Usage)
- [ExpFile](#ExpFile)
- [Reader](#Reader)
- [Writer](#Writer)

## Usage

Using context manager to read an SSCF EXP file:

```python
from sscf import ExpFile

with ExpFile(file="example.exp") as exp_file:
    data = exp_file.data
    version = exp_file.version
    channel_count = exp_file.channel_count
    sample_count = exp_file.sample_count
    sample_interval = exp_file.sample_interval
```

Or using the class directly:

```python
from sscf import ExpFile

exp_file = ExpFile(file="example.exp")
data = exp_file.data

print(data.head())

                          O2_A     CO2_A  ...  CommMS  ElSeconds
Date_Time_1                               ...
2025-05-01 00:00:00  19.586468  0.128644  ...    74.0   0.075925
2025-05-01 00:00:01  19.586531  0.120446  ...   112.0   1.114281
2025-05-01 00:00:02  19.587494  0.115201  ...    87.0   2.090176
2025-05-01 00:00:03  19.593752  0.107807  ...   102.0   3.105359
2025-05-01 00:00:04  19.604551  0.100145  ...   135.0   4.137529
```

<hr>
<strong id='ExpFile'>ExpFile</strong>(<b>file</b><i>=\_NoDefault.no_default</i>, <b>filepath</b><i>=\_NoDefault.no_default</i>)

Class for reading SSCF EXP files. This class inherits from Reader and provides methods to read and process data easily.

> Parameters

<ul style='list-style: none'>
	<li id='ExpFile-file'>
		<b>file : <i>StrPathType</i></b>
		<ul style='list-style: none'>
			<li id='ExpFile-file-description'>Path to the SSCF EXP file.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='ExpFile-filepath'>
		<b>filepath : <i>Optional[StrPathType]</i></b>
		<ul style='list-style: none'>
			<li id='ExpFile-filepath-description'>Optional path for the file. Defaults</li>
		</ul>
	</li>
</ul>

<hr>
<strong id='Reader'>Reader</strong>(<b>file</b><i>=_NoDefault.no_default</i>, <b>filepath</b><i>=_NoDefault.no_default</i>)

Reader class to read and parse SSCF files.

> Parameters

<ul style='list-style: none'>
	<li id='Reader-file'>
		<b>file : <i>Optional[StrPathType]</i></b>
		<ul style='list-style: none'>
			<li id='Reader-file-description'>Path to the file to read. This can be
            a string or a Path object. If provided, it will be used to read
            the file. If None, `path` will be used instead. If both are
            provided, `file` will be added to `path` to form a complete
            path. Defaults to None.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Reader-filepath'>
		<b>filepath : <i>Optional[StrPathType]</i></b>
		<ul style='list-style: none'>
			<li id='Reader-filepath-description'>An optional path to a directory or file.
            This can be a string or a Path object. Defaults to None.</li>
		</ul>
	</li>
</ul>

> Attributes

<ul style='list-style: none'>
	<li id='Reader-file'>
		<b>file : <i>Path</i></b>
		<ul style='list-style: none'>
			<li id='Reader-file-description'>The Path to the file being read.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Reader-version'>
		<b>version : <i>Optional[float]</i></b>
		<ul style='list-style: none'>
			<li id='Reader-version-description'>Version of the SSCF file format.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Reader-channel_count'>
		<b>channel_count : <i>Optional[int]</i></b>
		<ul style='list-style: none'>
			<li id='Reader-channel_count-description'>Number of channels in the SSCF file.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Reader-sample_count'>
		<b>sample_count : <i>Optional[int]</i></b>
		<ul style='list-style: none'>
			<li id='Reader-sample_count-description'>Number of samples in the SSCF file.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Reader-sample_interval'>
		<b>sample_interval : <i>Optional[float]</i></b>
		<ul style='list-style: none'>
			<li id='Reader-sample_interval-description'>Interval between samples in seconds.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Reader-data'>
		<b>data : <i>DataFrame</i></b>
		<ul style='list-style: none'>
			<li id='Reader-data-description'>Data read from the SSCF file.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Reader-end_date'>
		<b>end_date : <i>datetime</i></b>
		<ul style='list-style: none'>
			<li id='Reader-end_date-description'>End date of the recording.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Reader-remarks'>
		<b>remarks : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='Reader-remarks-description'>Remarks associated with the SSCF file.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Reader-markers'>
		<b>markers : <i>DataFrame</i></b>
		<ul style='list-style: none'>
			<li id='Reader-markers-description'>Markers in the SSCF file.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Reader-note_markers'>
		<b>note_markers : <i>list[str]</i></b>
		<ul style='list-style: none'>
			<li id='Reader-note_markers-description'>Note markers in the SSCF file.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Reader-channel_info'>
		<b>channel_info : <i>list[dict]</i></b>
		<ul style='list-style: none'>
			<li id='Reader-channel_info-description'>Information about each channel.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Reader-extended_remarks'>
		<b>extended_remarks : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='Reader-extended_remarks-description'>Extended remarks for the SSCF file.</li>
		</ul>
	</li>
</ul>

> Example Usage

```python
from sscf import Reader

reader = Reader(file="example.exp")
print(reader.file_type)
# Output:
1003.0
```

<hr>

<strong id='Writer'>Writer</strong>(<b>sscf</b><i>=\_NoDefault.no_default</i>, <b>new_filename</b><i>=\_NoDefault.no_default</i>, <b>export_path</b><i>=\_NoDefault.no_default</i>)

A class to write SSCF files. This class takes an SSCF Reader object and writes the SSCF data to a file in the SSCF format. It handles the creation of the file header, data, and footer, ensuring that the file is correctly formatted to be read by MacroInterpreter.

> Parameters

<ul style='list-style: none'>
	<li id='Writer-sscf'>
		<b>sscf : <i>Reader</i></b>
		<ul style='list-style: none'>
			<li id='Writer-sscf-description'>An instance of the SSCF Reader class containing the
            data to be written.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Writer-new_filename'>
		<b>new_filename : <i>Optional[StrPathType]</i></b>
		<ul style='list-style: none'>
			<li id='Writer-new_filename-description'>The name of the file to be created.
            If not provided, a default filename based on the current date will be used.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Writer-export_path'>
		<b>export_path : <i>Optional[StrPathType]</i></b>
		<ul style='list-style: none'>
			<li id='Writer-export_path-description'>The path where the file will be saved.
            If not provided, it defaults to the current working directory.
</li>
		</ul>
	</li>
</ul>

> Example Usage

```python
from sscf import Reader, Writer

reader = Reader(file="example.exp")
writer = Writer(sscf=reader, new_filename="output.exp")
writer.write()
# Output:
File written successfully to '~/output.exp'
```
