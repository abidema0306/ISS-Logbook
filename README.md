# 1. Background
-------------------------------------------------------------
## 1.1 Assignment brief

This project aims to desing a secure application that helps ESA astronnauts on the International Space station to record sensitive research information inline with OWASP'S main security threats (OWASP, 2021) as outlined in our Design document (Ashmore et al, 2022).


--------------------------------------------------------------

## 1.2 Architecture
The ISS Logbook application is built as a web microservice using Flask 2.2.2.

-----------

## 1.3 Threats

In the design document, a few threats were identified applicable to the logbook. These threats included taking over an existing user’s account and upgrading a lesser privileged account to one with more privileges.
For this reason, a program was written in Python (Downey, 2012), which enforces strong password practices, applies cryptographic hashing functions to protect this privileged data, locks the user accounts after too many incorrect login attempts, and separates user data from the more privileged staff data. The password must contain special characters, numbers and upper-case letters. The code will also require users to confirm their password to help them catch any typos. Passwords which meet all the requirements will then be hashed using the SHA-256 cryptographic hashing method and stored in the csv file together with the user’s email address, registration date and the number of login attempts (set to 3 by default for new users). To log in to the logbook, the users will have to enter their email address and password. The entered password will be hashed and compared to the one in the database. If the passwords match, the user will be allowed to login.



------------------------------------------------------------

# 2 Passwords: hashing and salting
        
The program enforces the following password restrictions:             
The password length must be between 8 and 64 characters. The 256-bit hashing function the program uses allows up to 64 hexadecimal characters (Khan, 2021)
The password must contain special characters, numbers and upper-case letters.
The password must contain at least one whitespace. Passwords with white spaces tend to be more secure (InfosecMatter, 2021).


--------------------------------------------------------------

# 3 Logbook Username, Password, Notes database

-------------------------------------------------------------

# 4 Dependencies

-----------------------------------------------------------

# 5 Authentication Module
------------------------------------------------------------

## 5.1 Registration

## 5.2 Login

## 5.3 Notes

---------------------------------------------------------------
# 6 Security Functions

## 6.1 Password Validation

Password validation should have many paramaters which included complexity, length, history, expiration date, and hashing to ensure account security (Simplilearn.com, 2021). A user creating a password must adhere to the these parameters or the account cannot be created. Below are examples taken from the Logbook app. 

1.`if user:
            flash('Email already exists.', category='error')`
            ![email exists](https://github.com/JonnyAsh/ISS-Logbook/blob/cad72aaad684b9f4fa6cbe8a218c557a0ff28a11/ISS%20Secure%20Logbook/website/images/email%20exists%20already.png)<br><br/>  
            
            
2.`elif len(email) < 10:
            flash('Email must be greater than 10 characters.', category='error')`
![email len](https://github.com/JonnyAsh/ISS-Logbook/blob/7b7553cdd6981c21fb849315b82e619ae368fd8b/ISS%20Secure%20Logbook/website/images/email%20length.png)<br> <br/>

3. `elif len(first_name) < 3:
            flash('First name must be greater than 1 character.', category='error')`
            ![name greater than 1](https://github.com/JonnyAsh/ISS-Logbook/blob/ab61e5a1cbed5773442007ffb9b2709811e60ef2/ISS%20Secure%20Logbook/website/images/first%20name%20len.png)<br><br/>
4. `elif password1 != password2:
            flash('Passwords don\'t match.', category='error')`
            ![password dont math](https://github.com/JonnyAsh/ISS-Logbook/blob/afeeb2392abe52e3dbee8535c33efaa2dcef9885/ISS%20Secure%20Logbook/website/images/not%20match%20password.png)<br><br/>
5. `elif not any(char.isdigit() for char in password1 and password2):
            flash('Password1 should have at least one numeral', category='error')`
           ![roman numeral](https://github.com/JonnyAsh/ISS-Logbook/blob/1018849cb847f14312ca84e071449e6edab1cc1d/ISS%20Secure%20Logbook/website/images/one%20roman%20numeral.png)<br><br/>
            
6. `elif not any(char.isupper() for char in password1 and password2):
            flash ('Password should have at least one uppercase letter', category='error')'`
            ![upper](https://github.com/JonnyAsh/ISS-Logbook/blob/8d8116b70ab20a24a392a58528370470f5e03fd4/ISS%20Secure%20Logbook/website/images/uppercase.png)<br><br/>
7. `elif not any(char.islower() for char in password1 and password2):
            flash('Password should have at least one lowercase letter', category='error')`
            ![lower](https://github.com/JonnyAsh/ISS-Logbook/blob/8d8116b70ab20a24a392a58528370470f5e03fd4/ISS%20Secure%20Logbook/website/images/lowercase.png)<br><br/>
8. `elif not any(char in SpecialSym for char in password1 and password2):
            flash('Password should have at least one of the symbols $@#', category='error')`
            ![symbol](https://github.com/JonnyAsh/ISS-Logbook/blob/a8e696ae2ca9295b103387f4c6265b1bade1c87c/ISS%20Secure%20Logbook/website/images/symbol.png)<br><br/>
            


## 6.2 Multifactor Authentication

## 6.3 Captcha

-------------------------------------------------------------

# 7 Linters

## 7.1 Flake8

## 7.2 Pylint

## 7.3 McCabe (Cyclomatic Complexity)
This tool measures the number of decisions such as 'if' conditionals in the source code; for example, the lower count, the less complex it is.
Any result between 1 and 10 is considered manageable and clean code (Qac, 2022).


## 7.4 Bandit

-------------------------------------------------------------

# 8 Testing

------------------------------------------------------------
# 9 Limitations
 
 ----------------------------------------------------------------

# 10 References

Ashmore, J. Adelakun, A. Tolofari, S. (2022) 'Development Team Project: Design Document'. Paper submitted to the university of the University of Essex Online for Secure Software Development Module.

Simplilearn.com. (2021) Understanding Why is the Password Validation Process Important in JavaScript | Simplilearn. Available from: https://www.simplilearn.com/tutorials/javascript-tutorial/password-validation#:~:text=Whenever%20a%20user%20creates%20a%20password%2C%20one%20extra [Accessed 5 Sep. 2022].

TechwithTim (2020) GitHub - techwithtim/Flask-Web-App-Tutorial: Code for the note storing flask web app made during a YouTube video. GitHub. Available from: https://github.com/techwithtim/Flask-Web-App-Tutorial [Accessed 9 Aug. 2022].

Qac, H. (2022) Cyclomatic Complexity Explained | Perforce. Available from: https://www.perforce.com/video-tutorials/qac/cyclomatic-complexity-explained#:~:text=Code%20with%20a%20cyclomatic%20complexity%20between%201%20and [Accessed 12 Sep. 2022].
‌

OWASP (2021) OWASP Top 10:2021. owasp.org. Available from: https://owasp.org/Top10/ [Accessed 3 Sept. 2022].

Downey, A.B. (2012) Python for software design how to think like a computer scientist. Cambridge: Cambridge University Press.   (Samuel entry)

Khan, M.W. (2021) Pool Map With Multiple Arguments in Python. Delft Stack. Available from: https://www.delftstack.com/howto/python/python-pool-map-multiple-arguments/ [Accessed 9 Sep. 2022].   (Samuel entry)
‌
‌
‌
‌



