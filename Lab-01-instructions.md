# WIIT-7340 Lab One
## Degrees Restaurant at Columbus State API v1.0

In this lab, we develop version 1.0 of the Degrees Restaurant at Columbus State 
website Application Programming Interface (API) 

__Estimated time to complete:__ 4 hours\
__Points possible:__ 50\
__Passing score:__ 40

## Before we begin

You will use the repository you create in the first step for *all* REST API labs. It is important __each lab has its own branch__ and, when compared to the master branch, __the changes in each branch are only for that lab__. 

Your work should be :

1. Lab One:
    1. Commit steps 1-5 on the master branch
    1. From *master* create a new "lab-one" branch
    1. Complete the remainder of Lab one on a "lab-one" branch
    1. Push your lab one branch to GitHub, create a pull request, and request my review
    1. *After I approve your pull request in GitHub*:
        1. Submit your work in Blackboard
        1. Merge your pull request changes from the lab one branch to the master branch
1. Lab Two:
    1. From *master* create a new "lab-two" branch
    1. Complete the assignment making all changes on the lab two branch
    1. Push your lab two branch to GitHub, create a pull request, and request my review
    1. *After I approve your pull request in GitHub*:
        1. Submit your work in Blackboard
        1. Merge your pull request changes from the lab one branch to the master branch

Repeat the Lab Two process for the remaining labs. Doing it this way make it easier to grade your work and provide comments in the code on GitHub. 

__*Failure to follow this process may result in a lower score.*__

### 1. Create a new private repository for your work

- [ ] [Create a new GitHub repository](https://help.github.com/en/github/getting-started-with-github/create-a-repo) making sure it's marked __private__
- [ ] Add me, __jeff-anderson-cscc__, as a [collaborator on your new repo](https://help.github.com/en/github/setting-up-and-managing-your-github-user-account/inviting-collaborators-to-a-personal-repository)

### 2. Create a new Spring Boot project

- [ ] Use [Spring Initializr](https://start.spring.io/) to create a new Spring Boot project with the following settings:

    * Group: `edu.cscc`
    * Artifact: `degrees`
    * Dependencies: 
        * `Spring Web`
        * `Spring JPA`
        * `H2 Database`

- [ ] Click __Generate__ to create the project zip file
- [ ] Unzip the project into a development directory of your choosing

### 3. Open the project in IntelliJ

- [ ] Start IntelliJ closing any projects that come up
- [ ] From the Welcome screen, choose __Open__ and navigate to the location of your newly unzipped project from step 2
- [ ] If you get a message about Maven projects needing to imported, choose to enable auto-import

__NOTE:__ It may take a few minutes for IntelliJ to import the project and download all dependencies

### 4. Make sure the application runs

- [ ] From the project pane, expand __src > test > java > edu.cscc.degrees__
- [ ] Right-click on `DegreesApplicationTests` and choose __Run 'DegreesApplicationTests'__ 

__IMPORTANT:__ Make sure the unit test runs successfully before continuing.

### 5. Commit your changes into GitHub

#### Create a local Git repository:

- [ ] From the IntelliJ menu, choose __VCS > Import into Version Control > Create Git Repository__.
- [ ] Choose the automatically selected default of your project's top directory for your local repo.

#### Check-in your initial commit:

- [ ] Add a line with `.mvn` at the bottom of your `.gitignore` file.
- [ ] Choose __VCS > Commit__.
- [ ] Check the box to the left of "Unversioned Files."
- [ ] Enter "Initial commit" into the "Commit Message" box
- [ ] Press "Commit"

#### Push your project to GitHub:

- [ ] Open a terminal window and navigate to your top-level project directory
- [ ] From the __Code__ tab of the GitHub repo you created in step 1, copy and paste the "…or push an existing repository from the command line" commands shown into the terminal window
- [ ] After the push completes, refresh the browser page on your repo and verify the __Code__ tab now shows the code from your project

### 6. Complete the assignment

Your assignment is to fully implement API spec [version 1.0.0, as shown on SwaggerHub](https://app.swaggerhub.com/apis/DataDaddy/wiit-7340_degrees_at_cscc_api/1.0.0).

__Notes:__
* You must write unit tests using mocks and stubs for your REST API controller as described in chapter 7, _Testing with mocks_, of the [Spring Web Essentials](https://leanpub.com/springwebessentials) textbook.
* Don't worry about validation (Chapter 8 from the book). We will add that to the next lab.
* Create a `MenuCategory` domain entity class as described in chapter 6, _Adding a database_ with the following properties:
    ```java
      private long id;
      private String categoryTitle;
      private String categoryNotes;
      private int sortOrder;
    ```
* Create a `MenuCategoryRepository` Spring JPA repository as described in chapter 6, _Adding a database_.

__Tasks:__

- [ ] __IMPORTANT:__ Create a new branch for your work __VCS > Git > Branches__ then __+New Branch__ using a meaningful name like `api-spec-1-0` or `week-1-homework`.
- [ ] Create one or more unit tests for each path and method in [version 1.0.0 of the API spec](https://app.swaggerhub.com/apis/DataDaddy/wiit-7340_degrees_at_cscc_api/1.0.0) which checks:
  - [ ] POST accepts a new item and returns 201 created, a response body with the saved item, and the location of the newly created item in the headers
  - [ ] One or more tests for GET returns a list of items (returns an empty list, a list with one item, etc.)
  - [ ] GET with valid ID returns expected data 
  - [ ] GET with an invalid ID returns 404 not found 
  - [ ] PUT with a valid ID and request body returns 204 no content    
  - [ ] PUT with an invalid ID returns 404 not found    
  - [ ] DELETE with valid ID returns 204 no content 
  - [ ] DELETE with an invalid ID returns 404 not found 
 
 * Where applicable, your unit tests check: 
     * The status code returned
     * The content type of the response
     * Element(s) and attribute(s) in the reply match those returned by the mock repository
     * Header values are correct
     * Repository methods are called (or not called) the expected number of times

- [ ] Create a REST API controller with the methods necessary to get each test to pass

__TIP:__ Write one unit test at a time adding just enough controller code to make it pass. If you try to do too much at once, it's easy to be overwhelmed with issues. 

__Scoring:__

Maximum score:
* Your controller has 100% code coverage.
* You have at least one unit test for each path, method, response status code combination.
* Your code correctly and fully implements the spec
* Where applicable, your unit tests check: 
    * The status code returned
    * The content type of the response
    * Element(s) and attribute(s) in the reply match those returned by the mock repository
    * Header values are correct
    * Repository methods are called (or not called) the expected number of times
* Your code follows all applicable patterns and practices from [Clean Code: A Handbook of Agile Software Craftsmanship](https://learning.oreilly.com/library/view/clean-code/9780136083238/)
* Your code is well organized with the minimum necessary to complete the lab.

### 7. Create a pull request adding me as a reviewer

After completing all the tasks above:

- [ ] Commit your changes to the branch created in step 6.
- [ ] Push your branch to GitHub.
- [ ] [Create a pull request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request) for your new branch.
- [ ] [Request a review ](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/requesting-a-pull-request-review) from me.

__STOP HERE UNTIL THE PULL REQUEST IS APPROVED__

I will provide feedback on GitHub. _If you completed your assignment on time_, I will give you up to one additional week to incorporate my feedback and improve your score. 

### 8. Submit the assignment in Blackboard

__WAIT UNTIL I APPROVE THE PULL REQUEST before continuing!__

- [ ] Follow the procedures outlined in [Once your pull request is reviewed and approved](https://github.com/jeff-anderson-cscc/wiit-7340-lab0-completing-and-submitting-assignments#once-your-pull-request-is-reviewed-and-approved) from the [Completing and Submitting Coding Assignments Lab](https://github.com/jeff-anderson-cscc/wiit-7340-lab0-completing-and-submitting-assignments#completing-and-submitting-coding-assignments-lab)