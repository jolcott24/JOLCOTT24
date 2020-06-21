---
layout: page
title: "Visualizations"
permalink: /visualizations/
author_profile: true
---
## &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2013 Referendum Proportion of Yes Votes on Question 1

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;with ggplot
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![](/2013_map_ggplot.png)

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;with R classic
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![](/2013_map_R_classic.png)


<!DOCTYPE html>
<html>
<head>

  <meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
  <script type="application/shiny-singletons"></script>
  <script type="application/html-dependencies">json2[2014.02.04];jquery[3.4.1];shiny[1.4.0.2];selectize[0.11.2];htmlwidgets[1.5.1];plotly-binding[4.9.2.1];bootstrap[3.4.1]</script>
<script src="shared/json2-min.js"></script>
<script src="shared/jquery.min.js"></script>
<link href="shared/shiny.css" rel="stylesheet" />
<script src="shared/shiny.min.js"></script>
<link href="shared/selectize/css/selectize.bootstrap3.css" rel="stylesheet" />
<!--[if lt IE 9]>
<script src="shared/selectize/js/es5-shim.min.js"></script>
<![endif]-->
<script src="shared/selectize/js/selectize.min.js"></script>
<script src="htmlwidgets-1.5.1/htmlwidgets.js"></script>
<script src="plotly-binding-4.9.2.1/plotly.js"></script>
<meta name="viewport" content="width=device-width, initial-scale=1" />
<link href="shared/bootstrap/css/bootstrap.min.css" rel="stylesheet" />
<script src="shared/bootstrap/js/bootstrap.min.js"></script>
<script src="shared/bootstrap/shim/html5shiv.min.js"></script>
<script src="shared/bootstrap/shim/respond.min.js"></script>  <title>Maine Voting Results Map Maker</title>

</head>

<body>
  <div class="container-fluid">
    <h2>Maine Voting Results Map Maker</h2>
    <div class="row">
      <div class="col-sm-4">
        <form class="well">
          <div class="form-group shiny-input-container">
            <label class="control-label" for="dataset">Year:</label>
            <div>
              <select id="dataset"><option value="2012" selected>2012</option>
<option value="2013">2013</option>
<option value="2014">2014</option>
<option value="2015">2015</option>
<option value="2016">2016</option>
<option value="2017">2017</option></select>
              <script type="application/json" data-for="dataset" data-nonempty="">{}</script>
            </div>
          </div>
          <hr/>
          <div id="column" class="shiny-html-output"></div>
          <hr/>
        </form>
      </div>
      <div class="col-sm-8">
        <div id="stateMap" style="width:100%; height:400px; " class="plotly html-widget html-widget-output shiny-report-size"></div>
      </div>
    </div>
  </div>
</body>

</html>

