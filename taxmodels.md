---
title: TaxModels
permalink: /taxmodels/
layout: page
order: 3
---

<h2 align="center"><b>Workflow of the OSPC models</b></h2>
<br>

<div style="text-align:justify">OSPC develops a family of tax models, consisted of <a style="display:inline-block" href="https://github.com/PSLmodels/Tax-Calculator">Tax-Calculator</a>, <a style="display:inline-block" href="https://github.com/PSLmodels/taxdata">Tax-Data</a>, <a style="display:inline-block" href="https://github.com/PSLmodels/Behavioral-Responses"> Behavior Response</a>, <a style="display:inline-block" href="https://github.com/PSLmodels/Tax-Brain"> Tax-Brain</a> and <a style="display:inline-block" href="https://github.com/PSLmodels/Tax-Cruncher">Tax-Cruncher</a>. All of the models are open source. The flowchart explains how models interact with each other. </div>
<br>

<center>
<img src="/images/flowchart.png" alt="OSPC" style="max-width:1000px; width:100%">
<br> <br>

<div style="text-align:justify">
Current Population Survey (CPS) and IRS Public Use File (PUF) are the base input mirco databases for OSPC tax models. Tax-data produces the input micro data files for Tax-Calculator, by conducting a series of data preparation procedures upon the original CPS and PUF data. These procedures include: the statistical matching between the CPS and PUF data to extrpolate the information from both data files; data extrapolation to forcast base year micro datasets into the future years, by growth rate calculated from selected marcro targets; and re-weighting to make adjustments upon the desired macro targets (return targets; aggregate targets; aggregate by income class targets) so their aggregates will stay on track. Marco targets are referenced from governmental published tax statistics, including: SOI Estimate, CBO projections, OASDI Report and BLS Database. Eventually, Tax-Data produces two processed CPS and PUF based micro-datasets, growth factor file and weights file.  
<br><br>
Tax-Calculator, the micro-simulation model, then reads the processed CPS and PUF micro datasets from Tax-Data, to perform income tax and paryroll tax analysis. This can be used for tax revenue projection of future years, distrubutional anlysis of tax collected across different income groups and analysis of the tax reform. Scholars inside and outside of AEI has used the model for their research (<a style="display:inline-block" href="https://github.com/PSLmodels/Tax-Calculator/blob/master/docs/use_cases.md">use cases</a>). The model can also be used as a calcualtor for any self defined <a style="display:inline-block" href="https://taxcalc.pslmodels.org/guide/input_vars.html">Input</a> datasets to produce <a style="display:inline-block" href="https://taxcalc.pslmodels.org/guide/output_vars.html">Output</a> of tax liabilities along with other intermediate variables. Users can also change the <a style="display:inline-block" href="https://taxcalc.pslmodels.org/guide/policy_params.html"> Policy Parameters </a> to perform tax reform simulation. Here are some <a style="display:inline-block" href="https://taxcalc.pslmodels.org/recipes/recipe00.html">Receipes</a>. By interacting with the Behavior-Response package, Tax-Calculator is also able to conduct dynamic analysis considering the behavior responses arise from the policy reform. Model is under the assumption of partial equilibrium elasticity.
<br><br>
We are also working on a new <a style="display:inline-block" href="https://github.com/bodiyang/Taxcalc-Payroll">Taxcalc-Payroll</a>. The model is developed to focus on payroll tax, with new features of spliting of the employer side and employee side payroll tax, employer side payroll tax offset function. It is expected to be lauched soon.</div>
<br>
<p align="justify"> Tax-Brain and Tax-Cruncher serve as an integrator to wrap up multiple models, a single interface to access Tax-Calculator and Behavior Response. They provide users with many useful tools like weighted total calcuation, making distribution table, difference plots, etc. Models can be run through Python API or the command line interface (CLI). There is also an online web application for the public with less programming experience. </p>

<br>
<h2 align="center"><b>Model Performance</b></h2>
<br>
<p align="justify"> To ensure the model's perfomance, we have regular valdiation work to compare OSPC tax models with the external sources, publications from governmanetal agencies and modelling results from other research organiztions. </p>
<img src="/images/performancechart.png" alt="OSPC" style="max-width:1000px; width:100%">

<div align="justify"> We conduct the validation via two methods. One method is the micro level validation by looking at the individual tax units. We have tested against <a style="display:inline-block" href="https://www.nber.org/research/data/taxsim">NBER TAXSIM model</a>, comparing the calculated tax liability (along with the intermediate variables like taxable income, AMT liabities etc.), record by record. The testing suites cover records from differenct income background over the past years. This process has helped the both side of OSPC and NBER TAXSIM to identify the modelling diffeneces and make the corresponding improvements. Once difference is found in <a style="display:inline-block" href="https://github.com/PSLmodels/Tax-Calculator/tree/master/taxcalc/validation"> validatoin </a>, we will fix it if it is bug, or document the difference if it coming from the different assumptions of the models and not having large impacts. So far, tax liability calculation from OSPC model and TAXSIM are bascially in the same line.
<br><br>
The other method is from the macro level by looking at the model produced economic aggregate, comparing the value of projected items with the Congressional Budget Office <a style="display:inline-block" href="https://www.cbo.gov/data/budget-economic-data">10-year economic & revenue projections</a>. Items considered for comparison include the calculation of AGI, calculation of income tax liability and share of AGI by income groups. The chart below is the result of some example items.
</div> 
<br><br>
<img src="/images/validationchart.png" alt="OSPC" style="max-width:1000px; width:100%">
<br>
<p align="justify"> OSPC modelling results match well with CBO's. For example, many key items like Total AGI showing differences less than 1.5% for the next 10 years projections. Please refer to this <a style="display:inline-block" href="https://github.com/PSLmodels/taxdata/tree/master/history/reports">latest report</a> for full list of comparisons with CBO. Generally speaking, our PUF based projection is closer to the CBO projections. Differences may come from micro data selection or different modelling assumptions and methods. 
<br><br>
The valdation work is kept tracked by economists from NBER and CBO as well. The open source nature has largely enchanced the model's reference. Other research organizations has also conducted comparison work with OSPC tax models. For example, Tax Foundation's model indicates the difference of Total AGI projections is around 2~3% till 2031.
</p> 