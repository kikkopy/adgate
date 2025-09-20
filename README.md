# AdGate

Robust anti-adblock solution for modern websites. Lightweight, undetectable, and effective.

[![npm version](https://img.shields.io/npm/v/adgate.svg?style=flat-square)](https://www.npmjs.com/package/adgate)
[![npm downloads](https://img.shields.io/npm/dm/adgate.svg?style=flat-square)](https://www.npmjs.com/package/adgate)
![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Size](https://img.shields.io/badge/minified-6KB-green.svg)
![JavaScript](https://img.shields.io/badge/javascript-ES6+-yellow.svg)

---

## 🚀 Installation

**CDN (unpkg)**

```html
<script src="https://unpkg.com/adgate/js/lib.js"></script>
```

**npm**

```bash
npm install adgate
```

Import in your project:

```js
import "adgate/js/lib.js";
```

---

## 🔍 Why AdGate?

Most anti-adblock solutions are easily bypassed or detected.
AdGate uses **14 detection methods** with randomized timing and self-protection to ensure your content stays protected.

---

## ⚡ Quick Setup

Add one line to your website:

```html
<script src="https://unpkg.com/adgate/js/lib.js"></script>
```

That's it! AdGate will automatically detect adblockers and block navigation.

---

## 🛠 Detection Methods

**Basic Detection**

* Hidden element tests
* Network request monitoring
* CSS property analysis
* Script loading failures

**Advanced Detection**

* DOM mutation observation
* Browser extension scanning
* Performance timing analysis
* Error event capturing

**Stealth Methods**

* Canvas fingerprint testing
* Web worker blocking
* Property getter traps
* CSS injection tests
* XHR request monitoring
* Fetch API hooking

---

## 🌍 Browser Support

✅ Chrome
✅ Firefox
✅ Safari
✅ Edge
✅ Mobile browsers

---

## 📦 Integration Examples

**Basic HTML**

```html
<script src="https://unpkg.com/adgate/js/lib.js"></script>
```

**WordPress**

```php
function add_adgate() {
    wp_enqueue_script('adgate', 'https://unpkg.com/adgate/js/lib.js', array(), '1.0.1', true);
}
add_action('wp_enqueue_scripts', 'add_adgate');
```

**React/Next.js**

```jsx
useEffect(() => {
  const script = document.createElement("script");
  script.src = "https://unpkg.com/adgate/js/lib.js";
  document.body.appendChild(script);
}, []);
```

---

## 🎨 Customization

The popup uses inline styles for compatibility but can be customized by modifying the source code (`s()` function).

**Custom styling**

```js
background: '#000000';
border: '2px solid #262626';
color: 'white';
```

**Custom messages**

```js
innerHTML = `
  <h2>Custom Title</h2>
  <p>Your message here</p>
`;
```

---

## 📊 Analytics Integration

Track adblock usage with your analytics:

```js
gtag('event', 'adblock_detected', {
  'event_category': 'AdGate',
  'value': 1
});
```

---

## 🐞 Troubleshooting

**Not working?**

* Check console for errors
* Verify script loads after DOM
* Test in incognito mode
* Check CSP rules

**False positives?**

* Lower detection sensitivity in source
* Add loading delays
* Test across browsers

---

## 🤝 Contributing

PRs welcome! Please test thoroughly before submitting.

---

## 📜 License

MIT License. Free for personal and commercial use.

---

**Created by [kikkopy](https://github.com/kikkopy)**
