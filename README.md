# Developer evaluation Test
The purpose of this test is to get to know more about technical capabilities of the candidate. 


## Back-End Tasks
The task is to develop two APIs for user registration and login. 

**Language/Framework**: You may use NodeJs/Java/Python, but we encourage you to do it in NodeJs.


**Registration API:** \
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


**Sign In API:**\
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

### How To Submit Your Code
- Clone this github project in your local. You may clone the repository from GitHub UI or use this command (`git clone https://github.com/pobitrolimited/dev-test-back-end.git`)
- Create a branch with your name. Command to create branch: `git checkout -b test_candidate1`
- Create a separate directory on the root of the repository, like `dev-test-back-end/candidate1/`. 
- Add all your code in that directory. 
- Commit all the changes. 
  - Command to add your changes `git add ./candidate1/`
  - Command to commit your changes: `git commit -m 'Source code for Candidate 1'`
- Push your branch, Command to push the code:`git push origin test_candidate1`
- Lastly, email `pobitro@etlimited.net` to notify that you have submitter your code.


If you don't know GitHub or have difficulty pushing the code in GitHub then zip the source code(without dependency packages) and email to `pobitro@etlimited.net`.




