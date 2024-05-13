<strong id='export'>export</strong>(<b>data</b><i>=\_NoDefault.no_default</i>, <b>new_filename</b><i>=\_NoDefault.no_default</i>, <b>export_path</b><i>=\_NoDefault.no_default</i>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>data : <i>sablepy.core.data.Data | pandas.core.frame.DataFrame | sablepy.plotting.time_series.TimeSeries | sablepy.plotting.bar_plot.BarPlot | plotly.graph_objs._figure.Figure, optional</i></b>
        <ul style='list-style: none'>
            <li>Data to export. Object type dictates type of file created when exporting object. If <code>dtype=sablepy.Data, or pandas.DataFrame</code>, exported file is a csv. If <code>dtype=sablepy.TimeSeries, sablepy.BarPlot, or plotly.Figure</code>, exported file is a png.</li>
        </ul>
    </li>
    <li>
        <b>new_filename : <i>str, optional</i></b>
        <ul style='list-style: none'>
            <li>String expression of the filename of the exported file.</li>
        </ul>
    </li>
    <li>
        <b>export_path : <i>pathlib.Path | str, optional</i></b>
        <ul style='list-style: none'>
            <li>Absolute path to export file.</li>
        </ul>
    </li>
</ul>
