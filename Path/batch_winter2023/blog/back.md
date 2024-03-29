# Backend Path - Winter 2023

## Content table
- [Content Table](#content-table)
- [Week 1](#week-1)
  - [Exercise: Essentials and Spring Boot](#essentials-and-spring-boot)
- [Week 2](#week-2)
  - [Exercise: Introduction to Spring](#introduction-to-spring)
  - [Exercise: Web APIs](#web-apis)
- [Week 3](#week-3)
  - [Exercise: MultipartFile and Async](#multipartfile-and-async)
- [Week 4](#week-4)
  - [Exercise: Imbd files](#imdb-files)
- [Week 5](#week-5)
  - [Exercise: Elasticsearch I](#elasticsearch-i)
- [Week 6](#week-6)
  - [Exercise: Elasticsearch II](#elasticsearch-ii)
- [Week 7](#week-7)
  - [Exercise: Elasticsearch III](#elasticsearch-iii)
- [Week 8](#week-8)
  - [Exercise: Elasticsearch IV](#elasticsearch-iv)
- [Week 9](#week-9)
  - [Finishing IMDb Project](#finishing-imdb-project)
- [Week 10](#week-10)
  - [Retail Trust Index](#retail-trust-index)
  - [My Motive Search](#my-motive-search)
- [Week 11](#week-11)
  - [Retail Trust Index](#retail-trust-index)
  - [My Motive Search](#my-motive-search)
----------------------------------------------------------------

## Week 1

### Essentials and Spring Boot

13/02/2023 - 17/02/2023

| **Content Deliverer** |
| ------------------ |
| Roberto Auro |

**Key learning points**
1. Installation of essential (Homebrew, sdk, java ...)
2. Introduction to Maven
3. Introduction to Spring Boot

### Exercise
The first week we were installing and configuring the tools we are going to use and we have done a small individual exercise in Spring in which we had to connect to Elasticsearch and test it.

- Installing Homebrew
- Installing SDK man
- Installing Java
- Installing Maven
- Downloading IntelliJ IDEA (CE)
- Downloading Docker (CE)
- Running Elasticsearch

----------------------------------------------------------------

## Week 2

### Introduction to Spring

27/02/2023 - 03/03/2023

| **Content Deliverer** |
| ------------------ |
| Roberto Auro |

**Key learning points**
1. Introduction to Spring Framework

In this session we got an introduction to Spring, how to inject dependencies, and the layered arquitecture we will use for the projects.  
Our first assignment consisted of making a component that could connect to Elastic and connecting our service classes to said component. We had to make test to ensure this connection is established correctly and itrs referenced correctly. Also, we had to use Docker to be able to run our application and the Elasticsearch container.

- #### [Exercise 1](https://github.com/juanma6245) by [Juan Manuel Manga](https://github.com/juanma6245) 
- #### [Exercise 1](https://github.com/Warkos99/EmpathyAcademy) by [Marcos Arce](https://github.com/Warkos99)  
- #### [Exercise 1](https://github.com/ChristianGm25) by [Christian González](https://github.com/ChristianGm25) 
- #### [Exercise 1](https://github.com/noeliaigc/search-academy-project) by [Noelia Iglesias](https://github.com/noeliaigc) 
- #### [Exercise 1](https://github.com/taniabg23/search-academy-project) by [Tania Bajo](https://github.com/taniabg23)
- #### [Exercise 1](https://github.com/gdeleiva/search-academy-project) by [Guillermo de Leiva](https://github.com/gdeleiva) 
- #### [Exercise 1](https://github.com/josperrod9) by [José Pérez](https://github.com/josperrod9) 
- #### [Exercise 1](https://github.com/Laisgs) by [Laís García](https://github.com/Laisgs) 
- #### [Exercise 1](https://github.com/laura-pb/search-academy-project/tree/Assigment_1) by [Laura Pernía](https://github.com/laura-pb) 
- #### [Exercise 1](https://github.com/Raul-Alv/search-academy-project) by [Raúl Álvarez](https://github.com/Raul-Alv) 


### Web APIs

27/02/2023 - 03/03/2023

| **Content Deliverer** |
| ------------------ |
| Roberto Auro |

**Key learning points**
1. Introduction to HTTP and HTTP verbs
2. Introduction to REST

The second session was about web APIs. In it we learned about the HTTP protocol, as well as HTTP verbs such as GET, POST, PUT, and their correct uses. Also we talked about REST and its uses, as well as its architecture and how this is tied to out assignments on Spring. We had to do an individual exercise of creating an API for a CRUD of users using the HTTP verbs. 

Here are the links for the GitHub repositories from the Backend&Search academies for the assignments:
- #### [Exercise 2](https://github.com/juanma6245) by [Juan Manuel Manga](https://github.com/juanma6245) 
- #### [Exercise 2](https://github.com/Warkos99/EmpathyAcademy) by [Marcos Arce](https://github.com/Warkos99) 
- #### [Exercise 2](https://github.com/ChristianGm25/academy_search/tree/assignment_users) by [Christian González](https://github.com/ChristianGm25) 
- #### [Exercise 2](https://github.com/noeliaigc/search-academy-project) by [Noelia Iglesias](https://github.com/noeliaigc) 
- #### [Exercise 2](https://github.com/taniabg23/search-academy-project) by [Tania Bajo](https://github.com/taniabg23) 
- #### [Exercise 2](https://github.com/gdeleiva/search-academy-project) by [Guillermo de Leiva](https://github.com/gdeleiva) 
- #### [Exercise 2](https://github.com/josperrod9) by [José Pérez](https://github.com/josperrod9) 
- #### [Exercise 2](https://github.com/Laisgs) by [Laís García](https://github.com/Laisgs) 
- #### [Exercise 2](https://github.com/laura-pb/search-academy-project/tree/Assigment_2) by [Laura Pernía](https://github.com/laura-pb) 
- #### [Exercise 2](https://github.com/Raul-Alv/search-academy-project) by [Raúl Álvarez](https://github.com/Raul-Alv) 

----------------------------------------------------------------

## Week 3

### MultipartFile and Async

06/03/2023 - 10/03/2023

| **Content Deliverer** |
| ------------------ |
| Roberto Auro |

**Key learning points**
1. Uploading Multipart Files
2. Use of Async notation

In this third week we couldn't have the learning session but we were told to complete the Web Api exercise with a method that should upload a MultipartFile and then another with the same functionality but using the @Async annotation. The implementation of this approach can be found in the exercise 2 solution.

----------------------------------------------------------------

## Week 4

### IMDb files

13/03/2023 - 17/03/2023

| **Content Deliverer** |
| ------------------ |
| Roberto Auro |

**Key learning points**
1. Index IMDb files

This week we had the fourth session and we continued with Web Apis. Roberto showed us a possible solution for the crud exercise and some of us shared our code so we review and comment it. In addition, he asked us to take a look to some imdb files that we are going to use for our project with the Frontend members and to start uploading and indexing them. He also showed us the JobRunr, a library for background processing in Java.

- #### [Exercise 3](https://github.com/juanma6245/search-academy-project/tree/Assignment_2_Web_Api_Upload_CSV) by [Juan Manuel Manga](https://github.com/juanma6245) 
- #### [Exercise 3](https://github.com/Warkos99/EmpathyAcademy) by [Marcos Arce](https://github.com/Warkos99)  
- #### [Exercise 3](https://github.com/ChristianGm25/academy_search) by [Christian González](https://github.com/ChristianGm25) 
- #### [Exercise 3](https://github.com/noeliaigc/search-academy-project/tree/exercise3) by [Noelia Iglesias](https://github.com/noeliaigc) 
- #### [Exercise 3](https://github.com/taniabg23/search-academy-project/tree/api-crud) by [Tania Bajo](https://github.com/taniabg23)
- #### [Exercise 3](https://github.com/gdeleiva/search-academy-project/tree/exercise4) by [Guillermo de Leiva](https://github.com/gdeleiva) 
- #### [Exercise 3](https://github.com/josperrod9/search-academy-project/tree/web-api) by [José Pérez](https://github.com/josperrod9) 
- #### [Exercise 3](https://github.com/Laisgs/search-academy-project/tree/lais) by [Laís García](https://github.com/Laisgs) 
- #### [Exercise 3](https://github.com/laura-pb/search-academy-project/tree/IMDBInitialSteps) by [Laura Pernía](https://github.com/laura-pb) 
- #### [Exercise 3](https://github.com/Raul-Alv/search-academy-project) by [Raúl Álvarez](https://github.com/Raul-Alv) 

----------------------------------------------------------------

## Week 5

### Elasticsearch I

20/03/2023 - 24/03/2023

| **Content Deliverer** |
| ------------------ |
| Roberto Auro |

**Key learning points**
1. Introduction to Elasticsearch

----------------------------------------------------------------

## Week 6

### Elasticsearch II

27/03/2023 - 31/03/2023

| **Content Deliverer** |
| ------------------ |
| Roberto Auro |

**Key learning points**
1. Introduction to Elasticsearch

This week we have been learning more about ElasticSearch and we started with indexing.


- #### [IMDB indexing](https://github.com/juanma6245/search-academy-project) by [Juan Manuel Manga](https://github.com/juanma6245) 
- #### [IMDB indexing](https://github.com/Warkos99/EmpathyAcademy) by [Marcos Arce](https://github.com/Warkos99)  
- #### [IMDB indexing](https://github.com/ChristianGm25/academy_search) by [Christian González](https://github.com/ChristianGm25) 
- #### [IMDB indexing](https://github.com/noeliaigc/IMDb-project) by [Noelia Iglesias](https://github.com/noeliaigc) 
- #### [IMDB indexing](https://github.com/taniabg23/search-academy-project/tree/imdb) by [Tania Bajo](https://github.com/taniabg23)
- #### [IMDB indexing](https://github.com/gdeleiva/search-academy-project) by [Guillermo de Leiva](https://github.com/gdeleiva) 
- #### [IMDB indexing](https://github.com/josperrod9/IMDb-project) by [José Pérez](https://github.com/josperrod9) 
- #### [IMDB indexing](https://github.com/Laisgs/search-academy-project/tree/actualMain) by [Laís García](https://github.com/Laisgs) 
- #### [IMDB indexing](https://github.com/laura-pb/search-academy-project/tree/main) by [Laura Pernía](https://github.com/laura-pb) 
- #### [IMDB indexing](https://github.com/Raul-Alv/search-academy-project/tree/imdb) by [Raúl Álvarez](https://github.com/Raul-Alv) 



----------------------------------------------------------------

## Week 7

### Elasticsearch III

03/04/2023 - 05/04/2023

| **Content Deliverer** |
| ------------------ |
| Roberto Auro |

**Key learning points**
1. Finishing indexing and introducing mapping

This week we have been working on the assignment from both week 5 and week 6, since this week ended early we didnt have another session.

- #### [IMDB indexing](https://github.com/juanma6245/search-academy-project) by [Juan Manuel Manga](https://github.com/juanma6245) 
- #### [IMDB indexing](https://github.com/Warkos99/EmpathyAcademy) by [Marcos Arce](https://github.com/Warkos99)  
- #### [IMDB indexing](https://github.com/ChristianGm25/academy_search) by [Christian González](https://github.com/ChristianGm25) 
- #### [IMDB indexing](https://github.com/noeliaigc/IMDb-project) by [Noelia Iglesias](https://github.com/noeliaigc) 
- #### [IMDB indexing](https://github.com/taniabg23/search-academy-project/tree/imdb) by [Tania Bajo](https://github.com/taniabg23)
- #### [IMDB indexing](https://github.com/gdeleiva/search-academy-project) by [Guillermo de Leiva](https://github.com/gdeleiva) 
- #### [IMDB indexing](https://github.com/josperrod9/IMDb-project) by [José Pérez](https://github.com/josperrod9) 
- #### [IMDB indexing](https://github.com/Laisgs/search-academy-project/tree/actualMain) by [Laís García](https://github.com/Laisgs) 
- #### [IMDB indexing](https://github.com/laura-pb/search-academy-project/tree/main) by [Laura Pernía](https://github.com/laura-pb) 
- #### [IMDB indexing](https://github.com/Raul-Alv/search-academy-project/tree/imdb) by [Raúl Álvarez](https://github.com/Raul-Alv) 

----------------------------------------------------------------
## Week 8

### Elasticsearch IV

10/04/2023 - 14/04/2023

| **Content Deliverer** |
| ------------------ |
| Francisco García López |

**Key learning points**
1. Introduction to aggregations 

This week we have been learning more about aggregations in ElasticSearch and we continue doing the search endpoints.

- #### [AGGREGATIONS](https://github.com/juanma6245/search-academy-project) by [Juan Manuel Manga](https://github.com/juanma6245) 
- #### [AGGREGATIONS](https://github.com/Warkos99/EmpathyAcademy) by [Marcos Arce](https://github.com/Warkos99)  
- #### [AGGREGATIONS](https://github.com/ChristianGm25/academy_search) by [Christian González](https://github.com/ChristianGm25) 
- #### [AGGREGATIONS](https://github.com/noeliaigc/IMDb-project) by [Noelia Iglesias](https://github.com/noeliaigc) 
- #### [AGGREGATIONS](https://github.com/taniabg23/search-academy-project/tree/imdb) by [Tania Bajo](https://github.com/taniabg23)
- #### [AGGREGATIONS](https://github.com/gdeleiva/search-academy-project) by [Guillermo de Leiva](https://github.com/gdeleiva) 
- #### [AGGREGATIONS](https://github.com/josperrod9/IMDb-project) by [José Pérez](https://github.com/josperrod9) 
- #### [AGGREGATIONS](https://github.com/Laisgs/search-academy-project/tree/actualMain) by [Laís García](https://github.com/Laisgs) 
- #### [AGGREGATIONS](https://github.com/laura-pb/search-academy-project/tree/main) by [Laura Pernía](https://github.com/laura-pb) 
- #### [AGGREGATIONS](https://github.com/Raul-Alv/search-academy-project/tree/imdb) by [Raúl Álvarez](https://github.com/Raul-Alv) 

----------------------------------------------------------------
## Week 9

### Finishing IMDb project

17/04/2023 - 21/04/2023

This week we didn't have any learning session, as it was devoted to finishing the IMDb project. We spent our time adding last minute functionalities, solving integration problems with our front-end fellow and fixing any bug we could find.
Here is the result of our hard work:

- #### [IMDb Project](https://github.com/juanma6245/search-academy-project) by [Juan Manuel Manga](https://github.com/juanma6245) 
- #### [IMDb Project](https://github.com/Warkos99/EmpathyAcademy) by [Marcos Arce](https://github.com/Warkos99)  
- #### [IMDb Project](https://github.com/ChristianGm25/academy_search) by [Christian González](https://github.com/ChristianGm25) 
- #### [IMDb Project](https://github.com/noeliaigc/IMDb-project) by [Noelia Iglesias](https://github.com/noeliaigc) 
- #### [IMDb Project](https://github.com/taniabg23/search-academy-project/tree/imdb) by [Tania Bajo](https://github.com/taniabg23)
- #### [IMDb Project](https://github.com/gdeleiva/search-academy-project) by [Guillermo de Leiva](https://github.com/gdeleiva) 
- #### [IMDb Project](https://github.com/josperrod9/IMDb-project) by [José Pérez](https://github.com/josperrod9) 
- #### [IMDb Project](https://github.com/Laisgs/search-academy-project/tree/actualMain) by [Laís García](https://github.com/Laisgs) 
- #### [IMDb Project](https://github.com/laura-pb/search-academy-project/tree/main) by [Laura Pernía](https://github.com/laura-pb) 
- #### [IMDb Project](https://github.com/Raul-Alv/search-academy-project/tree/imdb) by [Raúl Álvarez](https://github.com/Raul-Alv) 


----------------------------------------------------------------
## Week 10

### Academy projects start

24/04/2023 - 28/04/2023


During this week the Academy fellows are organizing all the issues anda structure of the project to start developing the prototypes of each project.


#### Retail Trust Index

| **Backends fellows** |
| ------------------ |
| [Laura Pernía](https://github.com/laura-pb)  |
| [Guillermo de Leiva](https://github.com/gdeleiva)  |
| [Laís García](https://github.com/Laisgs)  |
| [Christian González](https://github.com/ChristianGm25)  |

**Goal**
This project is a Trust score for UK brands and has the goal is to design and implement a Trust Score that fulfil [Amplify’s requirements](https://empathy.co/announcement/empathy-co-launches-new-retail-trust-index/).

#### My Motive Search

| **Backends fellows** |
| ------------------ |
| [Juan Manuel Manga](https://github.com/juanma6245)  |
| [José Pérez](https://github.com/josperrod9)  |
| [Noelia Iglesias](https://github.com/noeliaigc)  |
| [Raúl Álvarez](https://github.com/Raul-Alv)  |
| [Tania Bajo](https://github.com/taniabg23)  |

**Goal**
This project is Web app that allows the user to explore the whole Motive catalogue and has the goal is to explore a search experience that allows the user to navigate through the whole catalogue of Motive’s clients.
<br>
<br>
<img align="center" alt="Motive Video" src="./media/my-motive-search.png" width="150"/>
<img align="center" alt="Motive Video" src="./media/my-motive-search-1.png" width="530"/>
<img align="center" alt="Motive Video" src="./media/my-motive-search-2.png" width="150"/>


----------------------------------------------------------------
## Week 11

### Academy projects scrum first steps

01/05/2023 - 05/05/2023

The Academy Fellows are working in documentation about the proyects, setting up repos and having some meetings to make everything clear.

#### Retail Trust Index

Repo: https://github.com/empathyco/retail-trust-index-back
Docs: https://searchbroker.atlassian.net/wiki/spaces/OI/pages/4159439689/Retail+Trust+Index

#### My Motive Search

Repo: https://github.com/empathyco/my-motive-search
Docs: https://searchbroker.atlassian.net/wiki/spaces/AC/pages/4189978968/My+Motive+Search+Academy+Documentation


----------------------------------------------------------------
## Week 12

### Academy projects scrum first steps

08/05/2023 - 12/05/2023

Academy fellows are progessing in their various second phase projects, refining the Jira Boards, the scopes and start developing some functionalities.

#### Retail Trust Index

Repo: https://github.com/empathyco/retail-trust-index-back
Docs: https://searchbroker.atlassian.net/wiki/spaces/OI/pages/4159439689/Retail+Trust+Index

#### My Motive Search

Repo: https://github.com/empathyco/my-motive-search
Docs: https://searchbroker.atlassian.net/wiki/spaces/AC/pages/4189978968/My+Motive+Search+Academy+Documentation
