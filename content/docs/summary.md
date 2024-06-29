<strong id='get-summary'>get_summary</strong>(<b>new_filename</b>, <b>new_filetype</b><i>='pdf'</i>, <b>export_filepath</b><i>=\_NoDefault.no_default</i>, <b>file</b><i>=\_NoDefault.no_default</i>, <b>data</b><i>=\_NoDefault.no_default</i>, <b>all_plots</b><i>=True</i>, <b>plots</b><i>=\_NoDefault.no_default</i>)

> Parameters

<ul style='list-style: none'>
    <li>
        <b>new_filename : <i>str</i></b>
        <ul style='list-style: none'>
            <li>String expression representing the desired name of the pdf file generated.</li>
        </ul>
    </li>
    <li>
        <b>new_filetype : <i>str, default 'pdf'</i></b>
        <ul style='list-style: none'>
            <li>String expression representing the desired type of file to generate for the summary. Accepted arguments include ['pdf', 'html']. Defaults to 'pdf' new_filetype='html' will create an html file with responsive plots.</li>
        </ul>
    </li>
    <li>
        <b>export_filepath : <i>str | pathlib.Path, optional</i></b>
        <ul style='list-style: none'>
            <li>String or Path object indicating where to export the generated file. Defaults to None.</li>
        </ul>
    </li>
    <li>
        <b>file : <i>str, optional</i></b>
        <ul style='list-style: none'>
            <li>String expression representing the csv file to generate the summary pdf from. If 'file=None', an argument is expected for 'data'. Defaults to None.</li>
        </ul>
    </li>
    <li>
        <b>data : <i>pandas.core.frame.DataFrame | sablepy.Data, optional</i></b>
        <ul style='list-style: none'>
            <li>pandas.DataFrame or sablepy.Data object to generate the summary pdf from. Defaults to None.</li>
        </ul>
    </li>
    <li>
        <b>all_plots : <i>bool, default True</i></b>
        <ul style='list-style: none'>
            <li>Whether the summary generated includes all standard plots for respirometry and behavior. If 'all_plots=False',
            an argument for plots to generate is expected for 'plots'. Defaults to True.</li>
        </ul>
    </li>
    <li>
        <b>plots : <i>str | list[str], optional</i></b>
        <ul style='list-style: none'>
            <li>List of string expressions representing the plots to generate. Defaults to None.
            Accepted arguments include: 'respirometry', 'behavior', 'vo2', 'vco2', 'rq', 'kcalhr', 'ee', 'food', 'water', 'bodymass', 'allmeters'</li>
        </ul>
    </li>
</ul>
