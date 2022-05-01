# Maximilian Stubbemann and Tobias Koopmann: The German and International AI Network Data Set.

## Content
This repository provides a pipeline to create several datasets about authors and publications in the realm of artificial intelligence.  
These datasets are provided as JSONL files, storing several information as key-values pairs. The different data sets are defined as follows:

- ai\_dataset.json: This file contains all publications, which have been published on an  AI conference.(*)
- german\_ai_dataset.json: This file contains all publications, which have been published on a  AI conferences (*) and have at least one author with a German affiliation in DBLP.
- ai\_community_dataset.json: This file contains all publications of authors, which have published at least one publication on one of the AI conferences. (*)
- german\_ai\_community_dataset.json: This file contains all publications of German authors (according to DBLP), which have published at least one publication on one of the given AI conferences. (*)
- persons.json: This file contains information about all researchers in the realm of AI.
- german\_persons.json: This file contains information about all German researchers in the realm of AI.

We use the AI conferences that are collected in the [paper](https://arxiv.org/pdf/1903.09516.pdf) by Kristian Kersting et al.

The publication information base on the DBLP data set (currently 2020-01-01). Based on this XML, we extract all publications published on one of the conferences mentioned above.  
After extracting these publications, we extract all their authors and search for further information (e.g. country, affiliation and URLs) in the dblp.xml and extract all of their publications (articles in conference proceedings and journal articles).  
Afterwards, we match all publications with the public available Semantic Scholar dataset (currently the release from 2020-01-01) in order to add information about the in citation count.  
Finally, we identify the German authors in the data to provide data sets about the German AI crowd.

The pipline will start when executing the file main.py within the Code/ directory. First please install the requirements. The pipeline will download the DBLP dump. Semantic Scholar will be downloaded automatically if it is not already present. The execution of the script will take several hours of time. The most time consuming part is (in our experience) the download of the Semantic Scholar Corpus, if it is not already on disk.

### WARNING:
To match the data with the additional semantic scholar info, the Semantic Scholar Research Corpus will be downloaded and will be written to disk. The compressed corpus will take about 115 Gigabyte of Disk Space.

## DBLP Data
You need to run the script main.py within the Code/ directory to generate the full dataset with abstracts and citation information. However, if you dont need this information, we provide the datasets without the information from Semantic Scholar in the zipped directory dblp\_data.

## DBLP and Semantic Scholar Licenses
The DBLP dump is licensed under [CC0](https://creativecommons.org/publicdomain/zero/1.0/). If you generate and use the data that incorporates the information of Semantic Scholar: note that the Semantic Scholar is published under the following [license](http://api.semanticscholar.org/corpus/legal/).

## Credits
If you use this work, we strongly ask you to cite us by using the citation information from Zenodo.

However, as our data is build upon the DBLP data, we also advise you to cite the DBLP data. Our script downloads and uses the dump from 2020-01-01 which can be cited as:  

**The dblp team: dblp computer science bibliography. Monthly snapshot release of November 2019. https://dblp.org/xml/release/dblp-2020-01-01.xml.gz**.

If you use the data that contains the info extracted from Semantic Scholar, we advice you to also cite Semantic Scholar by citing

**Construction of the Literature Graph in Semantic Scholar** by Ammar et al.

The complete bibtex can be found [here](https://api.semanticscholar.org/corpus/).

## License
The German and International AI Network Data Set (c) by Maximilian Stubbemann and Tobias Koopmann

The German and International AI Network Data Set is licensed under a
Creative Commons Attribution-ShareAlike 4.0 International License.

You should have received a copy of the license along with this
work. If not, see <http://creativecommons.org/licenses/by-sa/4.0/>.
