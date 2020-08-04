# Frequently Asked Questions

## How to access the course material in Github

Instead of trying to download each file separately via the Github interface, it is recommended to use one of these options:
 - The best way is to clone the repository using git, and use pull to get the latest updates.
   - If you want to learn to use git, start by installing a [git client](https://www.google.com/search?q=git+clients&oq=git+client). There are plenty of good git tutorials online.
 - If you don't want to learn to use git, download a the repository as a zip file. Click the green button "Code" at the main page of the repository and choose "Download ZIP" ([direct link](https://github.com/avehtari/BDA_course_Aalto/archive/master.zip)). Remember to download again during the course to get the latest updates.

## Problems installing R packages on Windows ?

> ⚠️ Note that getting the setup needed for the course working on Windows might involve a bit more effort than on Linux and Mac. Consequently, **we recommmend using either Linux or MacOS**.
> Moreover, `Stan`, the probabilistic programming language which we will use later on during the course requires a C++ compiler toolchain which is not available by default in Windows (blame Microsoft).
> However, if you insist on using Windows and have a problem getting the setup working, below are two options to consider:

## How to use R and RStudio remotely

### Option 1: Using R and RStudio via Jupyterhub

Instead of installing RStudio on your computer, you can use it in your web browser:
- go to [jupyter.cs.aalto.fi](jupyter.cs.aalto.fi)
- choose `R: General use (JupyterLab) 3.0.0`
- in the Launcher click `RStudio`
- in the RStudio Files pane (bottom right) you can create folders for your work and upload files from your computer to the server 
  - the **notebooks** folder is currently the only persistent folder (stays there if you sign out) so save everything to that folder!
  - You may get an error when uploading a large zip file, but uploading smaller zip files work. The maximum filesize will be increased in the future.
- after uploading files use Files pane to open them ()e.g. an RMarkdown notebook)
- knitting of R and Rmd files works as well
- when running RStan, there is currently extra dialog popping up which required clicking Yes, but this will be fixed in near future
  - there is a limited memory available (3Gib) and bigger models and datasets can run out of memory with cryptic error message

###  Option 2: Use Aalto Linux via remote-desktop solution provided by Aalto-IT.

* Goto `vdi.aalto.fi`
* Download VMWare Horizon application or use the web portal
  * If using the VMWare Horizon application, click on `New Server` and enter `vdi.aalto.fi`
* Enter your aalto username (aalto email works too) and password in the respective fields.
* Select `Ubuntu 18.04`
* Open `RStudio` from the panel on the left

## Error related to LC_CTYPE while installing `aaltobda` r-package.
One of the reported errors was as follows:
```
I'm having problems downloading the github code. I keep getting the following error message:
Error: (converted from warning) Setting LC_CTYPE failed, using "C"
Execution halted
Error: Failed to install 'aaltobda' from GitHub:
 (converted from warning) installation of package '/var/folders/g6/bdv4dr4s6qq4zyxw2nzy26kr0000gn/T//Rtmp3uYwuD/file121f355845a3/aaltobda_0.1.tar.gz' had non-zero exit status
 ```

### Solution
See the following StackOverflow solution. ([link](https://stackoverflow.com/a/3909546))

## Installing `knitr`
If you just installed RStudio and R, chances are you don't have `knitr` installed, the package responsible of rendering your pdf.

### Solution
```{r}
install.packages("knitr")
```
You can also install packages from RStudio menu `Tools->Install Packages`.

## If `knitr` is installed but the pdf won't compile
In this case it is possible that you don't have LaTeX installed, which is the package that runs the engine to process the text and render the pdf itself.

### Solution
Tinytex is the bare minimum Latex core that you need to install in order to run the pdf compiler. If you want to go further and download a full distribution of Latex, look at texlive for linux and mactex for macOS.

```{r}
install.packages("tinytex")
tinytex::install_tinytex()
```

## How to install the latest version of `RStan`
* Make sure you have installed R version 3.4.0 or newer. If you don't, install a newer version using instructions from [https://www.r-project.org/](https://www.r-project.org/)
* Install `RStan` along with the necessary C++ compiler toolchain as described [here](https://github.com/stan-dev/rstan/wiki/RStan-Getting-Started)


## What is `tidyr` or `tidyverse` that is used in the R demos? What does `%>%` mean?
* [Tidyverse](https://www.tidyverse.org/) is a collection of R packages designed for data science. The packages "share an underlying design philosophy, grammar, and data structures".
* A clear characteristic that distinguishes tidyverse from the base R is the [pipe operator](https://style.tidyverse.org/pipes.html) `%>%`
* In this course you do not need to use tidyverse. However, some packages belonging to tidyverse, such as `ggplot2`, can be useful for visualizing results in the reports.

