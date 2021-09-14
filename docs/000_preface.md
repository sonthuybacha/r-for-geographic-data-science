# Preface {-}

## Lecture slides {-}

1. **R coding**
    - **100 Introduction**
        - 101 [Introduction to R](slides/101-introduction.html)
        - 102 [Core concepts](slides/102-core-concepts.html)
        - 103 [Tidyverse](slides/103-tidyverse.html)
    - **110 R programming**
        - 111 [Data types (vectors, factors, matrices, arrays, lists)](slides/111-data-types.html)
        - 112 [Control structures (conditional statements, loops)](slides/112-control-structures.html)
        - 113 [Functions](slides/113-functions.html)
2. **Data wrangling**
    - **200 Selection and manipulation**
        - 201 [Data Frames](slides/201-data-frames.html)
        - 202 [Data selection and filtering](slides/202-selection-filtering.html)
        - 203 [Data manipulation](slides/203-data-manipulation.html)
    - **210 Table operations**
        - 211 [Join operations](slides/211-data-join.html)
        - 212 [Table pivot](slides/212-tidy-data.html)
        - 213 [Read and write data](slides/213-read-write.html)
    - **220 Reproducibility**
        - 221 [Reproducibility](slides/221-reproducibility.html)
        - 222 [R and Markdown](slides/222-rmarkdown.html)
        - 223 [Git](slides/223-git.html)
3. **Data analysis**
    - **300 Exploratory data analysis**
        - 301 [Data visualisation](slides/301-data-visualisation.html)
        - 302 [Descriptive statistics](slides/302-descriptive-stats.html)
        - 303 [Exploring assumptions](slides/303-exploring-assumptions.html)
    - **310 Comparing data** 
        - 311 [Comparing groups](slides/311-comparing-means.html)
        - 312 [Correlation](slides/312-correlation.html)
        - 313 [Data transformations](slides/313-data-transformations.html)
    - **320 Regression models**
        - 321 [Simple regression](slides/321-regression.html)
        - 322 [Assessing regression assumptions](slides/322-regression-assessing.html)
        - 323 [Multiple regression](slides/323-regression-multiple.html)
4. **Machine learning**
    - **400 Supervised**
        - 401 [Introduction to Machine Learning](slides/401-machine-learning-intro.html)
        - 402 [Artificial Neural Networks](slides/402-neural-networks.html)
        - 403 [Support vector machines](slides/403-support-vector-machines.html)
    - **410 Unsupervised**
        - 411 [Principal Component Analysis](slides/411-principal-components.html)
        - 412 [Centroid-based clustering](slides/412-clustering-centroid.html)
        - 413 [Hierarchical and density-based clustering](slides/413-clustering-hierarchical-density.html)


## Reference books {-}

Suggested reading

- *R for Data Science* by Garrett Grolemund and Hadley Wickham, O'Reilly Media, 2016. See [online book](https://r4ds.had.co.nz/).
- *Machine Learning with R: Expert techniques for predictive modeling* by Brett Lantz, Packt Publishing, 2019. See book [webpage](https://subscription.packtpub.com/book/big_data_and_business_intelligence/9781788295864).

Further reading

- *Programming Skills for Data Science: Start Writing Code to Wrangle, Analyze, and Visualize Data with R* by Michael Freeman and Joel Ross, Addison-Wesley, 2019. See book [webpage](https://www.pearson.com/us/higher-education/program/Freeman-Programming-Skills-for-Data-Science-Start-Writing-Code-to-Wrangle-Analyze-and-Visualize-Data-with-R/PGM2047488.html) and [repository](https://programming-for-data-science.github.io/).
- *The Art of R Programming: A Tour of Statistical Software Design* by Norman Matloff, No Starch Press, 2011. See book [webpage](https://nostarch.com/artofr.htm).
- *Discovering Statistics Using R* by Andy Field, Jeremy Miles and Zoë Field, SAGE Publications Ltd, 2012. See book [webpage](https://www.discoveringstatistics.com/books/discovering-statistics-using-r/).
- *An Introduction to Statistical Learning with Applications in R* by Gareth James, Daniela Witten, Trevor Hastie and Robert Tibshirani, Springer, 2013. See book [webpage](http://faculty.marshall.usc.edu/gareth-james/ISL/).
- *Introduction to Machine Learning with R* by Scott V. Burger, O'Reilly Media, 2018. See book [webpage](https://www.oreilly.com/library/view/introduction-to-machine/9781491976432/).
- *Machine Learning with R, the tidyverse, and mlr* by Hefin I. Rhys, Manning Publications, 2020. See book [webpage](https://www.manning.com/books/machine-learning-with-r-the-tidyverse-and-mlr).
- *Deep Learning with R* by François Chollet with J. J. Allaire, Manning Publications, 2018. See book [webpage](https://www.manning.com/books/deep-learning-with-r?query=deep%20learning%20with%20r).
- *An Introduction to R for Spatial Analysis and Mapping* by Chris Brunsdon and Lex Comber, Sage, 2015. See book [webpage](https://uk.sagepub.com/en-gb/eur/an-introduction-to-r-for-spatial-analysis-and-mapping/book241031).
- *Geocomputation with R* by Robin Lovelace, Jakub Nowosad and Jannes MuenchowSee, CRC Press, 2019. See [online book](https://geocompr.robinlovelace.net/).



## Reproducibility {-}

### Instructor {-}

You can now reproduce granolarr using [Docker](https://www.docker.com/). First [install Docker](https://docs.docker.com/get-docker/) on your system, [install Git](https://git-scm.com/downloads) if not already installed, and [clone this repository from GitHub](https://github.com/sdesabbata/granolarr). You can then either build the sdesabbata/granolarr image running the `Docker_Build.sh` script in the root directory of the repository or simply [pull the latest sdesabbata/granolarr image from the Docker Hub](https://hub.docker.com/repository/docker/sdesabbata/granolarr).

You should now have all the code and the computational environment to reproduce these materials, which can be done by running the script `Docker_Make.sh` (`Docker_Make_WinPowerShell.sh` on Windows using PowerShell) from the repository folder. The script will instantiate a Docker container for the sdesabbata/granolarr image, bind mount the repository folder to the container and execute `Make.R` on the container, clearing and re-making all the materials. The data used in the materials can be re-created from the original open data using the scripts in `src/utils`, as described in `data/README.md`.

For instance, in a unix-based system like Linux or Mac OS, you can reproduce granolarr using the following four commands:


```bash
docker pull sdesabbata/granolarr:latest
git clone https://github.com/sdesabbata/granolarr.git
cd granolarr
./Docker_Make.sh
```

This approach should allow not simply to use the materials as they are, but to easily edit and create your own version in the same computational environment. To develop your own materials, simply modify the code in the repository and run the `Docker_Make.sh` from the repository folder again to obtain the updated materials. 

The [RMarkdown](https://rmarkdown.rstudio.com/) code used to create the materials for the lectures and practical sessions can be found in the `src/lectures` and `src/practicals` folders, respectively. Both folders contain one RMarkdown file per session which contains the headings necessary to create the respective html slides  (compiled to `docs/lectures/html`) and pdf documents (compiled to `docs/practicals/pdf`), whereas the main corpus of the materials can be found in the files included in the respective `contents` folders. The latter files are also used directly to generate the [Bookdown](https://bookdown.org/) version of the materials (which are compiled to `docs/lectures/bookdown` and `docs/practicals/bookdown`). The `docs` folder also contains the files used to generate the [GitHub Pages](https://pages.github.com/) website using the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) Jekyll theme. The `utils` folder also contains the IOSlides templates and some style classes used in the RMarkdown code.


```bash
.
├── DockerConfig
├── data
├── docs
│   ├── _data
│   ├── _pages
│   ├── _posts
│   ├── assets
│   │   └── images
│   ├── exercises
│   ├── lectures
│   │   ├── bookdown
│   │   └── html
│   └── practicals
│       ├── bookdown
│       └── pdf
└── src
    ├── lectures
    │   ├── contents
    │   └── images
    ├── practicals
    │   ├── contents
    │   ├── images
    │   └── materials
    └── utils
        ├── IOSlides
        └── RMarkdown
```

You can edit the materials in the `granolarr` repository folder using RStudio or another editor on your computer and then compile the new materials using Docker. Alternatively, you can follow the *learner* instructions below to start RStudio Server using Docker, and develop your materials in the same environment in which they will be compiled. The first option might be quicker for minor edits, whereas the latter option might be preferable for substantial modifications, and especially when you might need to test your code.


### Learner {-}

As a learner, you can use [Docker](https://www.docker.com/) to follow the practical sessions instructions and complete the exercises. First [install Docker](https://docs.docker.com/get-docker/) on your system, [install Git](https://git-scm.com/downloads) if not already installed, and [clone this repository from GitHub](https://github.com/sdesabbata/granolarr). 

You can then either build the sdesabbata/granolarr image running the `Docker_Build.sh` script in the root directory of the repository or simply [pull the latest sdesabbata/granolarr image from the Docker Hub](https://hub.docker.com/repository/docker/sdesabbata/granolarr).You should now have all the code and the computational environment to reproduce these materials, which can be done by running the script `Docker_RStudio_Start.sh` (`Docker_RStudio_Start_WinPowerShell.sh` on Windows using PowerShell) from the repository folder. 


For instance, in a unix-based system like Linux or Mac OS, you can set up and start the granolarr container using the following four commands:


```bash
docker pull sdesabbata/granolarr:latest
git clone https://github.com/sdesabbata/granolarr.git
cd granolarr
./Docker_RStudio_Start.sh
```

The `Docker_RStudio_Start.sh` script will first create a `my_granolarr` folder in the parent directory of the root directory of the repository (if it doesn't exitst). The script will then instantiate a Docker container for the sdesabbata/granolarr image, bind mount the `my_granolarr` folder and the `granolarr` repository folder to the container and start an RStudio Server.

Using your browser, you can access the RStudio Server running from the Docker container by typing `127.0.0.1:28787` in your address bar, and using `rstudio` as username and `rstudio` as password. As the `my_granolarr` folder is binded, everything that you will save in the the `my_granolarr` folder in your home directory on RStudio Server will be saved on your computer. Everything else will be lost when the Docker container is stopped.

To stop the Docker container, running the script `Docker_RStudio_Stop.sh` (same on Windows using PowerShell) from the repository folder.



## Session info {-}

```r
sessionInfo()
```

```
## R version 4.1.1 (2021-08-10)
## Platform: x86_64-pc-linux-gnu (64-bit)
## Running under: Ubuntu 20.04.3 LTS
## 
## Matrix products: default
## BLAS/LAPACK: /usr/lib/x86_64-linux-gnu/openblas-pthread/libopenblasp-r0.3.8.so
## 
## locale:
##  [1] LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C              
##  [3] LC_TIME=en_US.UTF-8        LC_COLLATE=en_US.UTF-8    
##  [5] LC_MONETARY=en_US.UTF-8    LC_MESSAGES=C             
##  [7] LC_PAPER=en_US.UTF-8       LC_NAME=C                 
##  [9] LC_ADDRESS=C               LC_TELEPHONE=C            
## [11] LC_MEASUREMENT=en_US.UTF-8 LC_IDENTIFICATION=C       
## 
## attached base packages:
## [1] stats     graphics  grDevices utils     datasets  methods   base     
## 
## loaded via a namespace (and not attached):
##  [1] knitr_1.33      xml2_1.3.2      magrittr_2.0.1  downlit_0.2.1  
##  [5] R6_2.5.1        rlang_0.4.11    fastmap_1.1.0   fansi_0.5.0    
##  [9] stringr_1.4.0   tools_4.1.1     xfun_0.25       utf8_1.2.2     
## [13] jquerylib_0.1.4 htmltools_0.5.2 ellipsis_0.3.2  yaml_2.2.1     
## [17] digest_0.6.27   tibble_3.1.4    lifecycle_1.0.0 crayon_1.4.1   
## [21] bookdown_0.23   sass_0.4.0      vctrs_0.3.8     fs_1.5.0       
## [25] evaluate_0.14   rmarkdown_2.10  stringi_1.7.4   compiler_4.1.1 
## [29] bslib_0.2.5.1   pillar_1.6.2    jsonlite_1.7.2  pkgconfig_2.0.3
```