# Command Injection Analysis in DVWA

## Objective

Analyze how the command injection vulnerability varies according to the security level in DVWA.

---

## Low Level

* No input validation
* User input is directly concatenated into a system command

Result:
Allows the complete execution of arbitrary commands on the server.

---

## Medium Level

* A blacklist filter is implemented
* Some special characters are blocked

Weakness:
The filter is incomplete and can be bypassed using different operators or variations of the input.

---

## High Level

* Stricter validations are applied
* Use of system sanitization functions

Observation:
Significantly reduces the risk, but does not guarantee complete protection if the validation is not correct.

---

## Injection Example

Input sent:
127.0.0.1 | whoami

Result:
The system executes an additional command due to the shell's interpretation of operators.

---

## Technical Analysis

The vulnerability occurs because the backend directly executes user input in the system shell without proper validation.

This allows operators such as `|`, `;`, `&&`, and `||` to be interpreted as commands.

---

## Conclusion

Security mechanisms based solely on blacklists are insufficient.

The main problem is the direct execution of user-controlled input in the system.

---

## Lessons Learned

* Understanding how the backend works is fundamental.
* Execution logic is more important than payloads.
* Poorly implemented filters can be bypassed.

