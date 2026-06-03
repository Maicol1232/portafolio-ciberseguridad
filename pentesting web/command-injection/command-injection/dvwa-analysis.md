# Command Injection Analysis (DVWA)

## Objective

Analyze how the command injection vulnerability changes across different security levels.

---

## Low Level

### Behavior

The application takes user input and directly executes it in the system shell.

### Security

No input validation or filtering is applied.

### Impact

An attacker can execute arbitrary system commands.

### Example

Input:
127.0.0.1 | whoami

---

## Medium Level

### Behavior

The application filters some characters using a blacklist.

### Security

Basic filtering is applied, but it is incomplete.

### Weakness

Blacklists can be bypassed using alternative operators or payload variations.

### Impact

Command injection is still possible.

---

## High Level

### Behavior

The application applies stricter validation to user input.

### Security

More secure filtering and sanitization functions are used.

### Weakness

If validation is not properly implemented, it can still be bypassed.

### Impact

The risk is reduced, but not completely eliminated.

---

## Conclusion

Security mechanisms based only on blacklists are not sufficient.

The root problem is the direct execution of user input in the system shell.

---

## Key Takeaways

* Input validation must be strict and secure
* Blacklist filtering is not reliable
* Understanding backend behavior is essential
