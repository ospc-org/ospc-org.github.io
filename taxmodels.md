---
title: TaxModels
permalink: /taxmodels/
layout: page
order: 3
---

<h2 align="center"><b>Workflow of the OSPC models</b></h2>
<br>

<div style="text-align:justify">OSPC develops a family of tax models, consisting of <a style="display:inline-block" href="https://github.com/PSLmodels/Tax-Calculator">Tax-Calculator</a>, <a style="display:inline-block" href="https://github.com/PSLmodels/taxdata">Tax-Data</a>, <a style="display:inline-block" href="https://github.com/PSLmodels/Behavioral-Responses"> Behavioral Responses</a>, and <a style="display:inline-block" href="https://github.com/PSLmodels/Tax-Brain"> Tax-Brain</a>. All of the models are open source. The flowchart explains how models interact with each other. </div>
<br>

<center>
<img src="/images/flowchart.png" alt="OSPC" style="max-width:1000px; width:100%">
<br> <br>

<div style="text-align:justify">
The Current Population Survey (CPS) and IRS Public Use File (PUF) are the base data sets for the OSPC tax models. Tax-data produces the input micro data files for Tax-Calculator, by conducting a series of data preparation procedures upon the original CPS and PUF data. These procedures include the statistical matching between CPS and PUF data; data extrapolation to forecast base year micro datasets into the future years; and re-weighting to hit the desired macro targets. Macro targets are based on governmental data, including: IRS Statistics of Income data, CBO projections, OASDI Trustees Report and BLS data. Tax-Data produces two processed CPS and PUF based micro-datasets, a growth factor file and a weights file.  
<br><br>
Tax-Calculator, the micro-simulation model, uses the processed CPS and PUF micro datasets from Tax-Data, to perform income tax and payroll tax analysis. Tax-Calculator can be used for revenue estimation, individual tax calculation, and distributional analysis. Users can also change <a style="display:inline-block" href="https://taxcalc.pslmodels.org/guide/policy_params.html"> Policy Parameters </a> to perform tax reform simulations. The Behavior-Responses package allows a user of Tax-Calculator to conduct conventional analysis, which considers the behavior responses that arise from changes to policy. 
<br><br>
<p align="justify"> Tax-Brain serves as an integrator to wrap multiple models. It uses a single interface to access Tax-Calculator and Behavior Responses. It provides users with many useful tools and can be run through the Python API or the command line interface (CLI). There is also an online web application for the users with less programming experience. </p>
<br>
<div style="text-align:justify">
Scholars inside and outside of AEI have used the model for their research (<a style="display:inline-block" href="https://github.com/PSLmodels/Tax-Calculator/blob/master/docs/use_cases.md">use cases</a>).
</div>

<br>
<h2 align="center"><b>Model Performance</b></h2>
<br>
<div align="justify"> We regularly validate OSPC tax models in two ways. One method validates calculations at the micro level by looking at the individual tax units. We test against <a style="display:inline-block" href="https://www.nber.org/research/data/taxsim">NBER TAXSIM model</a>, comparing calculated tax liability and the intermediate variables like taxable income and AMT liabilities, record by record. This process helps both OSPC and NBER TAXSIM to identify modelling differences and make improvements.
</div>
<br><br>
<center>
<img src="/images/performancechart.png" alt="OSPC" style="max-width:1000px; width:100%">
<br><br>
<div align="justify">
The second method validates the model at a macro level. This method compares the value of projected aggregates from Tax-Calculator with the Congressional Budget Office's <a style="display:inline-block" href="https://www.cbo.gov/data/budget-economic-data">10-year economic & revenue projections</a>. Items considered for comparison include the calculation of AGI, calculation of income tax liability, and share of AGI by income groups. The chart below shows macro validation for some example items.
</div> 
<br>
<center>
<img src="/images/validationchart.png" alt="OSPC" style="max-width:1000px; width:100%">
<br>
<p align="justify"> Many key items in Tax-Calculator like Total AGI show differences of less than 1.5% to CBO over the next 10 years. Please refer to this <a style="display:inline-block" href="https://github.com/PSLmodels/taxdata/tree/master/history/reports">latest report</a> for full list of comparisons with CBO. 
</p> 