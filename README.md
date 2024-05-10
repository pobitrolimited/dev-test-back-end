# Developer evaluation Test
The purpose of this test is to get to know more about technical capabilities of the candidate. 

## Things we will be observing
- **We expect you to complete all three tasks but we HIGHLY encourage you to submit the tasks(not all) that you have completed or partially completed tasks.**
- **You have done it on your own. No one should help you on this. We value partially completed task more than completed task if you have done without any help compare to completed with help.**
- Code readability, add comments in the code so that others can understand.
- Code optimization, minimize duplicate code.

## Tasks 1: Develop an API server
The task is to develop two APIs for user registration and login. 

**Language/Framework**: You may use NodeJs/Java/Python, but we encourage you to do it in NodeJs.

### Registration API:
Here are the details for registration api:
- API endpoint should be `/api/v1/registration`
- API endpoint should accept only HTTP POST requests
- API endpoint should accept request payload in `JSON` format
- Registration api payload will be: 
```json 
{
  "name": "Name of the Candidate",
  "email": "Email address of the Candidate",
  "phone": "Phone number of the Candidate",
  "password": "A Password with at least 1 upper case letter, 1 lower case letter, 1 number and 1 special character"
}
```
- API should do minimal validation on payload: all the properties are required and has to be in the payload. If you can/possible then do email and password validation.
- The API should write the registration data in a json file. Create a json file `user.json` and keep appending registration data.
- Each new  registration should be added in new line, and one line for each registration. Here is how it should look like:
```json
{"name":"Candidate1","email":"Candidate1@email.com","phone":"0171xxxxxxx","password":"c@nd!dAte1"}
{"name":"Candidate2","email":"Candidate2@email.com","phone":"0171xxxxxxx","password":"c@nd!dAte2"}
{"name":"Candidate3","email":"Candidate3@email.com","phone":"0171xxxxxxx","password":"c@nd!dAte3"}
```
- The api should return HTTP status code `201` if all the properties are present in the payload. If all the properties are not in the payload then return HTTP status code `400`.
- Add comments in the code.
- (Optional) Store the password as Hash. You can use bcrypt([NodeJs Package](https://www.npmjs.com/package/bcrypt),[Python Package](https://pypi.org/project/bcrypt/)) to generate the hash.


### Sign In API
Here are the details for Sign In api:
- API endpoint should be `/api/v1/signin`
- API endpoint should accept only HTTP POST requests
- API endpoint should accept request payload in `JSON` format
- Sign In api payload will be: 
```json
{
  "email": "Candidate Email",
  "password": "Candidate's Password"
}
```
- The API should check the required properties(email and password) in the payload. Return HTTP status `400` if any required properties are missing.
- The API should return HTTP status `200` if the user is found in `users.json` file. If user is not found then return HTTP status `401`. 
- Add comments in the code.

## Task 2: Design a database for an organization
In this task you have to design a database for an organization's employee information management. You may design for relational database or NoSQL.  


You may submit the database schema using simple diagrams or ER diagram. **If you are unable to draw the design using a tool, you can draw it in a paper and take a picture and submit.** 

***We encourage you to submit partial design if you can't complete it.**

Here is the details of the organization:

A organization has multiple departments. There may be sub-departments under a department. Each employee works/reports in sub-department/department(if there are no sub-department). 
Departments and sub-department are in different cities. 

Each employee has the following information:
- Name
- NID - May have multiple NIDs
- Phone Number - May have multiple Phone numbers. If there are multiple phone numbers then there will be one primary phone number.
- Home District
- Education details - SSC, HSC, Honours degree/Bachelor Degre, Masters Degree. Each degree should have : Educational institution name, passing year, grade/marks.
- Current Designation
- Current Department
- Current Sub Department
- Joining Date in the Organization
- Joining Date in the Current Designation
- Termination Date
- Trainings - Employees may have completed 0 or more trainings. 
- Leaves - Number of days an employee has taken leaves. 
- Login info - email/phone number and password 

More details:
* Trainings are different types. Each training has start date, end date, location, description. Multiple employee from different department/location 
* Employees leave/vacation needs to be tracked. Employees request for leave for 1 or more days. Any leave request are approved/declined by by Employees superior(the person he/she reports to).
* Employees may move/shifted/promoted to other departments.
* Each Employee has to login on entering the office building and log out when exiting. An Employee may leave and come back the office multiple time in a day.

There are services/applications which does the following queries:
- How many leaves an employee has taken this year, last year?
- Hom many employees in a department ?
- Find if an employee was in office or not at 11am.
- How many trainings an employee has completed so far and this year?
- List the employees(name only) who has taken a specific training.
- What are the departments an employee worked on so far?
- List the employees(name only) from a District
- How many hours/minutes an employee was in the office on a specific day?
- List the employees(name only) who are graduated from a specific educational institution.
- List the employees(name only) who has taken more than 15 days of leave this year.

**Note that you should store information such a way that it will be optimized/fast read from database when any of the above questions are asked.**

## Task 3: Programming Challenge
We prefer you to code in JavaScript/NodeJs/TypeScript/Python/Java. But you may use any programming language if you want.

***We encourage you to submit partial solutions if you can't complete it.** 

**How to submit the code?**
- Add comments/details around important logic in your code
- Add notes/instructions in the code about how to run it
- Save the code in a `.txt` file and send it to us for submission.


**Problem 1** \
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target. \
You may assume that each input would have exactly one solution, and you may not use the same element twice. \
You can return the answer in any order. 

Example 1:
```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```

Example 2:
```
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

Example 3:
```
Input: nums = [3,3], target = 6
Output: [0,1]
```

**Problem 2** \
Given a string `s` containing just the characters `(`, `)`, `{`, `}`, `[` and `]`, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.
3. Every close bracket has a corresponding open bracket of the same type.

**Example 1:**
```
Input: s = "()"
Output: true
```

**Example 2:**
```
Input: s = "()[]{}"
Output: true
```

**Example 3:**
```
Input: s = "(]"
Output: false
```

### How To Submit Your Code
- Create a directory/folder in your computer. Name the folder with your name. If your name is `Ab. Cde Fghi`, the folder name will be `ab_cde_fghi`.
- Create separate directory for each task, like for task1, `ab_cde_fghi/task1` and for task2 `ab_cde_fghi/task2`
- Zip the entire ab_cde_fghi folder without any dependency packages/libraries.
- Lastly, email zipped directory to `info@etlimited.net`  with Subject `Submission - Back-end Dev - <YOUR_NAME>`.


For any other difficulty contact us at `info@etlimited.net`.