---
title: Bar Chart
sidebar_position: 1
queries: 
- orders_by_month.sql
- orders_by_category_2021.sql
- orders_by_item_all_time.sql
- categories_by_channel.sql
---

<BarChart 
    data={orders_by_category_2021}
    x=month
    y=sales
    series=category
    title="Sales by Category"
/>


```markdown
<BarChart 
    data={orders_by_category_2021}
    x=month
    y=sales
    series=category
    title="Sales by Category"
/>
```

## Examples

### Default

<BarChart 
    data={orders_by_month}
    x=month
    y=sales
/>


```markdown
<BarChart 
    data={orders_by_month}
    x=month
    y=sales
/>
```

### Stacked

<BarChart 
    data={orders_by_category_2021}
    x=month
    y=sales
    series=category
/>

```markdown
<BarChart 
    data={orders_by_category_2021}
    x=month
    y=sales
    series=category
/>
```

### 100% Stacked

<BarChart 
    data={orders_by_category_2021}
    x=month
    y=sales
    yFmt=pct0
    series=category
    type=stacked100
/>

```markdown
<BarChart 
    data={orders_by_category_2021}
    x=month
    y=sales
    yFmt=pct0
    series=category
    type=stacked100
/>
```

### Grouped

<BarChart 
    data={orders_by_category_2021}
    x=month
    y=sales
    series=category
    type=grouped
/>

```markdown
<BarChart 
    data={orders_by_category_2021}
    x=month
    y=sales
    series=category
    type=grouped
/>
```

### Horizontal

<BarChart 
    data={orders_by_item_all_time}
    x=item
    y=sales 
    swapXY=true
    yFmt=usd0k
/>

```markdown
<BarChart 
    data={orders_by_item_all_time}
    x=item
    y=sales 
    swapXY=true
    yFmt=usd0k
/>
```

### Horizontal Stacked

<BarChart 
    data={categories_by_channel}
    x=category
    y=sales
    series=channel
    swapXY=true
/>

```markdown
<BarChart 
    data={categories_by_channel}
    x=category
    y=sales
    series=channel
    swapXY=true
/>
```

### Horizontal 100% Stacked

<BarChart 
    data={categories_by_channel}
    x=category
    y=sales
    series=channel
    type=stacked100
    swapXY=true
/>

```markdown
<BarChart 
    data={categories_by_channel}
    x=category
    y=sales
    series=channel
    type=stacked100
    swapXY=true
/>
```

### Horizontal Grouped

<BarChart
    data={categories_by_channel}
    x=category
    y=sales
    series=channel
    type=grouped
    swapXY=true
/>

```markdown
<BarChart
    data={categories_by_channel}
    x=category
    y=sales
    series=channel
    type=grouped
    swapXY=true
/>
```

### Value Labels

<BarChart 
    data={orders_by_category_2021}
    x=month
    y=sales
    yFmt=usd1k
    series=category
    labels=true
/>


```markdown
<BarChart 
    data={orders_by_category_2021}
    x=month
    y=sales
    yFmt=usd1k
    series=category
    labels=true
/>
```

### Custom Color Palette

<BarChart 
    data={orders_by_category_2021}
    x=month 
    y=sales 
    series=category 
    colorPalette={[
        '#cf0d06',
        '#eb5752',
        '#e88a87',
        '#fcdad9',
        ]}
/>


```markdown
<BarChart 
    data={orders_by_category_2021}
    x=month 
    y=sales 
    series=category 
    colorPalette={[
        '#cf0d06',
        '#eb5752',
        '#e88a87',
        '#fcdad9',
        ]}
/>
```

### Secondary / Duel y Axis

<BarChart 
    data={orders_by_month} 
    x=month 
    y=sales
    yFmt=usd0k
    y2=num_orders
/>

```markdown
<BarChart 
    data={orders_by_month} 
    x=month 
    y=sales_usd0k 
    y2=num_orders_num0
/>
```

### Secondary / Duel Axis with Line

<BarChart 
    data={orders_by_month} 
    x=month 
    y=sales
    yFmt=usd0k
    y2=num_orders
    y2SeriesType=line
/>

```markdown
<BarChart 
    data={orders_by_month} 
    x=month 
    y=sales
    yFmt=usd0k
    y2=num_orders
    y2SeriesType=line
/>
```

## Options

### Data

<PropListing
    name=data
    description="Query name, wrapped in curly braces"
    required=true
    options="query name"
/>
<PropListing
    name=x
    description="Column to use for the x-axis of the chart"
    options="column name"
    defaultValue="First column"
/>
<PropListing
    name=y
    description="Column(s) to use for the y-axis of the chart"
    options="column name | array of column names"
    defaultValue="Any non-assigned numeric columns"
/>
<PropListing
    name=y2
    description="Column(s) to include on a secondary y-axis"
    options="column name | array of column names"
/>
<PropListing
    name=y2SeriesType
    description="Chart type to apply to the series on the y2 axis"
    options={['bar', 'line', 'scatter']}
    defaultValue=bar
/>
<PropListing
    name=series
    description="Column to use as the series (groups) in a multi-series chart"
    options="column name"
/>
<PropListing
    name=sort
    description="Whether to apply default sort to your data. Default sort is x ascending for number and date x-axes, and y descending for category x-axes"
    options={['true', 'false']}
    defaultValue=true
/>
<PropListing
    name=type
    description="Grouping method to use for multi-series charts"
    options={['stacked', 'grouped', 'stacked100']}
    defaultValue=stacked
/>
<PropListing
    name=stackName
    description="Name for an individual stack. If separate Bar components are used with different stackNames, the chart will show multiple stacks"
    options="string"
/>
<PropListing
    name=emptySet
    description="Sets behaviour for empty datasets. Can throw an error, a warning, or allow empty. When set to 'error', empty datasets will block builds in `build:strict`. Note this only applies to initial page load - empty datasets caused by input component changes (dropdowns, etc.) are allowed."
    options={['error', 'warn', 'pass']}
    defaultValue=error
/>
<PropListing
    name=emptyMessage
    description="Text to display when an empty dataset is received - only applies when `emptySet` is 'warn' or 'pass', or when the empty dataset is a result of an input component change (dropdowns, etc.)."
    options="string"
    defaultValue="No records"
/>

### Formatting & Styling

<PropListing
    name=xFmt
    description="Format to use for x column (<a class=markdown href='/core-concepts/formatting'>see available formats<a/>)"
    options="Excel-style format | built-in format name | custom format name"
/>
<PropListing
    name=yFmt
    description="Format to use for y column (<a class=markdown href='/core-concepts/formatting'>see available formats<a/>)"
    options="Excel-style format | built-in format name | custom format name"
/>
<PropListing
    name=y2Fmt
    description="Format to use for y2 column(s) (<a class=markdown href='/core-concepts/formatting'>see available formats<a/>)"
    options="Excel-style format | built-in format name | custom format name"
/>
<PropListing
    name=fillColor
    description="Color to override default series color. Only accepts a single color."
    options="CSS name | hexademical | RGB | HSL"
/>
<PropListing
    name=fillOpacity
    description="% of the full color that should be rendered, with remainder being transparent"
    options="number (0 to 1)"
    defaultValue=1
/>
<PropListing
    name=outlineWidth
    description="Width of line surrounding each bar"
    options="number"
    defaultValue=0
/>
<PropListing
    name=outlineColor
    description="Color to use for outline if outlineWidth > 0"
    options="CSS name | hexademical | RGB | HSL"
/>
<PropListing
    name=colorPalette
    description="Array of custom colours to use for the chart. E.g., <code class=markdown>{`{['#cf0d06','#eb5752','#e88a87']}`}</code>"
    options="array of color strings (CSS name | hexademical | RGB | HSL)"
    defaultValue="built-in color palette"
/>
<PropListing
    name=seriesColors
    description="Apply a specific color to each series in your chart. Unspecified series will receive colors from the built-in palette as normal. Note the double curly braces required in the syntax"
    options="object with series names and assigned colors"
    defaultValue="colors applied by order of series in data"
/>

### Value Labels

<PropListing
    name=labels
    description="Show value labels"
    options={['true', 'false']}
    defaultValue=false
/>
<PropListing
    name=stackTotalLabel
    description="Whether to show a total at the top of stacked bar chart"
    options={['true', 'false']}
    defaultValue=true
/>
<PropListing
    name=labelSize
    description="Font size of value labels"
    options="number"
    defaultValue=11
/>
<PropListing
    name=labelPosition
    description="Where label will appear on your series"
    options={['outside', 'inside']}
    defaultValue="Single Series: outside, Stacked: inside, Grouped: outside"
/>
<PropListing
    name=labelColor
    description="Font color of value labels"
    options="CSS name | hexademical | RGB | HSL"
    defaultValue="Automatic based on color contrast of background"
/>
<PropListing
    name=labelFmt
    description="Format to use for value labels (<a class=markdown href='/core-concepts/formatting'>see available formats<a/>)"
    options="Excel-style format | built-in format name | custom format name"
    defaultValue="same as y column"
/>
<PropListing
    name=yLabelFmt
    description="Format to use for value labels for series on the y axis. Overrides any other formats (<a class=markdown href='/core-concepts/formatting'>see available formats<a/>)"
    options="Excel-style format | built-in format name | custom format name"
/>
<PropListing
    name=y2LabelFmt
    description="Format to use for value labels for series on the y2 axis. Overrides any other formats (<a class=markdown href='/core-concepts/formatting'>see available formats<a/>)"
    options="Excel-style format | built-in format name | custom format name"
/>
<PropListing
    name=showAllLabels
    description="Allow all labels to appear on chart, including overlapping labels"
    options={['true', 'false']}
    defaultValue=false
/>

### Axes

<PropListing
    name=swapXY
    description="Swap the x and y axes to create a horizontal chart"
    options={['true', 'false']}
    defaultValue=false
/>
<PropListing
    name=yLog
    description="Whether to use a log scale for the y-axis"
    options={['true', 'false']}
    defaultValue=false
/>
<PropListing
    name=yLogBase
    description="Base to use when log scale is enabled"
    options="number"
    defaultValue=10
/>
<PropListing
    name=xAxisTitle
    description="Name to show under x-axis. If 'true', formatted column name is used. Only works with swapXY=false"
    options={['true', 'string', 'false']}
    defaultValue=false
/>
<PropListing
    name=yAxisTitle
    description="Name to show beside y-axis. If 'true', formatted column name is used."
    options={['true', 'string', 'false']}
    defaultValue=false
/>
<PropListing
    name=y2AxisTitle
    description="Name to show beside y2 axis. If 'true', formatted column name is used."
    options={['true', 'string', 'false']}
    defaultValue=false
/>
<PropListing
    name=xGridlines
    description="Turns on/off gridlines extending from x-axis tick marks (vertical lines when swapXY=false)"
    options={['true', 'false']}
    defaultValue=false
/>
<PropListing
    name=yGridlines
    description="Turns on/off gridlines extending from y-axis tick marks (horizontal lines when swapXY=false)"
    options={['true', 'false']}
    defaultValue=true
/>
<PropListing
    name=y2Gridlines
    description="Turns on/off gridlines extending from y2-axis tick marks (horizontal lines when swapXY=false)"
    options={['true', 'false']}
    defaultValue=true
/>
<PropListing
    name=xAxisLabels
    description="Turns on/off value labels on the x-axis"
    options={['true', 'false']}
    defaultValue=true
/>
<PropListing
    name=yAxisLabels
    description="Turns on/off value labels on the y-axis"
    options={['true', 'false']}
    defaultValue=true
/>
<PropListing
    name=y2AxisLabels
    description="Turns on/off value labels on the y2-axis"
    options={['true', 'false']}
    defaultValue=true
/>
<PropListing
    name=xBaseline
    description="Turns on/off thick axis line (line appears at y=0)"
    options={['true', 'false']}
    defaultValue=true
/>
<PropListing
    name=yBaseline
    description="Turns on/off thick axis line (line appears directly alongside the y-axis labels)"
    options={['true', 'false']}
    defaultValue=false
/>
<PropListing
    name=y2Baseline
    description="Turns on/off thick axis line (line appears directly alongside the y2-axis labels)"
    options={['true', 'false']}
    defaultValue=false
/>
<PropListing
    name=xTickMarks
    description="Turns on/off tick marks for each of the x-axis labels"
    options={['true', 'false']}
    defaultValue=false
/>
<PropListing
    name=yTickMarks
    description="Turns on/off tick marks for each of the y-axis labels"
    options={['true', 'false']}
    defaultValue=false
/>
<PropListing
    name=y2TickMarks
    description="Turns on/off tick marks for each of the y2-axis labels"
    options={['true', 'false']}
    defaultValue=false
/>
<PropListing
    name=yMin
    description="Starting value for the y-axis"
    options="number"
/>
<PropListing
    name=yMax
    description="Maximum value for the y-axis"
    options="number"
/>
<PropListing
    name=yScale
    description="Whether to scale the y-axis to fit your data. `yMin` and `yMax` take precedence over `yScale`"
    options={['true', 'false']}
    defaultValue=false
/>
<PropListing
    name=y2Min
    description="Starting value for the y2-axis"
    options="number"
/>
<PropListing
    name=y2Max
    description="Maximum value for the y2-axis"
    options="number"
/>
<PropListing
    name=y2Scale
    description="Whether to scale the y-axis to fit your data. `y2Min` and `y2Max` take precedence over `y2Scale`"
    options={['true', 'false']}
    defaultValue=false
/>
<PropListing
    name=showAllXAxisLabels
    description="Force every x-axis value to be shown. This can truncate labels if there are too many."
    options={['true', 'false']}
    defaultValue=false
/>
<PropListing
    name=yAxisColor
    description="Turns on/off color on the y-axis (turned on by default when secondary y-axis is used). Can also be used to set a specific color"
    options={['true', 'false', 'color string (CSS name | hexademical | RGB | HSL)']}
    defaultValue="true when y2 used; false otherwise"
/>

### Chart

<PropListing
    name=title
    description="Chart title. Appears at top left of chart."
    options="string"
/>
<PropListing
    name=subtitle
    description="Chart subtitle. Appears just under title."
    options="string"
/>
<PropListing
    name=legend
    description="Turns legend on or off. Legend appears at top center of chart."
    options={['true', 'false']}
    defaultValue="true for multiple series"
/>
<PropListing
    name=chartAreaHeight
    description="Minimum height of the chart area (excl. header and footer) in pixels. Adjusting the height affects all viewport sizes and may impact the mobile UX."
    options="number"
    defaultValue=180
/>
<PropListing
    name=renderer
    description="Which chart renderer type (canvas or SVG) to use. See ECharts' <a href='https://echarts.apache.org/handbook/en/best-practices/canvas-vs-svg/' class=markdown>documentation on renderers</a>."
    options={['canvas', 'svg']}
    defaultValue=canvas
/>

### Custom Echarts Options

<PropListing
    name=echartsOptions
    description="Custom Echarts options to override the default options. See <a href='/components/echarts-options/' class=markdown>reference page</a> for available options."
    options="{`{{exampleOption:'exampleValue'}}`}"
/>
<PropListing
    name=seriesOptions
    description="Custom Echarts options to override the default options for all series in the chart. This loops through the series to apply the settings rather than having to specify every series manually using `echartsOptions` See <a href='/components/echarts-options/' class=markdown>reference page</a> for available options."
    options="{`{{exampleSeriesOption:'exampleValue'}}`}"
/>
<PropListing
    name=printEchartsConfig
    description="Helper prop for custom chart development - inserts a code block with the current echarts config onto the page so you can see the options used and debug your custom options"
    options={['true', 'false']}
    defaultValue=false
/>

### Interactivity

<PropListing
    name=connectGroup
    description="Group name to connect this chart to other charts for synchronized tooltip hovering. Charts with the same `connectGroup` name will become connected"
/>



## Annotations

```sql target_data
select 8333 as target, '100k ARR' as name
```

Bar charts can include [annotations](/components/annotations) using the `ReferenceLine` and `ReferenceArea` components. These components are used within a chart component like so:

<BarChart data={orders_by_month} x=month y=sales>
  <ReferenceArea xMin='2020-03-14' xMax='2021-05-01' label='COVID-19 Lockdown'/>
  <ReferenceLine data={target_data} y=target label=name/>
</BarChart>

```html
<BarChart data={orders_by_month} x=month y=sales>
  <ReferenceArea xMin='2020-03-14' xMax='2021-05-01' label='COVID-19 Lockdown'/>
  <ReferenceLine data={target_data} y=target label=name/>
</BarChart>
```