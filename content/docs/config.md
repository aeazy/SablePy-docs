## SablePy Config

- [Config](#config)
- [DataConfig](#dataconfig)

<strong id='Config'>Config</strong>(<b>data</b>, <b>plotting</b>)

Class to represent the configuration of SablePy.

> Parameters

<ul style='list-style: none'>
	<li id='Config-data'>
		<b>data : <i>DataConfig</i></b>
		<ul style='list-style: none'>
			<li id='Config-data-description'>Configuration for data handling. See <a href="#dataconfig">DataConfig</a>.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='Config-plotting'>
		<b>plotting : <i>PlotConfig</i></b>
		<ul style='list-style: none'>
			<li id='Config-plotting-description'>Configuration for plotting. See <a href="#plotconfig">PlotConfig</a>.</li>
		</ul>
	</li>
</ul>

<hr>

<strong id='DataConfig'>DataConfig</strong>(<b>debug</b>, <b>light_start</b><i>=6</i>, <b>dark_start</b><i>=18</i>)

Class to represent the configuration of SablePy data handling.

> Parameters

<ul style='list-style: none'>
	<li id='DataConfig-debug'>
		<b>debug : <i>bool</i></b>
		<ul style='list-style: none'>
			<li id='DataConfig-debug-description'>If True, enable debug mode. If False, disable it. Defaults</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='DataConfig-light_start'>
		<b>light_start : <i>int, default 6</i></b>
		<ul style='list-style: none'>
			<li id='DataConfig-light_start-description'>Hour of the day when light starts.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='DataConfig-dark_start'>
		<b>dark_start : <i>int, default 18</i></b>
		<ul style='list-style: none'>
			<li id='DataConfig-dark_start-description'>Hour of the day when dark starts.</li>
		</ul>
	</li>
</ul>

<hr>
<strong id='PlotConfig'>PlotConfig</strong>(<b>layout</b>, <b>legend</b>, <b>title</b>, <b>xaxis</b>, <b>yaxis</b>)

Class to represent the configuration of SablePy plotting.

> Parameters

<ul style='list-style: none'>
	<li id='PlotConfig-layout'>
		<b>layout : <i>Layout</i></b>
		<ul style='list-style: none'>
			<li id='PlotConfig-layout-description'>Configuration for the plot
			layout. See <a href='https://github.com/aeazy/SablePy-docs/blob/main/content/docs/plotting/attributes.md#layout'>Layout</a>.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='PlotConfig-legend'>
		<b>legend : <i>Legend</i></b>
		<ul style='list-style: none'>
			<li id='PlotConfig-legend-description'>Configuration for the plot
			legend. See <a href='https://github.com/aeazy/SablePy-docs/blob/main/content/docs/plotting/attributes.md#legend'>Legend</a>.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='PlotConfig-title'>
		<b>title : <i>Title</i></b>
		<ul style='list-style: none'>
			<li id='PlotConfig-title-description'>Configuration for the plot
			title. See <a href='https://github.com/aeazy/SablePy-docs/blob/main/content/docs/plotting/attributes.md#title'>Title</a>.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='PlotConfig-xaxis'>
		<b>xaxis : <i>Axis</i></b>
		<ul style='list-style: none'>
			<li id='PlotConfig-xaxis-description'>Configuration for the x-axis.
			See <a href='https://github.com/aeazy/SablePy-docs/blob/main/content/docs/plotting/attributes.md#axis'>Axis</a>.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='PlotConfig-yaxis'>
		<b>yaxis : <i>Axis</i></b>
		<ul style='list-style: none'>
			<li id='PlotConfig-yaxis-description'>Configuration for the y-axis.
			See <a href='https://github.com/aeazy/SablePy-docs/blob/main/content/docs/plotting/attributes.md#axis'>Axis</a>.</li>
		</ul>
	</li>
</ul>

<hr>
