# 1. Background
-------------------------------------------------------------
## 1.1 Assignment brief

This project aims to desing a secure application that helps ESA astronnauts on the International Space station to record sensitive research information inline with OWASP'S main security threats (OWASP, 2021) as outlined in our Design document (Ashmore et al, 2022).


--------------------------------------------------------------

## 1.2 Architecture
The ISS Logbook application is built as a web microservice using Flask 2.2.2.

-----------

## 1.3 Threats
------------------------------------------------------------

## 2 Passwords: hashing and salting


--------------------------------------------------------------

## 3 Logbook Username, Password, notes database

-------------------------------------------------------------

## 4 Dependenices

-----------------------------------------------------------

## 5 Authentication Module
------------------------------------------------------------

## 5.1 Registration

## 5.2 Login

## 5.3 Notes

---------------------------------------------------------------
## 6 Security Functions

## 6.1 Password Validation

Password validation should have many paramaters which included complexity, length, history, expiration date, and hashing to ensure account security (Simplilearn.com, 2021). A user creating a password must adhere to the these parameters or the account cannot be created. Below are examples taken from the Logbook app. 

1.`if user:
            flash('Email already exists.', category='error')`
            ![email exists](https://github.com/JonnyAsh/ISS-Logbook/blob/550988653b81f0a46e6179dba6b39aec2387a02c/ISS%20Secure%20Logbook/website/images/email%20exists.png)<br> <br/>  
            
            
2.`elif len(email) < 10:
            flash('Email must be greater than 10 characters.', category='error')`
![email len](https://github.com/JonnyAsh/ISS-Logbook/blob/08d313228517d24fa5b1583276a711bc40114f4e/ISS%20Secure%20Logbook/website/images/EMAIL%20LEN.png)<br> <br/>

3. `elif len(first_name) < 3:
            flash('First name must be greater than 1 character.', category='error')`
            ![name greater than 1](https://github.com/JonnyAsh/ISS-Logbook/blob/64bc7000f4fa5faa6763f6b2cbdfa9a37a03cc1d/ISS%20Secure%20Logbook/website/images/first%20name.png)<br><br/>
4. `elif password1 != password2:
            flash('Passwords don\'t match.', category='error')`
            ![password dont math](https://github.com/JonnyAsh/ISS-Logbook/blob/15574e69f50f1906ed73e193a8b7e594f398354f/ISS%20Secure%20Logbook/website/images/password%20dont%20match.png)<br><br/>
5. `elif not any(char.isdigit() for char in password1 and password2):
            flash('Password1 should have at least one numeral', category='error')`
           ![roman numeral](https://github.com/JonnyAsh/ISS-Logbook/blob/309eb8cf232a06acfed62d8ab5ff9bd630be2216/ISS%20Secure%20Logbook/website/images/one%20roman%20number.png)<br><br/>
            
6. `elif not any(char.isupper() for char in password1 and password2):
            flash ('Password should have at least one uppercase letter', category='error')'`
            ![email len]
7. `elif not any(char.islower() for char in password1 and password2):
            flash('Password should have at least one lowercase letter', category='error')`
            ![email len]
8. `elif not any(char in SpecialSym for char in password1 and password2):
            flash('Password should have at least one of the symbols $@#', category='error')`
            v
9. `elif len(password1) < 8:
            flash('Password must be at least 8 characters.', category='error')`
            ![email len]



https://github.com/JonnyAsh/ISS-Logbook/blob/64bc7000f4fa5faa6763f6b2cbdfa9a37a03cc1d/ISS%20Secure%20Logbook/website/images/first%20name.png


## 6.2 Multifactor Authentication

## 6.3 Captcha

-------------------------------------------------------------

## 7 Linters

## 7.1 Flake8

## 7.2 Pylint

## 7.3 McCabe (Cyclomatic Compplexity)

-------------------------------------------------------------

## 8 Testing

------------------------------------------------------------

## 9 References

Ashmore, J. Adelajun, A. Tolofari, S. (2022) 'Development Team Project: Design Document'. Paper submitted to the university of the University of Essex Online for Secure Software Development Module.
Simplilearn.com. (2021) Understanding Why is the Password Validation Process Important in JavaScript | Simplilearn. Available from: https://www.simplilearn.com/tutorials/javascript-tutorial/password-validation#:~:text=Whenever%20a%20user%20creates%20a%20password%2C%20one%20extra [Accessed 5 Sep. 2022].

TechwithTim (2020) GitHub - techwithtim/Flask-Web-App-Tutorial: Code for the note storing flask web app made during a YouTube video. GitHub. Available from: https://github.com/techwithtim/Flask-Web-App-Tutorial [Accessed 9 Aug. 2022].

OWASP (2021) OWASP Top 10:2021. owasp.org. Available from: https://owasp.org/Top10/ [Accessed 3 Sept. 2022].
‌
‌



