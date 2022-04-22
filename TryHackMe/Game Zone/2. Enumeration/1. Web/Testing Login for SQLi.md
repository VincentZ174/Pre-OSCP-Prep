## Testing Login for SQLi

* home page has a login form that we can test for SQLi
![7580567c1bb71e3c8a437767e34fded7.png](../../../../_resources/7580567c1bb71e3c8a437767e34fded7.png)
* if we type `' or 1=1 -- -'` for the username field and leave the password empty we're able to log in
