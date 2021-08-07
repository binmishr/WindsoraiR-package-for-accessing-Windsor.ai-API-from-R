# WindsoraiR-package-for-accessing-Windsor.ai-API-from-R

I recently got acquainted with Windsor.ai – a hub for connecting various sources of marketing data like Facebook ads or Google Analytics. The platform is interesting because it provides ways to analyze and visualize your merged marketing data through template dashboards or to pipe the data to any number of tools (Python, R, Google data Studio, Tableau, etc). In collaboration with the people at Winsdor.ai, I developed a very simple package to interface with the Windsor.ai API.

The new package, called windsoraiR, is available on CRAN and on Github. Its first incarnation is rather simple. I just provide one function to access the API and return the queried data in the form of a data.frame making it super easy to do some additional wrangling, charting or analysis. To access data from the Windsor.ai API, one needs to acquire a free API key and set up data sources (this can be pretty much any online channel of marketing data, see more on the Windsor.ai website).

We install from CRAN:

install.packages("windsoraiR")

Or using remotes or devtools:

# install.packages("remotes")
remotes::install_github("windsor-ai/windsoraiR")

Once we have the package installed, we can fetch data using winsdoraiR::winsdor_fetch():

winsdor_data <- 
windsor_fetch(api_key = "your api key",
 connector = "all",
 date_preset = "last_7d",
 fields = c("source", "campaign", "clicks",
            "medium", "sessions", "spend"))

This, of course, is work in progress and I would love feedback and ideas for future development. How might one want to query the API and or what helper function might be good to have to process the results in R once data has been pulled? Issues and pull requests are welcomed on Github. By the way, for the python lovers, a python package equivalent to winsdoraiR 
