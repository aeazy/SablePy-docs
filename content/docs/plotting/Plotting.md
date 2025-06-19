# SablePy Plotting

The SablePy library provides powerful tools for creating and customizing plots
using Plotly. This section covers the main plotting classes available in
SablePy: `Bar`, `Heatmaps`, and `TimeSeries`. Each plotting class in SablePy
is designed to handle specific types of data visualizations. `BasePlot` serves
as the foundation for all plotting classes, providing common functionality and
methods. The specialized classes extend `BasePlot` to offer plot-specific features
and customization options.

Each plot utilizes a `PlotConfig` dataclass to manage configuration settings,
ensuring a consistent and flexible approach to plot customization. The
`PlotConfig` dataclass includes parameters for titles, axis labels, colors, and other
styling options. See [PlotConfig](../config.md#PlotConfig) for more details.

While SablePy Plotting can utilize a `pandas.DataFrame` directly, the workflow
is optimized for use with the `sablepy.Data` class. This integration allows for
seamless data manipulation and visualization, making it easier to analyze and
plot.

## Plotting Classes

- [`Bar`](./Bar): Create and customize bar plots with various options for
  grouping, stacking, and styling.
- [`Heatmaps`](./Heatmaps): Generate heatmaps to visualize data cage activity
  over time.
- [`TimeSeries`](./TimeSeries): Create line plots to visualize time series data. 
