# 2019-06-museums

### R-Script & data

The preprocessing and analysis of the data was conducted in the [R project for statistical computing](https://www.r-project.org/). The RMarkdown script used to generate this document and all the resulting data can be downloaded [under this link](http://koa87.github.io/2019-06-museums/rscript.zip). Through executing `main.Rmd`, the herein described process can be reproduced and this document can be generated. In the course of this, data from the folder `input` will be processed and results will be written to `output`. 


### GitHub

The code for the herein described process can also be freely downloaded from [https://github.com/koa87/2019-06-museums](https://github.com/koa87/2019-06-museums). 


### License

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons Lizenzvertrag" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Dataset" property="dct:title" rel="dct:type">2019-06-museums</span> von <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/koa87/2019-06-museums" property="cc:attributionName" rel="cc:attributionURL">swissinfo.ch</a> is licensed under <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)</a>.


### Data description of output files

#### `museums_answers_ratios.csv`

| Attribute | Type | Description |
|-------|------|-----------------------------------------------------------------------------|
| name | Character | Name of the museum |
| city | Character | City the museum is located |
| canton | Character | Canton the city is in |
| language | Character | Language spoken in the region of the museum |
| big_museum | Boolean | Either NA or 1 for the 10 most visited museums in Switzerland (3 did not answer) |
| single_exh_f | Numeric | Number of female artists in single exhibitions |
| single_exh_m | Numeric | Number of male artists in single exhibitions |
| group_exh_f | Numeric | Number of female artists in group exhibitions |
| group_exh_m | Numeric | Number of male artists in group exhibitions |
| visitors_lastyear | Numeric | Numbers of yearly visitors of the museum (latest year available) |
| female_artists_all | Numeric | Number of female artists - single and group exhibitions combined |
| male_artists_all | Numeric | Number of male artists - single and group exhibitions combined |
| single_exhibitions_all | Numeric | Total number of single exhibitions in this museum |
| group_exhibitions_all | Numeric | Total number of group exhibitions in this museum |
| per_single_exh_f | Numeric | Ratio of female artists in single exhibitions |
| per_single_exh_m | Numeric | Ratio of male artists in single exhibitions |
| per_group_exh_f | Numeric | Ratio of female artists in group exhibitions |
| per_group_exh_m | Numeric | Ratio of male artists in group exhibitions |


### Disclaimer

The published information has been carefully compiled, but does not claim to be up-to-date, complete or correct. No liability is assumed for damages arising from the use of this script or the information drawn from it. This also applies to contents of third parties which are accessible via this offer.


### Original data source

#### Database
 
First, we defined what an art museum is. This is the definition by which we selected the museums we were going to include in our research: an art museum is “a public or private museum or gallery, which exhibits exhibitable artworks, collects and temporarily exhibits fine or applied art (including design, sculptures, but no historical objects and small artworks). One or more permanent exhibitions are not enough, they have to organise temporary exhibitions.”
 
In order to establish a list of Swiss art museums, we started from a list of all 1111 Swiss museums by the [Swiss Federal Statistical Office](https://www.bfs.admin.ch/news/de/2019-0544). We then compared this list to other information (for example a list that was published by Swiss newspaper [Tages Anzeiger](http://blog.tagesanzeiger.ch/datenblog/index.php/865/schweizer-museen-im-check) in 2014 and information provided by the [Association of Swiss museums](https://www.museums.ch//ins-museum/museumssuche/sucheresultate-museen.html). We ended up having a list of 125 art museums and galleries that corresponded to our definition.

 
#### Procedure
 
We contacted all museums per e-mail and asked them if they could send us the following information: A list of all personal exhibitions - with names and gender of the artist - that took place between 2008 and 2018, as well as a list of all collective exhibitions with female and male artists divided by gender (no names necessary) for the same period. When possible, we said we would like to have these as separate lists in chronological order or listed by year, otherwise aggregated for the whole time span. We chose the time span of eleven years, because we knew that for most museums it meant a lot of work to put the information together. Nevertheless, 11 years is a significant amount of time. We contacted most museums at the end of March and and asked to receive the data by May 5th. We cannot give an analysis on how the situation has developed during this time span, as many museums didn't separate their data into years.
 
Definition of personal or single exhibition: "an exhibition showing the artwork of only one artist or of more than one artist if they are identified as an artistic collective". In this last case, each artist is counted in the statistic of single exhibitions – for example in a collective of 4 artists there can be 3 men and 1 woman. Everything else is considered as group exhibition – also when the exhibition is only showcasing the artwork of two artists, but which are not working as a collective. 

Over the period of 6 weeks we got answers from almost all museums. 73 send us this information, however 16 of them only sent the information for the single exhibitions. In 5 cases, there were no group exhibitions. In 7 cases, we counted the information ourselves on their website (Fondation Beyeler, Mamco, Kunsthaus Glarus, Alte Fabrik, Pinacoteca communale Communale, Fotomuseum Winterthur, Kunsthaus Zug).

Queer artists: Since the main topic of our research is the visibility of female artists, as compared to male, we decided to adopt a binary gender definition when asking the museums for their data. However of course, not everybody identifies with one of these genders. Thus, when sending us the requested information, some of the museums pointed out that in the same period they exhibited queer artists as well. These artists were not included in the final numbers. Kunstmuseum Luzern: single exhibitions: one queer arist, group exhibitions: 3 queer artists. Kunsthalle Basel: 1 queer artist in a group exhibition. Migros Museum für Gegenwartskunst: 1 queer artist in single exhibitions, 2 queer artists in the group exhibitions. 

Remarks: The Antikenmuseum Basel mostly exhibits antique artefacts. They only sent us data for two exhibitions with modern art. For the following museums, we don't have data for the full period of 2008 - 2018: Kunst(Zeug)Haus (data from 2008 to 2016), Kunst+Wissen (2014 to 2018, no temporary exhibitions before that time), Musée des beaux-arts in Le Locle (no data for 2011 and 2012, museum was closed), MASI Lugano: before 2015, they were two separate museums, this is why we couldn't access the archive for the exhibitions between 2008 and 2015, and therefore there is no data available, Museum of Digital Art: They only opened in 2016, therefore we did not include the data in the analysis.