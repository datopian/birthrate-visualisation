---
title: Global Birth Rate Dashboard
toc: false
---

<div class="portaljs-banner">
  <div class="portaljs-banner-content">
    <span class="portaljs-banner-icon">👶</span>
    <div class="portaljs-banner-text">
      <p class="portaljs-banner-title">World Bank Birth Rate Indicator</p>
      <p class="portaljs-banner-description">Explore the global demographic transition — crude birth rates per 1,000 people (1960-2023)</p>
    </div>
  </div>
  <a href="https://data.worldbank.org/indicator/SP.DYN.CBRT.IN" target="_blank" rel="noopener noreferrer" class="portaljs-banner-cta">
    View Source Data <span class="portaljs-banner-cta-arrow">→</span>
  </a>
</div>

<style>
.hero {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  padding: 0.5rem 0.75rem;
  background: var(--theme-background-alt);
  color: var(--theme-foreground);
  border-radius: 4px;
  margin-bottom: 0.75rem;
  border: 2px solid var(--theme-foreground-faint);
}

.hero h1 {
  margin: 0;
  font-size: 1.25rem;
  font-weight: 700;
  color: var(--theme-foreground-alt);
  line-height: 1.2;
}

.hero p {
  margin: 0.15rem 0 0;
  font-size: 0.7rem;
  color: var(--theme-foreground-muted);
  line-height: 1.3;
}

.dashboard-layout {
  display: grid;
  grid-template-columns: 210px 1fr;
  gap: 1rem;
  margin: 0 0 4rem 0;
}

.sidebar {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  padding-right: 0.5rem;
  border-right: 1px solid var(--theme-foreground-faint);
}

.stat-card {
  background: var(--theme-background-alt);
  border: 2px solid var(--theme-foreground-faint);
  border-radius: 4px;
  padding: 0.5rem;
  text-align: left;
  min-height: 60px;
}

.stat-value {
  font-size: 1.3rem;
  font-weight: 900;
  color: var(--theme-foreground-alt);
  margin: 0.1rem 0;
  line-height: 1.1;
}

.stat-label {
  font-size: 0.6rem;
  color: var(--theme-foreground-muted);
  text-transform: uppercase;
  letter-spacing: 0.03em;
  font-weight: 600;
  line-height: 1.2;
}

.stat-change {
  font-size: 0.6rem;
  font-weight: 500;
  margin-top: 0.1rem;
  color: var(--theme-foreground-muted);
  line-height: 1.2;
}

.positive { color: #059669; }
.negative { color: #dc2626; }
.highlight-orange { color: #f59e0b; }

.main-content {
  display: flex;
  flex-direction: column;
  gap: 0;
  min-height: 400px;
  background: white;
  border: 1px solid var(--theme-foreground-faint);
  border-radius: 6px;
  overflow: visible;
}

.chart-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 0;
}

.chart-container {
  background: white;
  border: none;
  border-radius: 0;
  padding: 0.6rem;
  min-height: 280px;
}

.chart-container:not(:last-child) {
  border-right: 1px solid #e5e7eb;
}

.chart-container h3 {
  margin: 0 0 0.4rem 0;
  font-size: 0.75rem;
  font-weight: 700;
  color: var(--theme-foreground);
}

.chart-large {
  min-height: 380px !important;
  border-bottom: 1px solid #e5e7eb;
}

.controls-section {
  background: var(--theme-background-alt);
  border: 2px solid var(--theme-foreground-faint);
  border-radius: 4px;
  padding: 0.5rem;
}

.controls-section h3 {
  margin: 0 0 0.35rem 0;
  font-size: 0.6rem;
  font-weight: 700;
  color: var(--theme-foreground);
  text-transform: uppercase;
  letter-spacing: 0.03em;
}

.insights-section {
  background: var(--theme-background-alt);
  border: 2px solid var(--theme-foreground-faint);
  border-radius: 4px;
  padding: 0.6rem;
  font-size: 0.7rem;
  line-height: 1.35;
}

.insights-section h3 {
  margin: 0 0 0.4rem 0;
  font-size: 0.7rem;
  font-weight: 700;
  color: var(--theme-foreground);
  text-transform: uppercase;
  letter-spacing: 0.03em;
}

.insights-section ul {
  margin: 0;
  padding-left: 1rem;
  list-style-type: none;
}

.insights-section li {
  margin-bottom: 0.35rem;
  position: relative;
  padding-left: 0.4rem;
  font-size: 0.68rem;
  line-height: 1.4;
}

.insights-section li::before {
  content: "•";
  position: absolute;
  left: -0.4rem;
  color: var(--theme-foreground-focus);
  font-weight: bold;
  font-size: 0.7rem;
}

.insights-section .data-sources {
  margin-top: 0.55rem;
  padding-top: 0.55rem;
  border-top: 1px solid var(--theme-foreground-faint);
  font-size: 0.62rem;
  color: var(--theme-foreground-muted);
  line-height: 1.35;
}

.country-select {
  width: 100%;
  padding: 0.35rem;
  font-size: 0.7rem;
  border: 1px solid var(--theme-foreground-faint);
  border-radius: 4px;
  background: white;
  margin-top: 0.25rem;
}

@media (max-width: 1200px) {
  .chart-grid {
    grid-template-columns: 1fr 1fr;
  }
}

@media (max-width: 1024px) {
  .dashboard-layout {
    grid-template-columns: 1fr;
  }
  
  .sidebar {
    flex-direction: row;
    flex-wrap: wrap;
    border-right: none;
    border-bottom: 1px solid var(--theme-foreground-faint);
    padding-right: 0;
    padding-bottom: 0.75rem;
  }
  
  .controls-section {
    width: 100%;
  }
  
  .stat-card {
    flex: 1;
    min-width: 180px;
  }
}

@media (max-width: 768px) {
  .chart-grid {
    grid-template-columns: 1fr;
  }
  
  .chart-container:not(:last-child) {
    border-right: none;
    border-bottom: 1px solid #e5e7eb;
  }
  
  .sidebar {
    flex-direction: column;
  }
  
  .stat-card {
    min-width: auto;
  }
}
</style>

<div class="hero">
  <h1>Global Birth Rate Dashboard</h1>
  <p>The Demographic Transition — Tracking worldwide fertility decline from 1960 to 2023</p>
</div>

```js
// Load and process the birth rate data
const rawData = FileAttachment("data/indicator.csv").csv({typed: true});
const birthData = (await rawData).map(d => ({
  country: d["Country Name"],
  code: d["Country Code"],
  year: +d.Year,
  value: +d.Value
})).filter(d => !isNaN(d.value) && d.value > 0);

// Get unique years and countries
const years = [...new Set(birthData.map(d => d.year))].sort((a, b) => a - b);
const countries = [...new Set(birthData.map(d => d.country))].sort();
const minYear = d3.min(years);
const maxYear = d3.max(years);

// Calculate global averages by year
const globalAverages = d3.rollups(
  birthData,
  v => d3.mean(v, d => d.value),
  d => d.year
).map(([year, avg]) => ({ year, average: avg })).sort((a, b) => a.year - b.year);

const firstGlobalAvg = globalAverages[0];
const latestGlobalAvg = globalAverages[globalAverages.length - 1];
const totalDecline = firstGlobalAvg.average - latestGlobalAvg.average;
const percentDecline = ((totalDecline / firstGlobalAvg.average) * 100).toFixed(1);

// Major regions for comparison
const majorRegions = ["World", "European Union", "Sub-Saharan Africa", "East Asia & Pacific", "Latin America & Caribbean", "North America", "South Asia", "Middle East & North Africa"];
const regionData = birthData.filter(d => majorRegions.includes(d.country));
```

```js
// Scrubber component for year selection
function Scrubber(values, {format = value => value, initial = 0, direction = 1, delay = null, autoplay = true, loop = true, loopDelay = null, alternate = false} = {}) {
  values = Array.from(values);
  const form = html`<form style="font: 9px var(--sans-serif); display: flex; flex-direction: column; gap: 0.35rem;">
    <button name=b type=button style="width: 100%; padding: 0.25rem; font-size: 9px;"></button>
    <label style="display: flex; flex-direction: column; gap: 0.2rem;">
      <input name=i type=range min=0 max=${values.length - 1} value=${initial} step=1 style="width: 100%;">
      <output name=o style="font-size: 10px; font-weight: 600; text-align: center;"></output>
    </label>
  </form>`;
  let frame = null, timer = null, interval = null;
  const start = () => { form.b.textContent = "⏸ Pause"; if (delay === null) frame = requestAnimationFrame(tick); else interval = setInterval(tick, delay); };
  const stop = () => { form.b.textContent = "▶ Play"; if (frame !== null) cancelAnimationFrame(frame), frame = null; if (timer !== null) clearTimeout(timer), timer = null; if (interval !== null) clearInterval(interval), interval = null; };
  const running = () => frame !== null || timer !== null || interval !== null;
  const step = () => { form.i.valueAsNumber = (form.i.valueAsNumber + direction + values.length) % values.length; form.i.dispatchEvent(new CustomEvent("input", {bubbles: true})); };
  const tick = () => { if (form.i.valueAsNumber === (direction > 0 ? values.length - 1 : direction < 0 ? 0 : NaN)) { if (!loop) return stop(); if (alternate) direction = -direction; if (loopDelay !== null) { if (frame !== null) cancelAnimationFrame(frame), frame = null; if (interval !== null) clearInterval(interval), interval = null; timer = setTimeout(() => (step(), start()), loopDelay); return; } } if (delay === null) frame = requestAnimationFrame(tick); step(); };
  form.i.oninput = event => { if (event && event.isTrusted && running()) stop(); form.value = values[form.i.valueAsNumber]; form.o.value = format(form.value, form.i.valueAsNumber, values); };
  form.b.onclick = () => { if (running()) return stop(); direction = alternate && form.i.valueAsNumber === values.length - 1 ? -1 : 1; form.i.valueAsNumber = (form.i.valueAsNumber + direction) % values.length; form.i.dispatchEvent(new CustomEvent("input", {bubbles: true})); start(); };
  form.i.oninput();
  if (autoplay) start(); else stop();
  Inputs.disposal(form).then(stop);
  return form;
}
```

<div class="dashboard-layout">
  <div class="sidebar">
    <div class="controls-section">
      <h3>Timeline</h3>

```js
const selectedYear = view(Scrubber(years, {
  delay: 150,
  loop: false,
  initial: years.length - 1,
  autoplay: false,
  format: d => `📅 ${d}`
}));
```

<h3 style="margin-top: 0.5rem;">Compare Country</h3>

```js
const selectedCountry = view(Inputs.select(countries, {
  value: "World",
  label: ""
}));
```

</div>

```js
// Calculate stats for selected year
const yearData = birthData.filter(d => d.year === selectedYear);
const globalYearAvg = yearData.length > 0 ? d3.mean(yearData, d => d.value) : 0;

const firstYearData = birthData.filter(d => d.year === minYear);
const firstYearAvg = d3.mean(firstYearData, d => d.value);

const declineFromStart = firstYearAvg - globalYearAvg;
const declinePercent = ((declineFromStart / firstYearAvg) * 100).toFixed(1);

const countryYearData = birthData.filter(d => d.year === selectedYear && d.country === selectedCountry);
const countryRate = countryYearData.length > 0 ? countryYearData[0].value : null;

// Top and bottom countries
const sortedByRate = yearData.slice().sort((a, b) => b.value - a.value);
const topCountries = sortedByRate.slice(0, 5);
const bottomCountries = sortedByRate.slice(-5).reverse();

// Rate of change (year over year)
const prevYearData = birthData.filter(d => d.year === selectedYear - 1);
const currentYearMap = new Map(yearData.map(d => [d.country, d.value]));
const prevYearMap = new Map(prevYearData.map(d => [d.country, d.value]));

const rateChanges = yearData
  .filter(d => prevYearMap.has(d.country))
  .map(d => ({
    country: d.country,
    change: d.value - prevYearMap.get(d.country),
    current: d.value
  }))
  .sort((a, b) => a.change - b.change);

const fastestDecliners = rateChanges.slice(0, 5);
```

<div class="stat-card">
  <div class="stat-label">Global Average</div>
  <div class="stat-value">${globalYearAvg.toFixed(1)}</div>
  <div class="stat-change">births per 1,000 (${selectedYear})</div>
</div>

<div class="stat-card">
  <div class="stat-label">Decline Since 1960</div>
  <div class="stat-value positive">-${declineFromStart.toFixed(1)}</div>
  <div class="stat-change">(${declinePercent}% reduction)</div>
</div>

<div class="stat-card">
  <div class="stat-label">${selectedCountry}</div>
  <div class="stat-value highlight-orange">${countryRate ? countryRate.toFixed(1) : "N/A"}</div>
  <div class="stat-change">births per 1,000</div>
</div>

<div class="stat-card">
  <div class="stat-label">Countries Tracked</div>
  <div class="stat-value">${yearData.length}</div>
  <div class="stat-change">in ${selectedYear}</div>
</div>

<div class="insights-section">
  <h3>Key Insights</h3>
  <ul>
    <li><strong>Global Decline:</strong> World birth rates have fallen from ~${firstYearAvg.toFixed(0)} to ~${latestGlobalAvg.average.toFixed(0)} per 1,000 since 1960</li>
    <li><strong>Demographic Transition:</strong> Nearly all countries follow the pattern of declining fertility as development increases</li>
    <li><strong>Regional Gaps:</strong> Sub-Saharan Africa still has rates >35, while Europe is below 12</li>
    <li><strong>Fastest Declines:</strong> East Asia saw the most dramatic reductions, led by China's one-child policy era</li>
  </ul>
  <div class="data-sources">
    <strong>Data:</strong> <a href="https://data.worldbank.org/indicator/SP.DYN.CBRT.IN" target="_blank" rel="noopener noreferrer">World Bank Open Data</a>, CC-BY-4.0 License
  </div>
</div>
</div>

<div class="main-content">

```js
// Global trend chart with selected country overlay
function globalTrendChart({width} = {}) {
  const isMobile = width < 640;
  const height = isMobile ? 320 : 360;
  const marginTop = 25;
  const marginRight = isMobile ? 60 : 80;
  const marginBottom = isMobile ? 50 : 50;
  const marginLeft = isMobile ? 50 : 60;

  const filteredGlobal = globalAverages.filter(d => d.year <= selectedYear);
  const countryData = birthData.filter(d => d.country === selectedCountry && d.year <= selectedYear);
  
  const xScale = d3.scaleLinear()
    .domain([minYear, maxYear])
    .range([marginLeft, width - marginRight]);
  
  const yMax = Math.max(
    d3.max(globalAverages, d => d.average) || 40,
    d3.max(countryData, d => d.value) || 40
  );
  
  const yScale = d3.scaleLinear()
    .domain([0, yMax + 5])
    .range([height - marginBottom, marginTop])
    .nice();

  const globalLine = d3.line()
    .x(d => xScale(d.year))
    .y(d => yScale(d.average))
    .curve(d3.curveCatmullRom);

  const countryLine = d3.line()
    .x(d => xScale(d.year))
    .y(d => yScale(d.value))
    .curve(d3.curveCatmullRom);

  const container = d3.create("div")
    .style("position", "relative");

  const svg = container.append("svg")
    .attr("width", width)
    .attr("height", height)
    .attr("viewBox", [0, 0, width, height])
    .style("background", "white");

  const tooltip = container.append("div")
    .style("position", "absolute")
    .style("visibility", "hidden")
    .style("background", "white")
    .style("border", "1px solid #ccc")
    .style("border-radius", "4px")
    .style("padding", "8px")
    .style("font-size", "12px")
    .style("pointer-events", "none")
    .style("box-shadow", "0 2px 4px rgba(0,0,0,0.1)")
    .style("z-index", "1000");

  // Grid
  svg.append("g")
    .attr("transform", `translate(0,${height - marginBottom})`)
    .call(d3.axisBottom(xScale).tickFormat("").tickSize(-(height - marginTop - marginBottom)))
    .call(g => g.select(".domain").remove())
    .call(g => g.selectAll(".tick line").attr("stroke", "#e5e7eb").attr("stroke-opacity", 0.7));

  svg.append("g")
    .attr("transform", `translate(${marginLeft},0)`)
    .call(d3.axisLeft(yScale).tickFormat("").tickSize(-(width - marginLeft - marginRight)))
    .call(g => g.select(".domain").remove())
    .call(g => g.selectAll(".tick line").attr("stroke", "#e5e7eb").attr("stroke-opacity", 0.7));

  // Axes
  svg.append("g")
    .attr("transform", `translate(0,${height - marginBottom})`)
    .call(d3.axisBottom(xScale).tickFormat(d3.format("d")).ticks(isMobile ? 5 : 10).tickSize(0).tickPadding(8))
    .call(g => g.select(".domain").attr("stroke", "#ccc"));

  svg.append("g")
    .attr("transform", `translate(${marginLeft},0)`)
    .call(d3.axisLeft(yScale).ticks(7).tickSize(0).tickPadding(6))
    .call(g => g.select(".domain").attr("stroke", "#ccc"));

  svg.append("text")
    .attr("x", marginLeft)
    .attr("y", marginTop - 10)
    .attr("fill", "currentColor")
    .attr("font-size", "10px")
    .text("Births per 1,000");

  // Area gradient for global average
  svg.append("defs").append("linearGradient")
    .attr("id", "birthAreaGradient")
    .attr("x1", "0%").attr("y1", "0%")
    .attr("x2", "0%").attr("y2", "100%")
    .selectAll("stop")
    .data([
      {offset: "0%", color: "#3b82f6", opacity: 0.25},
      {offset: "100%", color: "#3b82f6", opacity: 0.05}
    ])
    .join("stop")
    .attr("offset", d => d.offset)
    .attr("stop-color", d => d.color)
    .attr("stop-opacity", d => d.opacity);

  const area = d3.area()
    .x(d => xScale(d.year))
    .y0(height - marginBottom)
    .y1(d => yScale(d.average))
    .curve(d3.curveCatmullRom);

  svg.append("path")
    .datum(filteredGlobal)
    .attr("fill", "url(#birthAreaGradient)")
    .attr("d", area);

  // Global average line
  svg.append("path")
    .datum(filteredGlobal)
    .attr("fill", "none")
    .attr("stroke", "#3b82f6")
    .attr("stroke-width", 2.5)
    .attr("d", globalLine);

  // Selected country line
  if (countryData.length > 0 && selectedCountry !== "World") {
    svg.append("path")
      .datum(countryData)
      .attr("fill", "none")
      .attr("stroke", "#f59e0b")
      .attr("stroke-width", 2.5)
      .attr("stroke-dasharray", "6,3")
      .attr("d", countryLine);
  }

  // Year indicator line
  svg.append("line")
    .attr("x1", xScale(selectedYear))
    .attr("x2", xScale(selectedYear))
    .attr("y1", marginTop)
    .attr("y2", height - marginBottom)
    .attr("stroke", "#dc2626")
    .attr("stroke-width", 2)
    .attr("stroke-dasharray", "4,4");

  // Current year point on global line
  const currentGlobal = filteredGlobal[filteredGlobal.length - 1];
  if (currentGlobal) {
    svg.append("circle")
      .attr("cx", xScale(currentGlobal.year))
      .attr("cy", yScale(currentGlobal.average))
      .attr("r", 6)
      .attr("fill", "#3b82f6")
      .attr("stroke", "white")
      .attr("stroke-width", 2);
  }

  // Current year point on country line
  const currentCountry = countryData[countryData.length - 1];
  if (currentCountry && selectedCountry !== "World") {
    svg.append("circle")
      .attr("cx", xScale(currentCountry.year))
      .attr("cy", yScale(currentCountry.value))
      .attr("r", 6)
      .attr("fill", "#f59e0b")
      .attr("stroke", "white")
      .attr("stroke-width", 2);
  }

  // Hover overlay
  const hoverCircle = svg.append("circle")
    .attr("r", 5)
    .attr("fill", "#3b82f6")
    .attr("stroke", "white")
    .attr("stroke-width", 2)
    .style("visibility", "hidden");

  svg.append("rect")
    .attr("x", marginLeft)
    .attr("y", marginTop)
    .attr("width", width - marginLeft - marginRight)
    .attr("height", height - marginTop - marginBottom)
    .attr("fill", "none")
    .attr("pointer-events", "all")
    .on("mousemove", function(event) {
      const [mx] = d3.pointer(event, svg.node());
      const year = Math.round(xScale.invert(mx));
      const dataPoint = filteredGlobal.find(d => d.year === year);
      
      if (dataPoint) {
        const dataX = xScale(dataPoint.year);
        const dataY = yScale(dataPoint.average);
        
        hoverCircle
          .attr("cx", dataX)
          .attr("cy", dataY)
          .style("visibility", "visible");

        let tooltipContent = `<strong>${dataPoint.year}</strong><br/>Global Avg: ${dataPoint.average.toFixed(2)}`;
        
        if (selectedCountry !== "World") {
          const countryPoint = countryData.find(d => d.year === year);
          if (countryPoint) {
            tooltipContent += `<br/>${selectedCountry}: ${countryPoint.value.toFixed(2)}`;
          }
        }

        tooltip
          .html(tooltipContent)
          .style("visibility", "visible")
          .style("left", `${dataX + 15}px`)
          .style("top", `${dataY - 20}px`);
      }
    })
    .on("mouseout", () => {
      tooltip.style("visibility", "hidden");
      hoverCircle.style("visibility", "hidden");
    });

  // Legend
  const legend = svg.append("g")
    .attr("transform", `translate(${width - marginRight + 10}, ${marginTop + 10})`);

  legend.append("line")
    .attr("x1", 0).attr("x2", 20)
    .attr("y1", 0).attr("y2", 0)
    .attr("stroke", "#3b82f6")
    .attr("stroke-width", 2.5);

  legend.append("text")
    .attr("x", 25).attr("y", 4)
    .attr("font-size", "10px")
    .attr("fill", "currentColor")
    .text("Global Avg");

  if (selectedCountry !== "World") {
    legend.append("line")
      .attr("x1", 0).attr("x2", 20)
      .attr("y1", 20).attr("y2", 20)
      .attr("stroke", "#f59e0b")
      .attr("stroke-width", 2.5)
      .attr("stroke-dasharray", "6,3");

    legend.append("text")
      .attr("x", 25).attr("y", 24)
      .attr("font-size", "10px")
      .attr("fill", "currentColor")
      .text(selectedCountry.length > 12 ? selectedCountry.substring(0, 12) + "..." : selectedCountry);
  }

  return container.node();
}
```

```js
// Top 5 highest birth rate countries chart
function topCountriesChart({width} = {}) {
  const isMobile = width < 640;
  
  return Plot.plot({
    width,
    height: isMobile ? 260 : 240,
    marginLeft: isMobile ? 100 : 120,
    marginRight: 40,
    marginBottom: 40,
    style: { fontSize: isMobile ? "11px" : "12px" },
    x: {
      label: "Birth Rate (per 1,000)",
      grid: true,
      domain: [0, Math.max(...topCountries.map(d => d.value)) + 5]
    },
    y: {
      label: null,
      domain: topCountries.map(d => d.country)
    },
    marks: [
      Plot.barX(topCountries, {
        x: "value",
        y: "country",
        fill: "#dc2626",
        fillOpacity: 0.8,
        tip: true,
        title: d => `${d.country}: ${d.value.toFixed(2)} births per 1,000`
      }),
      Plot.text(topCountries, {
        x: "value",
        y: "country",
        text: d => d.value.toFixed(1),
        dx: 5,
        textAnchor: "start",
        fontSize: 10,
        fill: "#374151"
      }),
      Plot.ruleX([0])
    ]
  });
}
```

```js
// Bottom 5 lowest birth rate countries chart
function bottomCountriesChart({width} = {}) {
  const isMobile = width < 640;
  
  return Plot.plot({
    width,
    height: isMobile ? 260 : 240,
    marginLeft: isMobile ? 100 : 120,
    marginRight: 40,
    marginBottom: 40,
    style: { fontSize: isMobile ? "11px" : "12px" },
    x: {
      label: "Birth Rate (per 1,000)",
      grid: true,
      domain: [0, 20]
    },
    y: {
      label: null,
      domain: bottomCountries.map(d => d.country)
    },
    marks: [
      Plot.barX(bottomCountries, {
        x: "value",
        y: "country",
        fill: "#059669",
        fillOpacity: 0.8,
        tip: true,
        title: d => `${d.country}: ${d.value.toFixed(2)} births per 1,000`
      }),
      Plot.text(bottomCountries, {
        x: "value",
        y: "country",
        text: d => d.value.toFixed(1),
        dx: 5,
        textAnchor: "start",
        fontSize: 10,
        fill: "#374151"
      }),
      Plot.ruleX([0])
    ]
  });
}
```

```js
// Decade comparison chart
const decadeData = d3.rollups(
  birthData.filter(d => d.country === "World"),
  v => d3.mean(v, d => d.value),
  d => Math.floor(d.year / 10) * 10
).map(([decade, avg]) => ({
  decade: `${decade}s`,
  decadeNum: decade,
  average: avg
})).filter(d => d.average).sort((a, b) => a.decadeNum - b.decadeNum);

const filteredDecades = decadeData.filter(d => d.decadeNum <= Math.floor(selectedYear / 10) * 10);

function decadeComparisonChart({width} = {}) {
  const isMobile = width < 640;
  const currentDecade = Math.floor(selectedYear / 10) * 10;

  return Plot.plot({
    width,
    height: isMobile ? 260 : 240,
    marginLeft: isMobile ? 40 : 50,
    marginRight: 30,
    marginBottom: isMobile ? 60 : 55,
    style: { fontSize: isMobile ? "11px" : "12px" },
    x: {
      label: null,
      tickRotate: -45
    },
    y: {
      label: "Avg Birth Rate",
      grid: true,
      domain: [0, 40]
    },
    marks: [
      Plot.barY(filteredDecades, {
        x: "decade",
        y: "average",
        fill: d => d.decadeNum === currentDecade ? "#f59e0b" : "#3b82f6",
        fillOpacity: d => d.decadeNum === currentDecade ? 1 : 0.7,
        stroke: d => d.decadeNum === currentDecade ? "white" : "none",
        strokeWidth: 2,
        tip: true,
        title: d => `${d.decade}\nAverage: ${d.average.toFixed(2)} births per 1,000`
      }),
      Plot.ruleY([0])
    ]
  });
}
```

```js
// Regional comparison chart
const regionYearData = regionData.filter(d => d.year === selectedYear);

function regionalComparisonChart({width} = {}) {
  const isMobile = width < 640;
  const sortedRegions = regionYearData.slice().sort((a, b) => b.value - a.value);

  const colorScale = d3.scaleOrdinal()
    .domain(sortedRegions.map(d => d.country))
    .range(d3.schemeTableau10);

  return Plot.plot({
    width,
    height: isMobile ? 260 : 240,
    marginLeft: isMobile ? 130 : 160,
    marginRight: 50,
    marginBottom: 40,
    style: { fontSize: isMobile ? "10px" : "11px" },
    x: {
      label: "Birth Rate (per 1,000)",
      grid: true,
      domain: [0, Math.max(...sortedRegions.map(d => d.value || 0)) + 5]
    },
    y: {
      label: null,
      domain: sortedRegions.map(d => d.country)
    },
    marks: [
      Plot.barX(sortedRegions, {
        x: "value",
        y: "country",
        fill: d => colorScale(d.country),
        fillOpacity: 0.85,
        tip: true,
        title: d => `${d.country}: ${d.value.toFixed(2)} births per 1,000 (${selectedYear})`
      }),
      Plot.text(sortedRegions, {
        x: "value",
        y: "country",
        text: d => d.value ? d.value.toFixed(1) : "",
        dx: 5,
        textAnchor: "start",
        fontSize: 9,
        fill: "#374151"
      }),
      Plot.ruleX([0])
    ]
  });
}
```

```js
// Yearly rate of change chart - shows how much the global average birth rate changed each year
// Negative values (below zero) = birth rate is declining (good for demographic transition)
// Values closer to zero = rate of decline is slowing down
const yearlyRates = globalAverages.slice(1).map((d, i) => ({
  year: d.year,
  rate: d.average - globalAverages[i].average
}));

const filteredRates = yearlyRates.filter(d => d.year <= selectedYear);

// Calculate average rate of decline for insight
const avgDeclineRate = d3.mean(filteredRates, d => d.rate);

function rateOfChangeChart({width} = {}) {
  const isMobile = width < 640;

  return Plot.plot({
    width,
    height: isMobile ? 260 : 240,
    marginLeft: isMobile ? 45 : 55,
    marginRight: 30,
    marginBottom: isMobile ? 45 : 40,
    style: { fontSize: isMobile ? "11px" : "12px" },
    x: {
      label: null,
      grid: true,
      ticks: isMobile ? 5 : 8,
      tickFormat: d => String(d)
    },
    y: {
      label: "Annual Change",
      grid: true,
      domain: [-0.7, 0.15]
    },
    color: {
      legend: false
    },
    marks: [
      // Zero line - values below this mean birth rates are declining
      Plot.ruleY([0], {stroke: "#374151", strokeWidth: 1.5}),
      // Area fill to show the decline visually
      Plot.areaY(filteredRates, {
        x: "year",
        y: "rate",
        y1: 0,
        fill: "#059669",
        fillOpacity: 0.2,
        curve: "catmull-rom"
      }),
      // Main line showing the rate of change
      Plot.line(filteredRates, {
        x: "year",
        y: "rate",
        stroke: "#059669",
        strokeWidth: 2,
        curve: "catmull-rom"
      }),
      // Dots for each year with tooltips
      Plot.dot(filteredRates, {
        x: "year",
        y: "rate",
        r: 3,
        fill: "#059669",
        tip: true,
        title: d => `${d.year}\nChange: ${d.rate.toFixed(3)} per 1,000\n${d.rate < 0 ? "↓ Birth rate declined" : "↑ Birth rate increased"}`
      }),
      // Average line to show typical decline rate
      Plot.ruleY([avgDeclineRate], {stroke: "#f59e0b", strokeWidth: 1.5, strokeDasharray: "6,3"}),
      // Current year indicator
      Plot.ruleX([selectedYear], {stroke: "#3b82f6", strokeWidth: 2, strokeDasharray: "4,4"}),
      // Highlight current year point
      Plot.dot(filteredRates.filter(d => d.year === selectedYear), {
        x: "year",
        y: "rate",
        fill: "#3b82f6",
        stroke: "white",
        strokeWidth: 2,
        r: 6
      }),
      // Label for the zero line
      Plot.text([{x: maxYear, y: 0.05}], {
        x: "x",
        y: "y", 
        text: ["No change"],
        fontSize: 9,
        fill: "#6b7280",
        textAnchor: "end"
      }),
      // Label for average
      Plot.text([{x: minYear + 3, y: avgDeclineRate + 0.04}], {
        x: "x",
        y: "y",
        text: [`Avg: ${avgDeclineRate.toFixed(2)}/yr`],
        fontSize: 9,
        fill: "#f59e0b",
        textAnchor: "start"
      })
    ]
  });
}
```

<div class="chart-container chart-large">
  <h3>🌍 Global Birth Rate Trend (1960-2023) — Blue: Global Average, Orange: ${selectedCountry}</h3>
  ${resize((width) => globalTrendChart({width}))}
</div>

<div class="chart-grid">
  <div class="chart-container">
    <h3>🔴 Top 5 Highest Birth Rates (${selectedYear})</h3>
    ${resize((width) => topCountriesChart({width}))}
  </div>

  <div class="chart-container">
    <h3>🟢 Top 5 Lowest Birth Rates (${selectedYear})</h3>
    ${resize((width) => bottomCountriesChart({width}))}
  </div>

  <div class="chart-container">
    <h3>📊 Decade Average Comparison</h3>
    ${resize((width) => decadeComparisonChart({width}))}
  </div>
</div>

<div class="chart-grid">
  <div class="chart-container">
    <h3>🌐 Regional Comparison (${selectedYear})</h3>
    ${resize((width) => regionalComparisonChart({width}))}
  </div>

  <div class="chart-container" style="grid-column: span 2;">
    <h3>📉 Annual Change in Global Birth Rate (Below zero = declining)</h3>
    ${resize((width) => rateOfChangeChart({width}))}
  </div>
</div>

</div>
</div>

---