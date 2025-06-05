## sablepy.Annotations

- [`add_annotation`](#add-annotation)
- [`add_hline`](#add-hline)
- [`add_vline`](#add-vline)

<strong id='add-annotation'>add_annotation</strong>(<b>text</b>, <b>x</b>, <b>y</b><i>=1</i>, <b>xref</b><i>='x'</i>, <b>yref</b><i>="paper"</i>, <b>showarrow</b><i>=True</i>, <b>xshift</b><i>=\_NoDefault.no_default</i>, <b>yshift</b><i>=\_NoDefault.no_default</i>, <b>textcolor</b><i>=\_NoDefault.no_default</i>, <b>arrowcolor</b><i>=\_NoDefault.no_default</i>)

Add a text annotation to a plot.

> Parameters

<ul style='list-style: none'>
	<li id='add_annotation-text'>
		<b>text : <i>str</i></b>
		<ul style='list-style: none'>
			<li id='add_annotation-text-description'>Annotation text.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_annotation-x'>
		<b>x : <i>str | int</i></b>
		<ul style='list-style: none'>
			<li id='add_annotation-x-description'>Annotation's x position. X position can be defined as a string expression matching the x-axis label or as an integer representing the hour or day.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_annotation-y'>
		<b>y : <i>str | int, default 1</i></b>
		<ul style='list-style: none'>
			<li id='add_annotation-y-description'>Annotation's y postion. If yref='y', the annotation is placed in the plot at the specified y value.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_annotation-xref'>
		<b>xref : <i>str, default 'x'</i></b>
		<ul style='list-style: none'>
			<li id='add_annotation-xref-description'>Distance from left of the plotting area to place the annotation. If xref='paper', and x=0.5, the annotation would be placed in the center of the page.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_annotation-yref'>
		<b>yref : <i>str, default "paper"</i></b>
		<ul style='list-style: none'>
			<li id='add_annotation-yref-description'>Distance from the bottom of the plotting area to place the annotation. If yref='y', the annotation is placed in the plot space at the point determined by 'ypos'.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_annotation-showarrow'>
		<b>showarrow : <i>bool, default True</i></b>
		<ul style='list-style: none'>
			<li id='add_annotation-showarrow-description'>Whether a line points to the position given by 'x' and 'y'.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_annotation-xshift'>
		<b>xshift : <i>int, optional</i></b>
		<ul style='list-style: none'>
			<li id='add_annotation-xshift-description'>Horizontal offset applied to annotation label.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_annotation-yshift'>
		<b>yshift : <i>int, optional</i></b>
		<ul style='list-style: none'>
			<li id='add_annotation-yshift-description'>Vertical offset applied to annotation label.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_annotation-textcolor'>
		<b>textcolor : <i>str, optional</i></b>
		<ul style='list-style: none'>
			<li id='add_annotation-textcolor-description'>String expression of annotation text color.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_annotation-arrowcolor'>
		<b>arrowcolor : <i>str, optional</i></b>
		<ul style='list-style: none'>
			<li id='add_annotation-arrowcolor-description'>String expression of annotation arrow color.</li>
		</ul>
	</li>
</ul>

<hr>

<strong id='add-vline'>add_vline</strong>(<b>x</b>, <b>line_color</b><i>='black'</i>, <b>line_dash</b><i>='solid'</i>, <b>line_opacity</b><i>=1.0</i>, <b>line_width</b><i>=1</i>, <b>textcolor</b><i>=\_NoDefault.no_default</i>)

Add a vertical line to a plot.

> Parameters

<ul style='list-style: none'>
	<li id='add_vline-x'>
		<b>x : <i>str | int</i></b>
		<ul style='list-style: none'>
			<li id='add_vline-x-description'>Annotation's x position. X position can be defined as a string expression matching the x-axis label or as an integer representing the hour or day.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_vline-line_color'>
		<b>line_color : <i>str, default 'black'</i></b>
		<ul style='list-style: none'>
			<li id='add_vline-line_color-description'>String expression of color.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_vline-line_dash'>
		<b>line_dash : <i>str, default 'solid'</i></b>
		<ul style='list-style: none'>
			<li id='add_vline-line_dash-description'>String expression of line dash style. Arguments include 'solid', 'dash', or 'dashdot'.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_vline-line_opacity'>
		<b>line_opacity : <i>float, default 1.0</i></b>
		<ul style='list-style: none'>
			<li id='add_vline-line_opacity-description'>Float representation of line opacity.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_vline-line_width'>
		<b>line_width : <i>int | float, default 1</i></b>
		<ul style='list-style: none'>
			<li id='add_vline-line_width-description'>Integer or float representation of line width.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_vline-textcolor'>
		<b>textcolor : <i>str, optional</i></b>
		<ul style='list-style: none'>
			<li id='add_vline-textcolor-description'>String expression of annotation label color.</li>
		</ul>
	</li>
</ul>

<hr>

<strong id='add-hline'>add_hline</strong>(<b>x</b><i>=0.0</i>, <b>y</b>, <b>label</b><i>=\_NoDefault.no_default</i>, <b>align_label</b><i>=\_NoDefault.no_default</i>, <b>line_color</b><i>='black'</i>, <b>line_dash</b><i>='solid'</i>, <b>line_opacity</b><i>=1.0</i>, <b>line_width</b><i>=1</i>, <b>showarrow</b><i>=False</i>, <b>xshift</b><i>=0</i>, <b>yshift</b><i>=10</i>, <b>textcolor</b><i>=\_NoDefault.no_default</i>)

Add a horizontal line to a plot.

> Parameters

<ul style='list-style: none'>
	<li id='add_hline-x'>
		<b>x : <i>float | int, default 0.0</i></b>
		<ul style='list-style: none'>
			<li id='add_hline-x-description'>Integer or float representation of label's x position where x=0 places the label on the left and x=1 places the label on the right of the plot.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_hline-y'>
		<b>y : <i>int | float | str</i></b>
		<ul style='list-style: none'>
			<li id='add_hline-y-description'>Integer, float, or string representation of line's y position. String expression arguments include 'min', 'mean', or 'max'.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_hline-label'>
		<b>label : <i>str, optional</i></b>
		<ul style='list-style: none'>
			<li id='add_hline-label-description'>String expression of line's label.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_hline-align_label'>
		<b>align_label : <i>str, optional</i></b>
		<ul style='list-style: none'>
			<li id='add_hline-align_label-description'>String expression of where to place label, taking precedence over the value given by 'x'. Accepted arguments include ['left', 'center', 'right'].</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_hline-line_color'>
		<b>line_color : <i>str, default 'black'</i></b>
		<ul style='list-style: none'>
			<li id='add_hline-line_color-description'>String expression of color.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_hline-line_dash'>
		<b>line_dash : <i>str, default 'solid'</i></b>
		<ul style='list-style: none'>
			<li id='add_hline-line_dash-description'>String expression of line dash style. Arguments include 'solid', 'dash', or 'dashdot'.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_hline-line_opacity'>
		<b>line_opacity : <i>float, default 1.0</i></b>
		<ul style='list-style: none'>
			<li id='add_hline-line_opacity-description'>Float representation of line opacity.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_hline-line_width'>
		<b>line_width : <i>int | float, default 1</i></b>
		<ul style='list-style: none'>
			<li id='add_hline-line_width-description'>Integer or float representation of line width.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_hline-showarrow'>
		<b>showarrow : <i>bool, default False</i></b>
		<ul style='list-style: none'>
			<li id='add_hline-showarrow-description'>Whether a line points to the position given by 'x' and 'y'.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_hline-xshift'>
		<b>xshift : <i>int, default 0</i></b>
		<ul style='list-style: none'>
			<li id='add_hline-xshift-description'>Horizontal offset applied to annotation label.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_hline-yshift'>
		<b>yshift : <i>int, default 10</i></b>
		<ul style='list-style: none'>
			<li id='add_hline-yshift-description'>Vertical offset applied to annotation label.</li>
		</ul>
	</li>
</ul>
<ul style='list-style: none'>
	<li id='add_hline-textcolor'>
		<b>textcolor : <i>str, optional</i></b>
		<ul style='list-style: none'>
			<li id='add_hline-textcolor-description'>String expression of annotation label color.</li>
		</ul>
	</li>
</ul>

<hr>
