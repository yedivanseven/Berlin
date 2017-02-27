# Berlin
## Some lesser known facts about Berlin
Both the budget of Berlin and a wealth of demographic data about this fine city
is openly and freely available on the interweb. This repository contains
several `IPython` notebooks that explore and connect various aspects of the
data, some of which are showcased on
[www.100-percent.net](http://www.100-percent.net).

### 1. Budget
Extract, collect, and examine the budget of both the city and the state of
Berlin from published data. Note that this is only for what the powers that be _planned_ or _plan_ to spend. Much less data is available on what the actually
_did_ spend (and that's not counting BBI Airport).

### 2. Gentrification
Based on swaths of demograpic data, the original goal was to localize
"gentrification" among Berlin's boroughs. After trying a wide range of metrics,
one could be identified that allowed clustering algorithms to divide Berlin
into at least four different kinds of neighborhoods with distinct
demographic characteristics. These are then plotted onto an interactive
OpenStreet map (see ClusterMap.html for an example).

##### Specific dependencies
+ `pyshp 1.2.10`
+ `folium 0.2.1`

### 3. WhereDoYouLive
Knowing all these demographics, we can try our best to locate you on an
interactive OpenStreet map (see PosteriorMap.html for one example), if you provide some detail about yourself. This is done within a Naive Bayes framework.

##### Specific dependencies
+ `pyshp 1.2.10`
+ `folium 0.2.1`

### 4. PlanWisely
Putting one and one together is harder than it sounds. Knowing the budget of
Berlin and quite a bit about its demography, can we actually measure the infinite wisdom of the city fathers in their budget allocation? Can we discern clear-cut
correlations (or their absence) between certain demographic groups and certain
budget items? The answer is far from straightforward and this is very much
work in progress. So far it is mostly an exercise in

+ various flavors of (genralized) linear models,
+ model selection (best-subset and forward),
+ cross-validation,
+ dimensionality reduction (PCA, PLS, and CCA).

## General Dependencies
Everything seems to run smoothly on a relatively fresh Anaconda 4.3 install
(this is for `python 3.6`).

## Data sources
While the data are free and open to access for everyone, they are published
under a different license and can, therefore, not be redistributed here.
The [demographic](https://daten.berlin.de/kategorie/demographie) data files
have been mildy edited to homogenize column lables _etc_. The
[budget](https://daten.berlin.de/kategorie/%C3%B6ffentliche-verwaltung-haushalt-und-steuern) data have additionally between split into individual years, where
only biannual budgets were available. The [geographic](https://daten.berlin.de/datensaetze/rbs-lor-lebensweltlich-orientierte-r%C3%A4ume-dezember-2015) data can be read in with the `pyshp` package
but has been converted to the geo-json format needed by `folium` with the
wonderful [QGIS](http://www.qgis.org/).
