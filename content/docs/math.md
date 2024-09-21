# _sablepy.common.math_

- [cumsum](#cumsum)
- [average_by_circadian_cycle](#average-by-circadian-cycle)
- [calculate_cumulative_ee](#calculate-cumulative-ee)
- [calculate_energy_balance](#calculate-energy-balance)
- [calculate_cumulative_energy_balance](#calculate-cumulative-energy-balance)
- [calculate_group_averages](#calculate-group-averages)
- [calculate_hourly_intake](#calculate-hourly-intake)
- [correct_behavior_data](#correct-behavior-data)
- [cumsum_behavior_data](#cumsum-behavior-data)
- [get_circadian_cycle](#get-circadian-cycle)
- [inverse_cumsum](#inverse-cumsum)
- [remove_outliers](#remove-outliers)

<hr>

<strong id='average-by-circadian-cycle'>average_by_circadian_cycle</strong>(<b>df</b>, <b>light_start</b><i>=6</i>, <b>dark_start</b><i>=18</i>)

> Description

Bin data based on the time of day, as defined by `light_start` and `dark_start`. DataFrame returned is formatted for usage with `sablepy.BarPlot`.

> Parameters

<ul style='list-style: none'>
    <li>
        <b>df : <i>sablepy.core.data.Data | pandas.core.frame.DataFrame</i></b>
        <ul style='list-style: none'>
            <li>sablepy.Data or pandas.DataFrame.</li>
        </ul>
    </li>
    <li>
        <b>light_start : <i>int, default 6</i></b>
        <ul style='list-style: none'>
            <li>Integer representing the time at which lights turn on. <code>light_start=6</code> would be interpreted as lights turning on at 6 AM.</li>
        </ul>
    </li>
    <li>
        <b>dark_start : <i>int, default 18</i></b>
        <ul style='list-style: none'>
            <li>Integer representing the time at which lights turn off. <code>dark_start=18</code> would be interpreted as lights turning off at 6 PM.</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='calculate-cumulative-ee'>calculate_cumulative_ee</strong>(<b>df</b>, <b>ocm_version</b><i>="2.53.3+"</i>)

Calculate cumulative energy expenditure (kcal).

> Parameters

<ul style='list-style: none'>
	<li id='calculate_cumulative_ee-df'>
		<b>df : <i>Data | DataFrame</i></b>
		<ul style='list-style: none'>
			<li id='calculate_cumulative_ee-df-description'><code>sablepy.Data</code> or <code>pandas.DataFrame</code> object with kcal_hr data.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='calculate_cumulative_ee-ocm_version'>
		<b>ocm_version : <i>Literal["2.53.2", "2.53.3+"], default "2.53.3+"</i></b>
		<ul style='list-style: none'>
			<li id='calculate_cumulative_ee-ocm_version-description'>String expression representing OCM version used to obtain kcal_hr data.</li>
		</ul>
	</li>
</ul>

<hr>
<strong id='calculate-energy-balance'>calculate_energy_balance</strong>(<b>df</b>, <b>diet</b><i>=3.56</i>)

> Description

Calculates the energy balance for each column provided. `df` must contain energy expenditure and food intake channels. Optionally, provide the energy value of the mice diet to calculate accordingly.

> Parameters

<ul style='list-style: none'>
    <li>
        <b>df : <i>sablepy.core.data.Data | pandas.core.frame.DataFrame</i></b>
        <ul style='list-style: none'>
            <li>sablepy.Data or pandas.DataFrame containing food intake and energy expenditure data.</li>
        </ul>
    </li>
    <li>
        <b>diet : <i>float, default 3.56</i></b>
        <ul style='list-style: none'>
            <li>Energy value of diet in kcal/g. Defaults to LabDiet 5008 (3.56kcal/g).</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='calculate-cumulative-energy-balance'>calculate_cumulative_energy_balance</strong>(<b>df</b>, <b>diet</b><i>=3.56</i>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>df : <i>sablepy.core.data.Data | pandas.core.frame.DataFrame</i></b>
        <ul style='list-style: none'>
            <li>sablepy.Data or pandas.DataFrame containing food intake and energy expenditure data.</li>
        </ul>
    </li>
    <li>
        <b>diet : <i>float, default 3.56</i></b>
        <ul style='list-style: none'>
            <li>Energy value of diet in kcal/g. Defaults to LabDiet 5008 (3.56kcal/g).</li>
        </ul>
    </li>
</ul>

<strong id='calculate-group-averages'>calculate_group_averages</strong>(<b>df</b>, <b>groups</b>)

> Description

Calculates group averages of metabolic data. If more than one variable is detected in the dataframe provided, each variable will be averaged (e.g., 'vo2','vco2', etc.).

> Parameters

<ul style='list-style: none'>
    <li>
        <b>df : <i>sablepy.core.data.Data | pandas.core.frame.DataFrame</i></b>
        <ul style='list-style: none'>
            <li>sablepy.Data or pandas.DataFrame containing metabolic data.</li>
        </ul>
    </li>
    <li>
        <b>groups : <i>list[sablepy.common.dataclasses.Group]</i></b>
        <ul style='list-style: none'>
            <li>Expects a list of <code>sablepy.Group</code> objects. See the <a href="https://github.com/aeazy/SablePy/blob/main/sablepy/content/docs/dataclasses.md#group">Group documentation</a> for more information.</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='calculate-hourly-intake'>calculate_hourly_intake</strong>(<b>df</b>, <b>food_or_water</b><i>='both'</i>)

> Description

Calculates the food or water consumption data on an hour-to-hour basis.

> Parameters

<ul style='list-style: none'>
    <li>
        <b>df : <i>pandas.core.frame.DataFrame</i></b>
        <ul style='list-style: none'>
            <li>pandas.DataFrame containing food or water intake data.</li>
        </ul>
    </li>
    <li>
        <b>food_or_water : <i>str, default 'both'</i></b>
        <ul style='list-style: none'>
            <li>Calculate hourly consumption for food or water. If <code>food_or_water='both'</code>, hourly channels will be calculated for food and water consumption channels.</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='correct-behavior-data'>correct_behavior_data</strong>(<b>df</b>)

> Description

Used by `sablepy.Combine` when combining multiple csv files where behavior data for each file is cumulatively summed.

> Parameters

<ul style='list-style: none'>
    <li>
        <b>df : <i>sablepy.core.data.Data | pandas.core.frame.DataFrame</i></b>
        <ul style='list-style: none'>
            <li>sablepy.Data or pandas.DataFrame</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='cumsum'>cumsum</strong>(<b>data</b>)

> Description

Cumulative sum of a column on the nth axis.

> Parameters

<ul style='list-style: none'>
    <li>
        <b>data : <i>sablepy.core.data.Data | pandas.core.frame.DataFrame</i></b>
        <ul style='list-style: none'>
            <li>sablepy.core.data.Data | pandas.core.frame.DataFrame</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='cumsum-behavior-data'>cumsum_behavior_data</strong>(<b>df</b>)

> Description

Used by `sablepy.Combine` after the cumulative difference is found using [`correct_behavior_data`](#correct-behavior-data), files are combined, and the behavior data must be cumulatively summed once more.

> Parameters

<ul style='list-style: none'>
    <li>
        <b>df : <i>sablepy.core.data.Data | pandas.core.frame.DataFrame</i></b>
        <ul style='list-style: none'>
            <li>sablepy.Data or pandas.DataFrame</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='get-circadian-cycle'>get_circadian_cycle</strong>(<b>df</b>, <b>light_or_dark</b><i>=\_NoDefault.no_default</i>, <b>start_hr</b><i>=\_NoDefault.no_default</i>, <b>end_hr</b><i>=\_NoDefault.no_default</i>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>df : <i>sablepy.core.data.Data | pandas.core.frame.DataFrame</i></b>
        <ul style='list-style: none'>
            <li>sablepy.Data or pandas.DataFrame object where index dtype is in datetime format.</li>
        </ul>
    </li>
    <li>
        <b>light_or_dark : <i>str, optional</i></b>
        <ul style='list-style: none'>
            <li>String expression defining if the circadian cycle is 'light' or 'dark'.</li>
        </ul>
    </li>
    <li>
        <b>start_hr : <i>int, optional</i></b>
        <ul style='list-style: none'>
            <li>Integer representation of cycle start in 24-hr format (e.g., <code>start_hr=6</code> is 6:00 AM).</li>
        </ul>
    </li>
    <li>
        <b>end_hr : <i>int, optional</i></b>
        <ul style='list-style: none'>
            <li>Integer representation of cycle end in 24-hr format (e.g., <code>end_hr=18</code> is 6:00 PM).</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='inverse-cumsum'>inverse_cumsum</strong>(<b>data</b>)

> Description

Calculates the difference between two points (diff = a[i+1] - a[i]). Useful for undoing channels previously cumulatively summed.

> Parameters

<ul style='list-style: none'>
    <li>
        <b>data : <i>sablepy.core.data.Data | pandas.core.frame.DataFrame | pandas.core.series.Series</i></b>
        <ul style='list-style: none'>
            <li>sablepy.Data, pandas.DataFrame or pandas.Series object.</li>
        </ul>
    </li>
</ul>

<hr>

<strong id='remove-outliers'>remove_outliers</strong>(<b>df</b>, <b>lower_bound</b><i>=0.01</i>, <b>upper_bound</b><i>=0.99</i>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>df : <i>sablepy.core.data.Data | pandas.core.frame.DataFrame</i></b>
        <ul style='list-style: none'>
            <li>sablepy.Data or pandas.DataFrame.</li>
        </ul>
    </li>
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
