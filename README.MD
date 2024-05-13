# SablePy

The SablePy library leverages Pandas and Plotly libraries to provide a number of tools to streamline your data analysis:

- Combine CSV files using [`sablepy.combine_csv_files`](#combine-csv-files)
- Analyze CSV files using a number of methods provided by [`sablepy.Data`](/content/docs/data.md)
- Create time series and bar plots using your data, with control over nearly every detail using [`sablepy.BarPlot`](/content/docs/barplot.md) and [`sablepy.TimeSeries`](/content/docs/timeseries.md)
- Easily export data to a CSV, or plot to a PNG, using [`sablepy.export`](/content/docs/export.md)
- Streamline data visualization with Jupyter notebooks, which are made even easier using [`sablepy.new_notebook`](#create-a-new-jupyter-notebook-using-a-template)

See the [Directory](#directory) for the full list of links to module documentation. Otherwise, see [Getting Started](#getting-started) to begin.

## Getting Started

- [Installation](#installation)
- [Combining CSV Files](#combine-csv-files)
  - [Instructions](#using-sablepycombine_csv_files)
  - [Example](#sablepycombine_csv_files-examples)
- [Analyzing data](#create-a-new-jupyter-notebook-using-a-template)

### Installation

- If you are updating a current project to the newest SablePy release, only steps 4-7 are required.

1. Create a new directory for your project:

   ```
   mkdir newProject
   ```

2. Navigate to the new directory:

   ```
   cd newProject
   ```

3. Create a virtual environment:

   - Using VSCode:

     1. Open the Command Palette (Ctrl + Shift + P)
     2. Search for the **Python: Create Environment** command and select it.
     3. For `environment type`, select **Venv**.
     4. For `interpreter`, select your desired Python version (e.g., Python 3.12.0).

   - Using the terminal:
     ```
     py -3 -m venv .venv
     .venv\Scripts\activate
     ```

4. Download the SablePy package:

   1. Navigate to [Releases](https://github.com/aeazy/SablePy/releases).
   2. Under **Assets**, locate the .whl file and download it.

5. Add the .whl file to the directory created in step 2. The directory should look something like this:

   ```
    .
    ├── newProject
        ├── .venv
        └── sablepy-24.x.x-py3-none-any.whl
   ```

6. Install the .whl file using a package manager (e.g., pip):

   ```
   pip install sablepy-24.x.x-py3-none-any.whl
   ```

   - Note: You can install pip using the terminal. The command is `py -m pip install --upgrade pip`.

7. After the .whl package is successfully installed, remove it from the directory.

8. Create the directory for you to upload your csv files:

   - Automatically create the folders using `sablepy.make_directories`:

     - In a new python script, import the function and run it:

       ```bash
       >>> from sablepy import make_directories

       >>> make_directories()
       Creating required directories...
       'newProject/analysis' created.
       'newProject/uploads' created.
       Required directories successfully created.
       ```

   - Manually create the folders using terminal:
     ```
     mkdir uploads
     mkdir analysis
     ```

9. The final directory should appear as:

   ```
   .
   ├── newProject
       ├── .venv
       ├── analysis
       └── uploads
   ```

### Combine CSV files

<div style="border:1px solid gray; padding: 10px;">

<strong id='combine-csv-files'>combine_csv_files</strong>(<b>files</b><i>=\_NoDefault.no_default</i>, <b>folder</b><i>=\_NoDefault.no_default</i>, <b>upload_dir</b><i>='uploads'</i>, <b>options</b><i>=\_NoDefault.no_default</i>)

> Parameters

   <ul style='list-style: none'>
      <li>
         <b>files : <i>list[str], optional</i></b>
         <ul style='list-style: none'>
               <li>List of string expressions representing the .csv files to combine. The suffix '.csv' is optional. If <code>files=None</code>, argument for <code>folder</code> is required.</li>
         </ul>
      </li>
      <li>
         <b>folder : <i>str, optional</i></b>
         <ul style='list-style: none'>
               <li>String expression of the folder name containing the .csv files to combine.</li>
         </ul>
      </li>
      <li>
         <b>upload_dir : <i>str, default 'uploads'</i></b>
         <ul style='list-style: none'>
               <li>Optionally, provide a custom directory where the .csv files to combine are located. </li>
         </ul>
      </li>
      <li>
         <b>options : <i>sablepy.common.dataclasses.CombineOptions, optional</i></b>
         <ul style='list-style: none'>
               <li>Requires the dataclass <code>sablepy.CombineOptions</code> to be passed as an argument. See the <a href="https://github.com/aeazy/SablePy/blob/main/sablepy/content/docs/dataclasses.md#combineoptions">documentation</a> for more info.</li>
         </ul>
      </li>
   </ul>
</div>

#### Using `sablepy.combine_csv_files`

1. Add the files you are going combine to the `uploads` folder. They can be uploaded individually, or within a folder.
   - If individually, the directory will appear as:
     ```
        .
        ├── newProject
            ├── .venv
            ├── analysis
            ├── uploads
            │   ├── example.csv
            │   └── example2.csv
            └── main.py
     ```
   - In a folder, the directory will appear as:
     ```
        .
        ├── newProject
            ├── .venv
            ├── analysis
            ├── uploads
            │   └── example
            │       ├── example.csv
            │       └── example2.csv
            └── main.py
     ```
2. In a python script:

   1. Import the function and the CombineOptions dataclass.

   2. Call the function, optionally providing the desired filename of the combined file, as well as any options using the `CombineOptions` dataclass.

#### `sablepy.combine_csv_files` Examples

- Using default options:

  - Using individually uploaded files:

    ```bash
    >>> from sablepy import combine_csv_files, CombineOptions

    >>> combine_csv_files(files=['example', 'example2'])
    ```

  - Using a folder upload:

    ```bash
    >>> from sablepy import combine_csv_files, CombineOptions

    >>> combine_csv_files(folder='example')
    ```

  - Both examples would create a .csv file named '**combined.csv**', which can be found under (**~/uploads/combined/**)

- Using CombineOptions:
  - Specify the filename of the combined .csv file:
    ```bash
    >>> combine_csv_files(
            folder='example',
            options=CombineOptions(new_filename='exampleCombined')
        )
    ```
  - Force overwrite a previously combined .csv file:
    ```bash
    >>> combine_csv_files(
            folder='example',
            options=CombineOptions(overwrite_existing=True))
        )
    ```
  - Delete the individual files after they are successfully combined:
    ```bash
    >>> combine_csv_files(
            folder='example',
            options=CombineOptions(delete_original_files=True)
        )
    ```
  - Disable resampling of the combined files:
    ```bash
    >>> combine_csv_files(
            folder='example',
            options=CombineOptions(resample_data=False)
        )
    ```
  - Specify the frequency to use when resampling the combined files:
    ```bash
    >>> combine_csv_files(
            folder='example',
            options=CombineOptions(resample_frequency="2h")
        )
    ```

### Create a new Jupyter Notebook using a template

The SablePy library includes 4 Jupyter notebook templates:

- Standard: Includes plots for both respirometry and behavior data
- Respirometry: Includes plots for only respirometry
- Behavior: Includes plots for only behavior data (e.g., Movement-related data and Food/Water Consumption Data)
- Heatmaps: Generates heatmap plots using positional data.
  - **NOTE:** This requires a specific csv file either generated by a custom macro or created manually. See [Heatmaps](src/sablepy/plotting/heatmap.py) for more information.

#### Example

In `main.py`:

1. Import the function to create a notebook from a template:
   ```
   from sablepy import new_analysis
   ```
2. Call the function:

   ```
   from sablepy import new_analysis

   # Create a notebook from the standard template. The file created will be named 'standard_{datetime}.ipynb'
   new_analysis(analysis='standard')

   # Optionally, you can provide your desired filename of the new notebook
   new_analysis(analysis='standard', new_filename='example') # The notebook created will be named 'example.ipynb'
   ```

## Directory

| Module                                    | Description                                                                             |
| ----------------------------------------- | --------------------------------------------------------------------------------------- |
| [Data](content/docs/data.md)              | Read CSV files and analyze data with numerous functions to assist in your data analysis |
| [Bar Plot](content/docs/barplot.md)       | Generate and customize barplots                                                         |
| [Time Series](content/docs/timeseries.md) | Generate and customize line plots                                                       |
| [Math](content/docs/math.md)              | Supplemental functions for data analysis                                                |
| [Export](content/docs/export.md)          | Export dataframes and plots to csv, pngs, or pdf files                                  |
