## Blog Post Title From First Header

Due to a plugin called `jekyll-titles-from-headings` which is supported by GitHub Pages by default. The above header (in the markdown file) will be automatically used as the pages title.

If the file does not start with a header, then the post title will be derived from the filename.

This is a sample blog post. You can talk about all sorts of fun things here.

---

### This is a header


#### Some T-SQL Code

```tsql
SELECT This, [Is], A, Code, Block -- Using SSMS style syntax highlighting
    , REVERSE('abc')
FROM dbo.SomeTable s
    CROSS JOIN dbo.OtherTable o;
```

#### Some PowerShell Code

```powershell
Write-Host "This is a powershell Code block";

# There are many other languages you can use, but the style has to be loaded first

ForEach ($thing in $things) {
    Write-Output "It highlights it using the GitHub style"
}
```

### Test Energy Chart

<div class="full-width-embed">
<iframe src="/assets/capacity_chart.html" width="100%" height="620" frameborder="0"></iframe>
</div>

### Interactive Chart

<iframe src="/assets/chart.html" width="100%" height="620" frameborder="0"></iframe>

### Interactive Plotly Chart

<div id="my-chart" style="width: 100%; height: 500px;"></div>

<script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
<script>
  const dates = [];
  const values = [];
  const startDate = new Date("2023-01-01");

  for (let i = 0; i < 90; i++) {
    const date = new Date(startDate);
    date.setDate(startDate.getDate() + i);
    dates.push(date.toISOString().split('T')[0]);
    values.push(Math.floor(Math.random() * 100));
  }

  const trace = {
    x: dates,
    y: values,
    type: 'bar',
    marker: { color: 'steelblue' }
  };

  const layout = {
    title: "Time Series Bar Chart with Zoom",
    xaxis: {
      rangeselector: {
        buttons: [
          { count: 7, label: '1w', step: 'day', stepmode: 'backward' },
          { count: 1, label: '1m', step: 'month', stepmode: 'backward' },
          { step: 'all' }
        ]
      },
      rangeslider: { visible: true },
      type: 'date'
    },
    yaxis: { title: "Random Value" }
  };

  Plotly.newPlot('my-chart', [trace], layout);
</script>

