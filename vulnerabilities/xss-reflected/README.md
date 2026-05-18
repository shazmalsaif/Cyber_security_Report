⚡ Reflected XSS – Low Security Level

### 🛠️ Objective:
Inject JavaScript code that gets immediately reflected in the response and executed in the victim’s browser.

---

### 🧭 Walkthrough

1. Navigate to the Reflected XSS page.
2. In the input box, enter the following payload:
```html
<script>alert('XSS')</script>
````

3. Submit the form.

✅ A popup alert will appear with the message: `XSS`.

---

### 🛑 Why It Works

* The input is directly reflected in the page without any sanitization or encoding.
* No filters are applied on special characters like `<`, `>`, or `"`.

---

### 🧪 Alternative Payloads to Test

```html
<img src=x onerror=alert(Hackable)>
"><script>alert("Hackable")</script>
<svg/onload=alert("Hackable")>
```

---

### 🧩 Summary

* ❌ No input validation or encoding
* ✅ Fully exploitable
* 🟢 Ideal for understanding basic XSS behavior

## ✅ Status

* ✅ Fully exploitable
* 🟢 Beginner-friendly
