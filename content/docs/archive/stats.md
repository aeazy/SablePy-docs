## Stats

- [Parameters](#Stats)
- Methods:
  - [`run_ancova`](#run-ancova)
- Examples:

<strong id='Stats'>Stats</strong>(<b>data</b>, <b>groups</b>)

SablePy module providing a number of tools used in statistical analyses.

> Parameters

<ul style='list-style: none'>
	<li id='Stats-data'>
		<b>data : <i>sablepy.core.data.Data | pandas.core.frame.DataFrame</i></b>
		<ul style='list-style: none'>
			<li id='Stats-data-description'><code>sablepy.Data</code> or <code>pandas.DataFrame</code> object.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Stats-groups'>
		<b>groups : <i>list[sablepy.common.dataclasses.Group] | dict</i></b>
		<ul style='list-style: none'>
			<li id='Stats-groups-description'>List of <a href="../docs/dataclasses.md#group"><code>sablepy.Group</code></a> objects, or dict
                object where key is group name and value is a list of integers representing cage
                numbers.</li>
		</ul>
	</li>
</ul>

<hr>
<strong id='run-ancova'>run_ancova</strong>(<b>dependent_variable</b>, <b>covariate</b>, <b>groups</b>)

Analysis of covariance to control for the effects of extraneous factors that might influence the dependent measure of interest.

> Parameters

<ul style='list-style: none'>
	<li id='run_ancova-dependent_variable'>
		<b>dependent_variable : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='run_ancova-dependent_variable-description'>String expression representing the dependent variable.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='run_ancova-covariate'>
		<b>covariate : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='run_ancova-covariate-description'>String expression representing the co-dependent variable.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='run_ancova-groups'>
		<b>groups : <i>list[Group] | dict</i></b>
		<ul style='list-style: none'>
			<li id='run_ancova-groups-description'>List of <a href="../docs/dataclasses.md#group"><code>sablepy.Group</code></a> objects, or dict
                object where key is group name and value is a list of integers representing cage
                numbers. If <code>Stats.groups=None</code>, argument is required. Defaults to None.</li>
		</ul>
	</li>
</ul>

<hr>
