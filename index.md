---
title       : Coursera Developing Data Products Slidify Project
subtitle    : Saturday, April 25, 2015
author      : Matías Alfredo Morales Armijo
job         : 
framework   :  io2012       # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax, quiz, bootstrap,interactive]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
ext_widgets: {rCharts: [libraries/nvd3]}
---

## The Project

This is my reproducible pitch presentation, where I describe what I did in my simple app project.
This project works with a matrix of incomes and expenses of three years (2012,2013,2014) of a company. This data matrix was invented. This shiny calculates the utility of the year selected by the user.
Utility is the difference between income and expense in a month.
$$Utility (U)=Income (I)-Expense (E)$$


--- 

## The Dataset column names (Example one year)

```r
data<-data.frame(year=c(2014,2014,2014,2014,2014,2014,2014,2014,2014,2014,2014,
2014,2013,2013,2013,2013,2013,2013,2013,2013,2013,2013,2013,2013,2012,2012,
2012,2012,2012,2012,2012,2012,2012,2012,2012,2012),month=c(1,2,3,4,5,6,7,8,9,10
,11,12,1,2,3,4,5,6,7,8,9,10,11,12,1,2,3,4,5,6,7,8,9,10,11,12),
incomes=c(500,1000,1100,1200,1350,900,800,900,1000,1150,1200,1300,
600,650,700,710,720,730,750,710,720,730,740,750,600,650,700,710,720,
730,750,710,720,730,740,750),expenses=c(20,30,40,50,60,70,65,60,54,77,
87,88,50,50,50,50,50,50,65,65,70,70,70,70,60,60,65,56,58,77,70,65,72,73,71,70))
head(data)
```

```
##   year month incomes expenses
## 1 2014     1     500       20
## 2 2014     2    1000       30
## 3 2014     3    1100       40
## 4 2014     4    1200       50
## 5 2014     5    1350       60
## 6 2014     6     900       70
```
 

---

## How it works

 1. The user select a year    
 2. In all cases above, when the user make a choice, the plot is updated with the year selected by the user.
 2. The Platform calculates Utility from year selected
 3. The user can choise between several graphical options: 
  Incomes in the selected year.
  Compare incomes/expenses 
  Utility in the year

Take this amazing experience going to: https://matiasmorales.shinyapps.io/project/


---

## Plot Sample

<div id = 'chart4' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart4()
    });
    function drawchart4(){  
      var opts = {
 "dom": "chart4",
"width":    600,
"height":    350,
"x": "month",
"y": "incomes",
"group": "year",
"type": "multiBarChart",
"id": "chart4" 
},
        data = [
 {
 "year":           2014,
"month":              1,
"incomes":            500,
"expenses":             20 
},
{
 "year":           2014,
"month":              2,
"incomes":           1000,
"expenses":             30 
},
{
 "year":           2014,
"month":              3,
"incomes":           1100,
"expenses":             40 
},
{
 "year":           2014,
"month":              4,
"incomes":           1200,
"expenses":             50 
},
{
 "year":           2014,
"month":              5,
"incomes":           1350,
"expenses":             60 
},
{
 "year":           2014,
"month":              6,
"incomes":            900,
"expenses":             70 
},
{
 "year":           2014,
"month":              7,
"incomes":            800,
"expenses":             65 
},
{
 "year":           2014,
"month":              8,
"incomes":            900,
"expenses":             60 
},
{
 "year":           2014,
"month":              9,
"incomes":           1000,
"expenses":             54 
},
{
 "year":           2014,
"month":             10,
"incomes":           1150,
"expenses":             77 
},
{
 "year":           2014,
"month":             11,
"incomes":           1200,
"expenses":             87 
},
{
 "year":           2014,
"month":             12,
"incomes":           1300,
"expenses":             88 
},
{
 "year":           2013,
"month":              1,
"incomes":            600,
"expenses":             50 
},
{
 "year":           2013,
"month":              2,
"incomes":            650,
"expenses":             50 
},
{
 "year":           2013,
"month":              3,
"incomes":            700,
"expenses":             50 
},
{
 "year":           2013,
"month":              4,
"incomes":            710,
"expenses":             50 
},
{
 "year":           2013,
"month":              5,
"incomes":            720,
"expenses":             50 
},
{
 "year":           2013,
"month":              6,
"incomes":            730,
"expenses":             50 
},
{
 "year":           2013,
"month":              7,
"incomes":            750,
"expenses":             65 
},
{
 "year":           2013,
"month":              8,
"incomes":            710,
"expenses":             65 
},
{
 "year":           2013,
"month":              9,
"incomes":            720,
"expenses":             70 
},
{
 "year":           2013,
"month":             10,
"incomes":            730,
"expenses":             70 
},
{
 "year":           2013,
"month":             11,
"incomes":            740,
"expenses":             70 
},
{
 "year":           2013,
"month":             12,
"incomes":            750,
"expenses":             70 
},
{
 "year":           2012,
"month":              1,
"incomes":            600,
"expenses":             60 
},
{
 "year":           2012,
"month":              2,
"incomes":            650,
"expenses":             60 
},
{
 "year":           2012,
"month":              3,
"incomes":            700,
"expenses":             65 
},
{
 "year":           2012,
"month":              4,
"incomes":            710,
"expenses":             56 
},
{
 "year":           2012,
"month":              5,
"incomes":            720,
"expenses":             58 
},
{
 "year":           2012,
"month":              6,
"incomes":            730,
"expenses":             77 
},
{
 "year":           2012,
"month":              7,
"incomes":            750,
"expenses":             70 
},
{
 "year":           2012,
"month":              8,
"incomes":            710,
"expenses":             65 
},
{
 "year":           2012,
"month":              9,
"incomes":            720,
"expenses":             72 
},
{
 "year":           2012,
"month":             10,
"incomes":            730,
"expenses":             73 
},
{
 "year":           2012,
"month":             11,
"incomes":            740,
"expenses":             71 
},
{
 "year":           2012,
"month":             12,
"incomes":            750,
"expenses":             70 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus" || opts.type==="bulletChart")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != "bulletChart"){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        

        
        
        
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>
