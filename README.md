# Natas15 Blind SQL Injection Solver

Python script that solves OverTheWire Natas15 by exploiting a blind boolean
SQL injection in the login form to extract natas16's password character by character.

## How it works
Natas15's login only returns "This user exists!" or nothing — no errors,
no password reflected. This script abuses that true/false oracle with
`SUBSTRING(password, pos, 1) = 'x'` payloads injected via the username field,
brute-forcing (or binary-searching) each character.

## Usage
pip install requests
python solve.py --user natas15 --pass <natas15_password>

## Example output
...
Recovered password: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
