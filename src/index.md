---
title: NBA Player Stats 2024–25
theme: dark
---

# NBA Player Stats
### 2024–25 Regular Season · Per-Game Stats

#### Which NBA players have the best stats this season?

```js
// ── DATA ── 2024-25 Regular Season (verify decimals vs Basketball Reference)
const raw = [
  {name:"Shai G-Alexander", team:"OKC", pos:"SG", pts:32.7, ast:6.4,  reb:5.1, fg_pct:.535, fg3_pct:.358, ts_pct:.653, per:33.5, mpg:34.2},
  {name:"Nikola Jokic",     team:"DEN", pos:"C",  pts:29.6, ast:9.5,  reb:12.7,fg_pct:.573, fg3_pct:.395, ts_pct:.645, per:32.5, mpg:34.5},
  {name:"Giannis Antet.",   team:"MIL", pos:"PF", pts:30.4, ast:6.0,  reb:11.9,fg_pct:.613, fg3_pct:.274, ts_pct:.643, per:32.0, mpg:34.5},
  {name:"Luka Doncic",      team:"LAL", pos:"PG", pts:28.1, ast:8.6,  reb:8.3, fg_pct:.491, fg3_pct:.376, ts_pct:.612, per:29.0, mpg:35.5},
  {name:"Victor Wembanyama",team:"SAS", pos:"C",  pts:25.4, ast:3.9,  reb:10.7,fg_pct:.503, fg3_pct:.380, ts_pct:.609, per:26.5, mpg:32.0},
  {name:"Jalen Brunson",    team:"NYK", pos:"PG", pts:29.0, ast:7.0,  reb:3.7, fg_pct:.492, fg3_pct:.389, ts_pct:.617, per:24.0, mpg:35.5},
  {name:"Devin Booker",     team:"PHX", pos:"SG", pts:28.1, ast:6.4,  reb:4.7, fg_pct:.499, fg3_pct:.381, ts_pct:.620, per:23.0, mpg:35.5},
  {name:"Kevin Durant",     team:"PHX", pos:"SF", pts:26.2, ast:4.9,  reb:6.5, fg_pct:.523, fg3_pct:.415, ts_pct:.634, per:23.0, mpg:37.0},
  {name:"Jayson Tatum",     team:"BOS", pos:"SF", pts:26.2, ast:5.5,  reb:7.9, fg_pct:.469, fg3_pct:.381, ts_pct:.595, per:22.5, mpg:36.0},
  {name:"Anthony Edwards",  team:"MIN", pos:"SG", pts:27.4, ast:5.6,  reb:5.7, fg_pct:.464, fg3_pct:.362, ts_pct:.585, per:22.0, mpg:35.5},
  {name:"Tyrese Maxey",     team:"PHI", pos:"PG", pts:26.3, ast:6.6,  reb:3.9, fg_pct:.479, fg3_pct:.401, ts_pct:.627, per:21.5, mpg:36.2},
  {name:"Cade Cunningham",  team:"DET", pos:"PG", pts:25.2, ast:9.2,  reb:5.2, fg_pct:.433, fg3_pct:.337, ts_pct:.562, per:20.5, mpg:36.0},
  {name:"Anthony Davis",    team:"LAL", pos:"C",  pts:25.6, ast:3.6,  reb:12.0,fg_pct:.560, fg3_pct:.280, ts_pct:.618, per:26.0, mpg:35.5},
  {name:"Donovan Mitchell", team:"CLE", pos:"SG", pts:24.9, ast:5.2,  reb:4.5, fg_pct:.470, fg3_pct:.364, ts_pct:.597, per:21.5, mpg:34.5},
  {name:"Damian Lillard",   team:"MIL", pos:"PG", pts:25.3, ast:7.1,  reb:4.4, fg_pct:.449, fg3_pct:.358, ts_pct:.598, per:21.0, mpg:35.0},
  {name:"Zion Williamson",  team:"NOP", pos:"PF", pts:25.2, ast:5.2,  reb:5.9, fg_pct:.574, fg3_pct:.333, ts_pct:.629, per:24.0, mpg:29.5},
  {name:"Alperen Sengun",   team:"HOU", pos:"C",  pts:23.1, ast:5.7,  reb:9.6, fg_pct:.554, fg3_pct:.262, ts_pct:.590, per:23.0, mpg:31.0},
  {name:"Karl-Anthony Towns",team:"NYK",pos:"C",  pts:24.0, ast:3.5,  reb:13.9,fg_pct:.505, fg3_pct:.398, ts_pct:.608, per:22.0, mpg:32.0},
  {name:"LeBron James",     team:"LAL", pos:"SF", pts:23.7, ast:8.0,  reb:7.4, fg_pct:.535, fg3_pct:.398, ts_pct:.630, per:23.5, mpg:35.3},
  {name:"Domantas Sabonis", team:"SAC", pos:"C",  pts:19.9, ast:8.2,  reb:14.4,fg_pct:.574, fg3_pct:.294, ts_pct:.600, per:24.0, mpg:35.0},
  {name:"Jaylen Brown",     team:"BOS", pos:"SG", pts:23.8, ast:4.0,  reb:5.9, fg_pct:.491, fg3_pct:.361, ts_pct:.583, per:19.5, mpg:33.5},
  {name:"Kyrie Irving",     team:"DAL", pos:"PG", pts:26.0, ast:5.5,  reb:5.2, fg_pct:.498, fg3_pct:.375, ts_pct:.609, per:21.0, mpg:35.5},
  {name:"Trae Young",       team:"ATL", pos:"PG", pts:23.6, ast:11.1, reb:3.0, fg_pct:.432, fg3_pct:.355, ts_pct:.578, per:20.5, mpg:34.5},
  {name:"De'Aaron Fox",     team:"SAS", pos:"PG", pts:23.5, ast:6.0,  reb:4.3, fg_pct:.505, fg3_pct:.334, ts_pct:.598, per:21.5, mpg:33.5},
  {name:"Stephen Curry",    team:"GSW", pos:"PG", pts:23.5, ast:5.7,  reb:4.3, fg_pct:.454, fg3_pct:.412, ts_pct:.629, per:21.5, mpg:33.0},
  {name:"Tyrese Haliburton",team:"IND", pos:"PG", pts:21.0, ast:10.5, reb:4.5, fg_pct:.475, fg3_pct:.398, ts_pct:.620, per:21.0, mpg:33.0},
  {name:"Jalen Williams",   team:"OKC", pos:"SG", pts:24.0, ast:5.8,  reb:4.5, fg_pct:.503, fg3_pct:.364, ts_pct:.609, per:21.0, mpg:33.5},
  {name:"Paolo Banchero",   team:"ORL", pos:"PF", pts:25.0, ast:5.7,  reb:7.5, fg_pct:.454, fg3_pct:.318, ts_pct:.550, per:19.5, mpg:35.0},
  {name:"Franz Wagner",     team:"ORL", pos:"SF", pts:25.0, ast:4.0,  reb:5.7, fg_pct:.482, fg3_pct:.362, ts_pct:.575, per:17.5, mpg:34.0},
  {name:"Julius Randle",    team:"MIN", pos:"PF", pts:22.0, ast:5.0,  reb:9.0, fg_pct:.452, fg3_pct:.318, ts_pct:.560, per:19.5, mpg:34.0},
  {name:"LaMelo Ball",      team:"CHA", pos:"PG", pts:24.5, ast:8.5,  reb:5.8, fg_pct:.428, fg3_pct:.345, ts_pct:.555, per:18.5, mpg:31.0},
  {name:"Jimmy Butler",     team:"GSW", pos:"SF", pts:21.0, ast:5.3,  reb:5.2, fg_pct:.510, fg3_pct:.250, ts_pct:.606, per:19.5, mpg:33.0},
  {name:"Bam Adebayo",      team:"MIA", pos:"C",  pts:20.5, ast:3.7,  reb:10.4,fg_pct:.531, fg3_pct:.000, ts_pct:.572, per:19.5, mpg:34.0},
  {name:"Jaren Jackson Jr.",team:"MEM", pos:"PF", pts:23.0, ast:2.0,  reb:7.0, fg_pct:.530, fg3_pct:.355, ts_pct:.605, per:18.5, mpg:32.5},
  {name:"Lauri Markkanen",  team:"UTA", pos:"PF", pts:24.3, ast:2.0,  reb:8.5, fg_pct:.485, fg3_pct:.376, ts_pct:.591, per:19.5, mpg:34.0},
  {name:"Evan Mobley",      team:"CLE", pos:"C",  pts:17.5, ast:3.0,  reb:10.0,fg_pct:.558, fg3_pct:.349, ts_pct:.601, per:18.5, mpg:34.0},
  {name:"Scottie Barnes",   team:"TOR", pos:"PF", pts:21.0, ast:7.0,  reb:8.5, fg_pct:.501, fg3_pct:.315, ts_pct:.572, per:18.5, mpg:35.0},
  {name:"Rudy Gobert",      team:"MIN", pos:"C",  pts:13.5, ast:1.2,  reb:12.5,fg_pct:.618, fg3_pct:.000, ts_pct:.668, per:19.5, mpg:31.5},
  {name:"Chet Holmgren",    team:"OKC", pos:"C",  pts:18.5, ast:2.2,  reb:8.2, fg_pct:.527, fg3_pct:.388, ts_pct:.651, per:21.0, mpg:30.5},
  {name:"Paul George",      team:"PHI", pos:"SF", pts:17.0, ast:3.5,  reb:5.5, fg_pct:.455, fg3_pct:.410, ts_pct:.590, per:17.0, mpg:30.5},
  {name:"Ja Morant",        team:"MEM", pos:"PG", pts:22.9, ast:8.3,  reb:5.8, fg_pct:.472, fg3_pct:.275, ts_pct:.575, per:22.0, mpg:31.5},
  {name:"Tyler Herro",      team:"MIA", pos:"SG", pts:22.5, ast:5.0,  reb:4.8, fg_pct:.448, fg3_pct:.385, ts_pct:.571, per:16.5, mpg:32.5},
  {name:"Coby White",       team:"CHI", pos:"PG", pts:22.3, ast:5.5,  reb:4.8, fg_pct:.468, fg3_pct:.394, ts_pct:.589, per:17.5, mpg:32.5},
  {name:"Zach LaVine",      team:"CHI", pos:"SG", pts:22.0, ast:4.8,  reb:4.7, fg_pct:.450, fg3_pct:.374, ts_pct:.569, per:17.0, mpg:32.0},
  {name:"Brandon Ingram",   team:"NOP", pos:"SF", pts:24.0, ast:5.5,  reb:5.0, fg_pct:.487, fg3_pct:.360, ts_pct:.586, per:19.5, mpg:33.0},
  {name:"Desmond Bane",     team:"MEM", pos:"SG", pts:22.0, ast:4.5,  reb:4.0, fg_pct:.454, fg3_pct:.393, ts_pct:.582, per:17.5, mpg:31.5},
  {name:"Immanuel Quickley",team:"TOR", pos:"PG", pts:20.0, ast:7.2,  reb:4.7, fg_pct:.444, fg3_pct:.378, ts_pct:.575, per:17.5, mpg:35.0},
  {name:"Darius Garland",   team:"CLE", pos:"PG", pts:21.0, ast:7.5,  reb:2.8, fg_pct:.461, fg3_pct:.362, ts_pct:.580, per:18.5, mpg:32.5},
  {name:"OG Anunoby",       team:"NYK", pos:"SF", pts:16.1, ast:2.5,  reb:4.5, fg_pct:.506, fg3_pct:.389, ts_pct:.589, per:15.0, mpg:32.5},
  {name:"Mikal Bridges",    team:"NYK", pos:"SF", pts:18.0, ast:3.5,  reb:4.3, fg_pct:.476, fg3_pct:.342, ts_pct:.563, per:15.5, mpg:36.0},
  {name:"Klay Thompson",    team:"DAL", pos:"SG", pts:14.5, ast:2.5,  reb:3.5, fg_pct:.430, fg3_pct:.374, ts_pct:.553, per:13.5, mpg:29.0},
  {name:"Derrick White",    team:"BOS", pos:"SG", pts:15.9, ast:5.5,  reb:4.4, fg_pct:.456, fg3_pct:.395, ts_pct:.592, per:16.0, mpg:32.0},
  {name:"Jerami Grant",     team:"POR", pos:"SF", pts:20.0, ast:3.0,  reb:4.0, fg_pct:.452, fg3_pct:.366, ts_pct:.572, per:16.0, mpg:31.0},
  {name:"Walker Kessler",   team:"UTA", pos:"C",  pts:11.0, ast:1.2,  reb:10.5,fg_pct:.704, fg3_pct:.000, ts_pct:.748, per:19.0, mpg:26.5},
  {name:"Brook Lopez",      team:"MIL", pos:"C",  pts:13.5, ast:1.3,  reb:4.8, fg_pct:.503, fg3_pct:.380, ts_pct:.593, per:14.5, mpg:27.5},
  {name:"Jordan Poole",     team:"WAS", pos:"SG", pts:17.5, ast:5.5,  reb:2.8, fg_pct:.416, fg3_pct:.330, ts_pct:.540, per:14.5, mpg:30.5},
];
```

```js
// ── CONTROLS (Observable Inputs) ──
const STAT_LABELS = {
  pts:"Points/Game", ast:"Assists/Game", reb:"Rebounds/Game",
  fg_pct:"FG %", fg3_pct:"3P %", ts_pct:"True Shooting %", per:"PER"
};
const statOptions = Object.entries(STAT_LABELS).map(([v,l]) => ({value:v, label:l}));

const xKey = view(Inputs.select(new Map(statOptions.map(o=>[o.label, o.value])), {
  label: "X axis", value: "pts"
}));
```

```js
const yKey = view(Inputs.select(new Map(statOptions.map(o=>[o.label, o.value])), {
  label: "Y axis", value: "ast"
}));
```

```js
const mpgMin = view(Inputs.range([0, 36], {
  label: "Min. minutes/game", value: 10, step: 1
}));
```

```js
const POSITIONS = ["PG","SG","SF","PF","C"];
const posFilter = view(Inputs.checkbox(POSITIONS, {
  label: "Positions", value: POSITIONS
}));
```

```js
// ── FILTERED DATA ──
const filtered = raw.filter(d => d.mpg >= mpgMin && posFilter.includes(d.pos));
```

**${filtered.length} players shown**

```js
// ── COLORS ──
const POS_COLORS = {PG:"#4fc3f7", SG:"#81c784", SF:"#ffb74d", PF:"#f06292", C:"#ce93d8"};
const color = d => POS_COLORS[d.pos] ?? "#aaa";
const ESPN_ABBR = {GSW:"gs", NYK:"ny", NOP:"no", WAS:"wsh", UTA:"utah"};
const logoUrl = team => `https://a.espncdn.com/i/teamlogos/nba/500/${ESPN_ABBR[team] ?? team.toLowerCase()}.png`;
```

```js
// ── CHART ──
const W = 980, H = 580;
const M = {top: 20, right: 30, bottom: 50, left: 55};

const fmt = d3.format(".2f");
const fmtPct = d3.format(".1%");
function fmtStat(key, val) {
  return ["fg_pct","fg3_pct","ts_pct"].includes(key) ? fmtPct(val) : fmt(val);
}

const xVals = filtered.map(d => d[xKey]);
const yVals = filtered.map(d => d[yKey]);

const xScale = d3.scaleLinear()
  .domain(d3.extent(xVals)).nice()
  .range([M.left, W - M.right]);

const yScale = d3.scaleLinear()
  .domain(d3.extent(yVals)).nice()
  .range([H - M.bottom, M.top]);

const rScale = d3.scaleSqrt()
  .domain(d3.extent(filtered, d => d.mpg))
  .range([4, 10]);

// build SVG
const svg = d3.create("svg")
  .attr("width", W)
  .attr("height", H)
  .attr("style", "background:#16161a; border-radius:8px; font-family:monospace;");

// grid lines
svg.append("g")
  .attr("transform", `translate(0,0)`)
  .call(d3.axisLeft(yScale).ticks(6).tickSize(-(W - M.left - M.right)).tickFormat(""))
  .attr("transform", `translate(${M.left},0)`)
  .call(g => g.select(".domain").remove())
  .call(g => g.selectAll("line").attr("stroke","#2a2a35").attr("stroke-opacity",0.6));

// x axis
svg.append("g")
  .attr("transform", `translate(0,${H - M.bottom})`)
  .call(d3.axisBottom(xScale).ticks(6).tickFormat(v => fmtStat(xKey, v)))
  .call(g => g.select(".domain").attr("stroke","#2a2a35"))
  .call(g => g.selectAll("text").attr("fill","#6b6b80").attr("font-size","11px"))
  .call(g => g.selectAll("line").attr("stroke","#2a2a35"));

// y axis
svg.append("g")
  .attr("transform", `translate(${M.left},0)`)
  .call(d3.axisLeft(yScale).ticks(6).tickFormat(v => fmtStat(yKey, v)))
  .call(g => g.select(".domain").attr("stroke","#2a2a35"))
  .call(g => g.selectAll("text").attr("fill","#6b6b80").attr("font-size","11px"))
  .call(g => g.selectAll("line").attr("stroke","#2a2a35"));

// axis labels
svg.append("text")
  .attr("x", (M.left + W - M.right) / 2).attr("y", H - 8)
  .attr("text-anchor","middle").attr("fill","#6b6b80").attr("font-size","12px")
  .text(STAT_LABELS[xKey]);

svg.append("text")
  .attr("transform", `translate(14,${(M.top + H - M.bottom)/2}) rotate(-90)`)
  .attr("text-anchor","middle").attr("fill","#6b6b80").attr("font-size","12px")
  .text(STAT_LABELS[yKey]);

// dots
const tip = svg.append("g").attr("pointer-events","none");
let selectedTeam = null;

const dots = svg.append("g")
  .selectAll("circle")
  .data(filtered, d => d.name)
  .join("circle")
    .attr("cx", d => xScale(d[xKey]))
    .attr("cy", d => yScale(d[yKey]))
    .attr("r",  d => rScale(d.mpg))
    .attr("fill", d => color(d))
    .attr("fill-opacity", 0.82)
    .attr("stroke","#ffffff28")
    .attr("stroke-width", 1)
    .attr("cursor","pointer")
  .on("click", function(event, d) {
    selectedTeam = selectedTeam === d.team ? null : d.team;
    tip.selectAll("*").remove();
    dots
      .attr("fill-opacity", c => selectedTeam === null ? 0.82 : c.team === selectedTeam ? 1.0 : 0.15)
      .attr("stroke", c => selectedTeam !== null && c.team === selectedTeam ? "white" : "#ffffff28")
      .attr("stroke-width", c => selectedTeam !== null && c.team === selectedTeam ? 1.5 : 1);
  })
  .on("mouseover", function(event, d) {
    d3.select(this)
      .attr("stroke","white").attr("stroke-width", 2)
      .attr("r", rScale(d.mpg) * 1.45);
    const px = xScale(d[xKey]), py = yScale(d[yKey]);
    const lines = [
      d.name,
      `${d.team} · ${d.pos}`,
      `PTS ${fmt(d.pts)}  AST ${fmt(d.ast)}  REB ${fmt(d.reb)}`,
      `FG% ${fmtPct(d.fg_pct)}  3P% ${fmtPct(d.fg3_pct)}  TS% ${fmtPct(d.ts_pct)}`,
      `PER ${fmt(d.per)}  MPG ${fmt(d.mpg)}`
    ];
    tip.selectAll("*").remove();
    const bx = px + 12, by = py - 10;
    const boxW = 265, boxH = lines.length * 16 + 10;
    tip.append("rect")
      .attr("x", bx - 6).attr("y", by - 14)
      .attr("width", boxW).attr("height", boxH)
      .attr("fill","#16161a").attr("stroke","#f0a500")
      .attr("stroke-width",1).attr("rx",4);
    tip.append("image")
      .attr("href", logoUrl(d.team))
      .attr("x", bx + boxW - 52).attr("y", by - 12)
      .attr("width", 40).attr("height", 40)
      .attr("opacity", 0.8);
    lines.forEach((ln, i) => {
      tip.append("text")
        .attr("x", bx).attr("y", by + i * 16)
        .attr("fill", i === 0 ? "white" : i === 1 ? POS_COLORS[d.pos] : "#9999aa")
        .attr("font-size", i === 0 ? "13px" : "11px")
        .attr("font-weight", i === 0 ? "bold" : "normal")
        .text(ln);
    });
  })
  .on("mouseout", function(event, d) {
    d3.select(this)
      .attr("stroke","#ffffff28").attr("stroke-width", 1)
      .attr("r", rScale(d.mpg));
    tip.selectAll("*").remove();
  });

// legend
const legX = W - M.right - 170, legY = H - M.bottom - 120;
POSITIONS.forEach((pos, i) => {
  const g = svg.append("g").attr("transform",`translate(${legX},${legY + i*20})`);
  g.append("circle").attr("r",6).attr("fill",POS_COLORS[pos]).attr("cy",-4);
  g.append("text").attr("x",12).attr("fill","#9999aa").attr("font-size","11px")
    .text(pos + " — " + {PG:"Point Guard",SG:"Shooting Guard",SF:"Small Forward",PF:"Power Forward",C:"Center"}[pos]);
});

display(svg.node());
```

*Click any dot to highlight all players from that team · click again to clear · hover for full stat line*

*Data source: [Basketball Reference](https://www.basketball-reference.com/leagues/NBA_2025_per_game.html) — NBA 2024–25 Regular Season per-game stats · [View source on GitHub](https://github.com/swortiz/NBAPLAYERSTATS)*

---

## Design

### Visual Encodings

**Scatter plot** was chosen as the primary form because the central question — how do players compare across two statistics simultaneously? — requires plotting two quantitative variables at once. A scatter plot makes outliers, clusters, and trade-offs (e.g., high scorer but low efficiency) immediately visible in a way bar charts or tables cannot.

**Color encodes position** using five distinct hues against the dark background. Position is the most natural grouping in basketball analysis because it determines expected stat profiles: centers rebound more, point guards assist more. Color lets users instantly spot whether positional patterns hold or break down for a given stat pair.

**Circle size encodes minutes per game** via a sqrt scale, representing the team's reliance on each player. Larger, more prominent circles naturally draw the eye to high-usage players, which matches the intuition that starters deserve more visual weight than bench players.

### Interaction Techniques

**Dual-axis selectors** (dropdowns for X and Y) allow any two of seven statistics to be compared, making the chart reusable across dozens of questions without rebuilding the page. This was preferred over a fixed encoding because no single stat pair answers all interesting questions — comparing PTS vs. AST reveals playmakers, while TS% vs. PER reveals efficiency tiers.

**MPG slider** is a dynamic query filter that lets the user progressively narrow to starters (≥ 30 min) or open up to all rotation players, reducing overplotting and focusing the story.

**Position checkboxes** enable quick position-group comparisons — isolating only guards, or seeing where centers cluster relative to forwards — without permanently removing data.

**Hover tooltip** provides details-on-demand with the full stat line plus team logo, following the "overview first, details on demand" principle. Showing all stats in the tooltip avoids cluttering the chart with labels while still making every data point explorable.

**Click-to-highlight team** dims all other players when a dot is clicked, letting users answer questions like "how does OKC's roster distribute across the efficiency spectrum?" Multiple players from the same team are brought into focus together, which approaches multi-view coordination without requiring a second chart.

### Alternatives Considered

**Parallel coordinates** would show all seven stats simultaneously but becomes unreadable with 55+ overlapping lines. The dual-axis approach trades full-dimensional visibility for clarity and ease of comparison.

**Fixed PTS vs. AST encoding** was the starting point but locking axes would prevent exploring efficiency metrics like TS% or PER, which are often more analytically interesting than raw counting stats.

**Animated transitions** between stat views were considered but added implementation complexity without meaningful analytical benefit for this domain — the user can simply re-select axes.

### References

- Data: [Basketball Reference 2024–25 Per-Game Stats](https://www.basketball-reference.com/leagues/NBA_2025_per_game.html)
- Team logos: [ESPN CDN](https://a.espncdn.com/i/teamlogos/nba/)
- Built with [Observable Framework](https://observablehq.com/framework/) and [D3.js](https://d3js.org/)
