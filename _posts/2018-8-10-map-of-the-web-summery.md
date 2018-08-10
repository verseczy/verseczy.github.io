---
layout: post
title: Create a “Map” of the Web Summery
---
# GSoC 2018 map of the web
## Describe my work briefly

- Complete statistic work of the CDX records of internet archive.
- Complete the foundationDB database to store big data of website information records.
- Complete the clustering of domain names and calculating the similarity of other domain names which are in the cluster.

## What is done

- Compute the total number of CDX records of each domain name and present the result via bokeh.
- Present the frequency and show the changes of each domain names from crawling. 
- Build the database to store the big data of similar web of domain names via foundationDB.
- Build the interface/webpage for users searching domain name and presenting the result on the webpage via Django.
- Optimize the speed of storing the data into database using transaction.
- Deploy the webpage on Internet Archive researcher box via Apache.
- Get the response of tagcloud API and preprocess the response, storing the results into files.
- Compute the word frequency of domain names and build LDA model for clustering all domain names.
- Use word2vec to process the words getting from domain names and compute the similarity between them via tf-idf. 
- Present the top 10 domain names with the highest similarity of the searching one on the interface/webpage.

## TODO

- Deploy the interface/webpage of clustering result and similarity result on Internet Archive researcher box.
- Build database to store the clustering result and similarity.

## Others useful link

[Github commits](https://github.com/internetarchive/map-of-the-web/commits/first-version "Github commits")

[GSoC dashboard](https://summerofcode.withgoogle.com/dashboard/ "GSoC dashboard")

[Proposal of map of the web](https://verseczy.github.io/Create-a-Map-of-the-Web-Proposal/ "Proposal of map of the web")

[GSoC 2018 map of the web - Internet Archive experience](https://verseczy.github.io/map-of-the-web-experience/ "GSoC 2018 map of the web - Internet Archive experience")
