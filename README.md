# healthcareai

[![Build status](https://ci.appveyor.com/api/projects/status/0xrpe233o9a16l4l/branch/master?svg=true)](https://ci.appveyor.com/project/CatalystAdmin/healthcareai-r/branch/master)

The aim of `healthcareai` is to make it easy to do machine learning with healthcare 
data. The package has two main goals:

-  Allow one to easily create models based on tabular data, and deploy a best
model that pushes predictions to SQL Server.

-  Provide tools related to data cleaning, manipulation, and imputation.

## For those starting out

Installation:

- Find the console of RGui (which comes with R) or RStudio (which is recommended and downloaded separately).

- Install prerequisites:
```R
install.packages(c('caret','data.table','devtools','doParallel','e1071','grpreg','lme4','lubridate','pROC','R6','ranger','ROCR','RODBC'),repos = "https://cran.cnr.berkeley.edu/")
```

- Install the latest release of healthcareai

```{r}
library(devtools)
devtools::install_url('https://github.com/HealthCatalystSLC/healthcareai-r/archive/v0.1.10.zip')
```

- Note: if you want the bleeding edge version, use this:

```{r}
library(devtools)
devtools::install_github(repo='HealthCatalystSLC/healthcareai-r')
```

- Load the package you just installed and read the built-in docs
```{r}
library(healthcareai)
?healthcareai
```

- If you like Jupyter notebooks, check out [step 1](inst/notebooks/Example1.ipynb) and [step 2](inst/notebooks/Example2.ipynb) in model building with healthcareai.

## Contributing

You want to help? Wohoo! We welcome that and are willing to help newbies get started.

First, See [here](CONTRIBUTING.md) for instructions on setting up your development environment

After that's done, *here's the contribution workflow:*

1) Identify an issue that suits your skill level [here](https://github.com/HealthCatalystSLC/healthcareai-r/issues)
   - Only look for issues in the Backlog category
   - Please reach out with questions on details and where to start

2) Create a topic branch to work in, as described [here](CONTRIBUTING.md/create-a-topic-branch-that-you-can-work-in)

3) Create a throwaway file on the Desktop (or somewhere outside the repo), based on an example

4) As you make changes
   - Document any new functions, methods, etc via [roxygen2](http://r-pkgs.had.co.nz/man.html)
   - Be sure to build often
     - Note: building checks for errors and allows you to use the latest code
   - Make small commits after getting a small piece working
   - Push often so your changes are backed up. See [here](https://gist.github.com/blackfalcon/8428401#push-your-branch) for more
   
5) When you're done with the issue you chose, do the following
   
   1. Build and fix any errors

   2. Run tests via `devtools::tests()` or CTRL+SHIFT+D and fix any errors
   
   3. Run the roxygen2 examples via `devtools::run_examples()` and fix any errors

   4. Under the build tab, run 'Check' and verify that only one roxygen warning arises
      - This warning is due to the [limitations](https://github.com/wch/R6/issues/3) of roxygen and R6 method documentation
      - This is the only warning/error/note that's allowed when merging to master
      
   5. Create a [pull request](https://yangsu.github.io/pull-request-tutorial/) so that your changes can be reviewed before merging

## For issues

- Double check that the code follows the examples in the built-in docs
```R
library(healthcareai)
?healthcareai
```
  
- Make sure you've thoroughly read the descriptions found [here](http://healthcare.ai/r/)

- If you're still seeing an error, [file an issue](https://github.com/HealthCatalystSLC/healthcareai-r/issues) that contains
  - Details on your environment (OS, database type)
  - Goals (ie, what are you trying to accomplish)
  - Crystal clear steps for reproducing the error
  
- If you're unsure, feel free to email [Levi Thatcher](mailto:levi.thatcher@healthcatalyst.com)
