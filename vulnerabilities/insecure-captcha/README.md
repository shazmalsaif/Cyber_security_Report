
🤖 Insecure CAPTCHA – Low Security Level

### 🛠️ Objective:
Bypass CAPTCHA validation to change the user's password without solving the challenge.

---

### 🧭 Walkthrough

1. Navigate to the Insecure CAPTCHA page.
2. Enter a new password, leave the CAPTCHA field blank, and submit.
   - ❌ You’ll receive an error due to missing CAPTCHA.

---

### 🔍 Burp Suite Exploit

1. Enable **FoxyProxy** and **Burp Suite Intercept**.
2. Fill in any values for the password fields and click submit.
3. In the intercepted request, locate the parameter:
```

step=1

```

4. Modify it to:
```

step=2

```

5. Forward the request.

✅ The password is changed successfully — CAPTCHA has been bypassed.

---

### 🧩 Summary

- ❌ CAPTCHA not validated on the backend
- ✅ Step manipulation bypasses the flow

## ✅ Status
- ✅ Fully exploitable
- 🟢 Beginner-friendly
