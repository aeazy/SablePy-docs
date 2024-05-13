## sablepy.Data

- [sablepy.Data](#sablepydata)
  - [sablepy.average_by_group](#sablepyaverage_by_group)
  - [sablepy.exclude_cages](#sablepyexclude_cages)
  - [sablepy.extract_time_period](#sablepyextract_time_period)
  - [sablepy.get_channel_data](#sablepyget_channel_data)
  - [sablepy.remove_outliers](#sablepyremove_outliers)
  - [sablepy.resample_data](#sablepyresample_data)
  - [sablepy.trim_data](#sablepytrim_data)

<strong id='data'>Data</strong>(<b>file</b><i>=\_NoDefault.no_default</i>, <b>data</b><i>=\_NoDefault.no_default</i>, <b>data_type</b><i>='individual'</i>, <b>folder</b><i>=\_NoDefault.no_default</i>, <b>filepath</b><i>=\_NoDefault.no_default</i>, <b>abs_path</b><i>=\_NoDefault.no_default</i>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>file : <i>str, optional</i></b>
        <ul style='list-style: none'>
            <li>String expression of csv file name.</li>
        </ul>
    </li>
    <li>
        <b>data : <i>pandas.core.frame.DataFrame, optional</i></b>
        <ul style='list-style: none'>
            <li>If <code>file=None</code>, a pandas.DataFrame can be used to create a Data object.</li>
        </ul>
    </li>
    <li>
        <b>data_type : <i>str, default 'individual'</i></b>
        <ul style='list-style: none'>
            <li>String expression of how they data is assembled, which is used to determine how the columns are labelled. If <code>data_type='individual'</code>, the column titles are expected to be the {variable}_{cage_num}. If <code>data_type='group'</code>, the column titles are expected to be the {variable}_{group_name}.</li>
        </ul>
    </li>
    <li>
        <b>folder : <i>str, optional</i></b>
        <ul style='list-style: none'>
            <li>String expression of folder where csv file is located in the <code>~/uploads</code> directory.</li>
        </ul>
    </li>
    <li>
        <b>filepath : <i>pathlib.Path | str, optional</i></b>
        <ul style='list-style: none'>
            <li>Relative path to <code>~/uploads</code> directory.</li>
        </ul>
    </li>
    <li>
        <b>abs_path : <i>pathlib.Path, optional</i></b>
        <ul style='list-style: none'>
            <li>Absolute path to the csv file.</li>
        </ul>
    </li>
</ul>

<ul style='list-style: none'>
    <li>
        <b>file : <i>str, optional</i></b>
        <ul style='list-style: none'>
            <li></li>
        </ul>
    </li>
    <li>
        <b>data : <i>pandas.core.frame.DataFrame, optional</i></b>
        <ul style='list-style: none'>
            <li>If <code>file=None</code>, a pandas.DataFrame can be used to create a Data object.</li>
        </ul>
    </li>
    <li>
        <b>data_type : <i>str, default 'individual'</i></b>
        <ul style='list-style: none'>
        </ul>
    </li>
</ul>

> Example

```
>>> data = Data('example.csv')
>>> data
           Date_Time_1  DurationMin_1  envirolightlux_1  envirolightlux_9  envirotemp_1
0  01/26/2024 11:55:38           60.0               3.0               3.0      22.24046
1  01/26/2024 12:55:38           60.0               3.0               3.0      22.23638
2  01/26/2024 13:55:38           60.0               3.0               3.0      22.21927
3  01/26/2024 14:55:38           60.0               3.0               3.0      22.22563
4  01/26/2024 15:55:38           60.0               3.0               3.0      22.23536
```

<hr>

### sablepy.average_by_group

<strong id='average-by-group'>average_by_group</strong>(<b>groups</b><i>=\_NoDefault.no_default</i>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>groups : <i>list[sablepy.common.dataclasses.Group], optional</i></b>
        <ul style='list-style: none'>
            <li>The <code>groups</code> argument expects a list of <code>Group</code> objects. See the <a href="https://github.com/aeazy/SablePy/blob/main/sablepy/content/docs/dataclasses.md#group">Group documentation</a> for more information</li>
        </ul>
    </li>
</ul>

> Example

```
>>> vo2_df
      vo2_1     vo2_2     vo2_3     vo2_4     vo2_5
0  2.838440  2.019207  2.742513  2.374455  2.607097
1  2.362644  1.959659  2.455035  2.320123  2.122715
2  2.147651  1.709375  2.079620  2.229678  1.964711
3  1.837459  1.173334  1.901298  1.956764  1.747900
4  1.886103  1.558226  1.830415  1.720444  1.770472

>>> vo2_df.average_by_group([Group('Control', [1,2]), Group('KO', [3,4,5])])
   vo2_Control    vo2_KO
0     2.428824  2.574688
1     2.161151  2.299291
2     1.928513  2.091336
3     1.505397  1.868654
4     1.722165  1.773777
```

<hr>

### sablepy.exclude_cages

<strong id='exclude-cages'>exclude_cages</strong>(<b>cage_nums</b>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>cage_nums : <i>list[int]</i></b>
        <ul style='list-style: none'>
            <li>Integer list of integers representing cage numbers to exclude.</li>
        </ul>
    </li>
</ul>

> Example

```
>>> vo2_df.exclude_cages([1,3])
      vo2_2     vo2_4     vo2_5     vo2_6     vo2_7
0  2.019207  2.374455  2.607097  2.536016  2.800204
1  1.959659  2.320123  2.122715  2.262234  2.548898
2  1.709375  2.229678  1.964711  2.100774  2.328478
3  1.173334  1.956764  1.747900  1.666257  2.309311
4  1.558226  1.720444  1.770472  1.750869  1.715556
```

<hr>

### sablepy.extract_time_period

<strong id='extract-time-period'>extract_time_period</strong>(<b>start_datetime</b><i>=\_NoDefault.no_default</i>, <b>end_datetime</b><i>=\_NoDefault.no_default</i>, <b>fmt</b><i>='%Y-%m-%d %H:%M:%S'</i>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>start_datetime : <i>str, optional</i></b>
        <ul style='list-style: none'>
            <li>String expression of new start datetime for the dataset. Default format expects datetime string <code>'%Y-%m-%d %H:%M:%S'</code>, with fallback format expecting <code>'%Y-%m-%d'</code>.</li>
        </ul>
    </li>
    <li>
        <b>end_datetime : <i>str, optional</i></b>
        <ul style='list-style: none'>
            <li>String expression of new end datetime for the dataset. Default format expects datetime string <code>'%Y-%m-%d %H:%M:%S'</code>, with fallback format expecting <code>'%Y-%m-%d'</code>.</li>        
        </ul>
    </li>
    <li>
        <b>fmt : <i>str, default '%Y-%m-%d %H:%M:%S'</i></b>
        <ul style='list-style: none'>
            <li>Default expected format for argument provided to <code>start_datetime</code> or <code>end_datetime</code>.</li>
        </ul>
    </li>
</ul>

> Example

```
>>> vo2_df.extract_time_period("2024-01-26 11:55:38", "2024-01-26 13:55:38")
                        vo2_1     vo2_2     vo2_3     vo2_4     vo2_5
Date_Time_1
2024-01-26 11:55:38  2.838440  2.019207  2.742513  2.374455  2.607097
2024-01-26 12:55:38  2.362644  1.959659  2.455035  2.320123  2.122715
2024-01-26 13:55:38  2.147651  1.709375  2.079620  2.229678  1.964711
2024-01-26 14:55:38  1.837459  1.173334  1.901298  1.956764  1.747900
2024-01-26 15:55:38  1.886103  1.558226  1.830415  1.720444  1.770472

>>> vo2_df.extract_time_period("2024-01-26 11:55:38", "2024-01-26 13:55:38")
                        vo2_1     vo2_2     vo2_3     vo2_4     vo2_5
Date_Time_1
2024-01-26 11:55:38  2.838440  2.019207  2.742513  2.374455  2.607097
2024-01-26 12:55:38  2.362644  1.959659  2.455035  2.320123  2.122715
2024-01-26 13:55:38  2.147651  1.709375  2.079620  2.229678  1.964711
```

<hr>

### sablepy.get_channel_data

<strong id='get-channel-data'>get_channel_data</strong>(<b>channel</b>, <b>average_by_group</b><i>=False</i>, <b>groups</b><i>=\_NoDefault.no_default</i>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>channel : <i>str</i></b>
        <ul style='list-style: none'>
            <li>String expression of the desired channel (e.g., 'vo2', 'rq').</li>
        </ul>
    </li>
    <li>
        <b>average_by_group : <i>bool, default False</i></b>
        <ul style='list-style: none'>
            <li>Average the desired channel by group. Requires an argument to be provided for <code>groups</code>.</li>
        </ul>
    </li>
    <li>
        <b>groups : <i>dict[str, list[int]], optional</i></b>
        <ul style='list-style: none'>
            <li>Dictionary where the key is the group name and the value is a list of integers representing the cages in the group.</li>
        </ul>
    </li>
</ul>

> Example

```
>>> df.get_channel_data('vo2')
      vo2_1     vo2_2     vo2_3     vo2_4     vo2_5
0  2.838440  2.019207  2.742513  2.374455  2.607097
1  2.362644  1.959659  2.455035  2.320123  2.122715
2  2.147651  1.709375  2.079620  2.229678  1.964711
3  1.837459  1.173334  1.901298  1.956764  1.747900
4  1.886103  1.558226  1.830415  1.720444  1.770472
```

<hr>

### sablepy.remove_outliers

<strong id='remove-outliers'>remove_outliers</strong>(<b>lower_bound</b><i>=0.01</i>, <b>upper_bound</b><i>=0.99</i>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>lower_bound : <i>float, default 0.01</i></b>
        <ul style='list-style: none'>
            <li>Float value defining the lower bound.</li>
        </ul>
    </li>
    <li>
        <b>upper_bound : <i>float, default 0.99</i></b>
        <ul style='list-style: none'>
            <li>Float value defining the upper bound.</li>
        </ul>
    </li>
</ul>

> Example

```
>>> vo2_df
                        vo2_1     vo2_2     vo2_3     vo2_4     vo2_5
Date_Time_1
2024-01-26 11:55:38  2.838440  2.019207  2.742513  2.374455  2.607097
2024-01-26 12:55:38  20.62644  1.959659  2.455035  2.320123  2.122715
2024-01-26 13:55:38  2.147651  1.709375  2.079620  2.229678  1.964711
2024-01-26 14:55:38  1.837459  1.173334  1.901298  1.956764  1.747900
2024-01-26 15:55:38  1.886103  1.558226  1.830415  1.720444  0.070472


>>> vo2_df.remove_outliers()
                        vo2_1     vo2_2     vo2_3     vo2_4     vo2_5
Date_Time_1
2024-01-26 11:55:38  2.838440  2.019207  2.742513  2.374455  2.607097
2024-01-26 12:55:38  2.362644  1.959659  2.455035  2.320123  2.122715
2024-01-26 13:55:38  2.147651  1.709375  2.079620  2.229678  1.964711
2024-01-26 14:55:38  1.837459  1.173334  1.901298  1.956764  1.747900
2024-01-26 15:55:38  1.886103  1.558226  1.830415  1.720444  1.770472
```

<hr>

### sablepy.resample_data

<strong id='resample-data'>resample_data</strong>(<b>frequency</b>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>frequency : <i>str</i></b>
        <ul style='list-style: none'>
            <li>String expression representing the frequency at which to resample the data.</li>
        </ul>
    </li>
</ul>

```
>>> vo2_df
                        vo2_1     vo2_2     vo2_3     vo2_4     vo2_5
Date_Time_1
2024-01-26 11:55:38  2.838440  2.019207  2.742513  2.374455  2.607097
2024-01-26 12:55:38  2.362644  1.959659  2.455035  2.320123  2.122715
2024-01-26 13:55:38  2.147651  1.709375  2.079620  2.229678  1.964711
2024-01-26 14:55:38  1.837459  1.173334  1.901298  1.956764  1.747900
2024-01-26 15:55:38  1.886103  1.558226  1.830415  1.720444  1.770472

>>> vo2_df.resample_data(frequency='3h')
                        vo2_1     vo2_2     vo2_3     vo2_4     vo2_5
Date_Time_1
2024-01-26 09:00:00  2.838440  2.019207  2.742513  2.374455  2.607097
2024-01-26 12:00:00  2.115918  1.614123  2.145318  2.168855  1.945109
2024-01-26 15:00:00  1.809171  1.460883  1.735692  1.818705  1.853890
2024-01-26 18:00:00  2.012067  2.014886  2.365785  1.959453  2.378953
2024-01-26 21:00:00  1.987108  1.937156  2.049643  1.729326  2.062832
```

<hr>

### sablepy.trim_data

<strong id='trim-data'>trim_data</strong>(<b>from_start_or_end</b>, <b>duration</b>, <b>fmt</b><i>='%Y-%m-%d %H:%M:%S'</i>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>from_start_or_end : <i>str</i></b>
        <ul style='list-style: none'>
            <li>Defines whether the data is removed from the start or the end of the experiment.</li>
        </ul>
    </li>
    <li>
        <b>duration : <i>str</i></b>
        <ul style='list-style: none'>
            <li>String expression representing how much time to trim from the start or the end of the experiment as defined by <code>from_start_or_end</code>.</li>
        </ul>
    </li>
    <li>
        <b>fmt : <i>str, default '%Y-%m-%d %H:%M:%S'</i></b>
        <ul style='list-style: none'>
            <li>Format of the datetime index.</li>
        </ul>
    </li>
</ul>

> Example

```
>>> vo2_df
                        vo2_1     vo2_2     vo2_3     vo2_4     vo2_5
Date_Time_1
2024-01-26 11:55:38  2.838440  2.019207  2.742513  2.374455  2.607097
2024-01-26 12:55:38  2.362644  1.959659  2.455035  2.320123  2.122715
2024-01-26 13:55:38  2.147651  1.709375  2.079620  2.229678  1.964711
2024-01-26 14:55:38  1.837459  1.173334  1.901298  1.956764  1.747900
2024-01-26 15:55:38  1.886103  1.558226  1.830415  1.720444  1.770472

>>> vo2_df.trim_data('start', '10h)
                        vo2_1     vo2_2     vo2_3     vo2_4     vo2_5
Date_Time_1
2024-01-26 21:55:38  2.135507  1.984336  2.367642  1.700436  2.248540
2024-01-26 22:55:38  1.759350  1.823996  2.447186  1.788185  1.827463
2024-01-26 23:55:38  2.066468  2.003137  1.334100  1.699358  2.112494
2024-01-27 00:55:38  2.246784  2.095919  1.853705  2.061225  2.486582
2024-01-27 01:55:38  1.563503  1.152611  1.878085  1.884731  2.250573

```
