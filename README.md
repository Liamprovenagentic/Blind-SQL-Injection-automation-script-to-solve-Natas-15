# Blind-SQL-Injection-automation-script-to-solve-Natas-15
A blind SQL injection script designed to reveal the password to Natas 16.

Natas15 (OverTheWire) is a blind boolean SQLi challenge — the login form only ever shows "This user exists!" or nothing, no error text, no password reflected back. You exploit that yes/no oracle to extract the password char by char using SUBSTRING/ASCII in the injected username field.

Core idea:

username = natas16" AND SUBSTRING(password,1,1)="a

If the page shows "This user exists!", your guess for character 1 is right. Iterate over every char position and every candidate char (or binary-search via ASCII(SUBSTRING(...)) > / < comparisons, much faster).
