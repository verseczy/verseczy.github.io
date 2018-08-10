---
layout: post
title: Create a “Map” of the Web Proposal
---

# Create a “Map” of the Web
## Google Summer of Code Proposal, 2018
Name: Zhengyue Cheng
### Problem description
Internet Archive is a “non-profit digital library of millions of free books, movies, software, music, websites, and more”. Wayback Machine from Internet Archive is a website which can help people to find specific webpages from 1996. In it, people can search and link webpages they
like and find their “history”.
Since it contains more than 600 billion archives today, these huge amounts of webpages need to be analyzed. Produce the reports about hosts and domains of the archives, and helping to inform web archiving efforts. In addition, this analysis will combine with third party data in order to improve this archiving program.
### Implementation plan
Crawl the website pages and classify these websites according to their domains, hosts and their contents. For this part, we can use Spark MLlib to make the classification because it has powerful classifiers of machine learning algorithms. After completing the clustering of these website pages, we can use MapReduce to achieve the classification storage of these webpages, storing them into database and managing them via HBase.
After finishing the classification storage, draw the graph of them and choose the best algorithms for general graphs like the topology-shapes-metrics approach and the force-directed approach. Show the result by using WebGL and write the report about it, via these, we can make contribution to the academic paper. In addition, based on the result of this program, it can help to improve the web archiving program with the third party data.
### Deliverables
- • Blog posts 
- • Graphs
- • Reports
- • Planning documents
- • Contribution to an academic paper

### Timeline
May.3 – May.16
Make preparation about literature reviews and familiarize with the method and algorithms about data clustering and visualization.
May.17 – May.31
Build the development environment. Contact with the mentor to understand the context and goal of the project.
Jun.1 – Jun.30
Design and develop the data clustering model, analyzing performance and the next improvements.
July.1 – July.25
Integrate the clustering model into the Wayback machine system, and develop the visualization program.
July.26 – Aug.1
Do integration test and begin to write research paper about it. Complete the whole project and paper work.
Aug 2 – 16
Have some extra time to refine and make improvement or adjustment of this project and paper about the project.


         


