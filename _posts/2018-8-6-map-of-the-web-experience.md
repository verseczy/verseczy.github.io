---
layout: post
title: Create a “Map” of the Web Experience
---
# GSoC 2018 Map of the web – Internet Archive
### Aims

Internet Archive is a “non-profit digital library of millions of free books, movies, software, music, websites, and more”. Wayback Machine from Internet Archive is a website which can help people to find specific webpages from 1996. In it, people can search and link webpages they like and find their “history”. 

This project aims:

Produce reports for the domain names’ CDX records and do some statistic work for them.

Build database to combine with third party data, like similar web in this project.

Do some analysis work to understand domain names better.

## The work has been done in this summer
### Part 1

Complete the statistic work of CDX records for domain names from Internet Archive.

CDX records are results from crawling different domain names and stored as the information of them. It contains the digest, urlkey, timestamp, mimetype, original, statuscode, length and snapshot url for each domain name. Using these records, we can know the basic information of domain names.

In this part, I counted the total number of CDX records of each domain name, showed the frequency of crawling from domain names using timestamp and analyzed the changes of digest of same domain names.

Finally, present the result on webpage via bokeh.

### Part 2

Complete the foundationDB database to store big data of website information records.

In this part, I built the database to store the big data of similar web of different domain names via foundationDB. Then, for presenting the information of each domain name, I built the webpage as an interface via Django, for searching and showing the domain name information in json format. Because of the large size of data, I used transaction to optimize the speed of storing the data into database. 

### Part 3

Complete the clustering of domain names and calculating the similarity of other domain names which are in the cluster.

In this part, firstly, I got the response of tagcloud API and preprocessed the responses by cleaning unicode and separating whole sentences into words. Then I stored the results into txt files for next step.

I computed the word frequency of different domain names for building LDA model to do the clustering task for all domain names. Also, I used word2vec process the words getting from domain names and compute the similarity between them via tf-idf.

Finally, present the top 10 domain names with the highest similarity of the searching one on the interface/webpage.

### Challenges

In this project, I met many difficulties and problems.

For the coding part, I was confused about how to select frameworks and tools to complete functions or programs at first. For example, I needed an interface and it was more suitable to use a simple webpage to represent the result at first version. I always imagined tasks very complex and did not know how to start. Through this project, I learned to “divide and conquer”, dividing a problem into small ones and conquering them. In addition, I learned many tools and frameworks, like Django to build a search website to present the results or foundationDB to create a database for storage of data. 

For the communication part, it is very important for me to learn how to communicate with other people. In the beginning, I was not clear about the work of this project, like what should I do, how to complete the project. 

During the project, I communicated with my mentor or other people to find out solutions. It is very helpful to talk with others to sort things out and it is also useful for eliminating misunderstandings and updating the progress of my work.

### Learning and benefits for the future career

Except learning exact tools in this project, it is my first time working in United States. It has lots of difference between work in China and America. And it is really a beneficial experience for me to adapt the work environment. My mentors and other people in Internet Archive are very friendly and patient. They gave me many good suggestions in both coding and communicating, and because of them, I had the confidence to complete this project.

Through this project, I reviewed and learned many skills in web and database and it is very helpful for my future career like basic skills. Also, I notice I am more interested in algorithms and building models. In the future, I may try to find job in this area. 

Thanks to Mark, David and Dan, I really have an unforgettable experience in CSoC and Internet Archive. 

