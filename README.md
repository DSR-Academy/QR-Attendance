Project Details


	•	Password stored in Google Sheets
	•	Login validated against the Sheet (works across all devices)
	•	Duplicate check on registration
	•	Attendance recorded on every login

Google Sheets Setup:

Tables: Timestamp | First Name | Last Name | Email | Transaction ID | Password | Type

"Type” will be “Registered” or “Login” for clarity.


This system finally will:
	•	Prevents duplicate accounts
	•	Supports login from any device
	•	Stores password in Google Sheets (plaintext — good for internal systems)
	•	Logs every attendance on login


Summary Sheet details

Name           -> Cell A1:  =UNIQUE(FILTER(Log!D2:D, Log!G2:G="Login"))
Login Count.   -> Cell B1: =ArrayFormula(IF(A2:A="", "", COUNTIFS(Log!D:D, A2:A, Log!G:G, "Login")))
First Name     -> Cell C1: =ArrayFormula(IF(A2:A="", "", INDEX(Log!B:B, MATCH(A2:A, Log!D:D, 0))))
Last Name      -> Cell D1: =ArrayFormula(IF(A2:A="", "", INDEX(Log!C:C, MATCH(A2:A, Log!D:D, 0))))
Transaction Id ->Cell E1: =ArrayFormula(IF(A2:A="", "", INDEX(Log!E:E, MATCH(A2:A, Log!D:D, 0))))

