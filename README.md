# AdGate

Robust anti-adblock solution for modern websites. Lightweight, undetectable, and effective.

[![npm version](https://img.shields.io/npm/v/adgate.svg?style=flat-square)](https://www.npmjs.com/package/adgate)
[![npm downloads](https://img.shields.io/npm/dm/adgate.svg?style=flat-square)](https://www.npmjs.com/package/adgate)
![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Size](https://img.shields.io/badge/minified-3.8KB-green.svg)
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
AdGate uses **8 advanced detection methods** with async processing, smart timeouts, and self-protection to ensure your content stays protected.

**New in v2.0:**
- ✅ Async/await architecture
- ✅ Promise-based detection
- ✅ Configurable sensitivity
- ✅ Whitelist support
- ✅ Theme customization
- ✅ Bot detection
- ✅ Performance optimized

---

## ⚡ Quick Setup

**Basic Integration**
```html
<script src="https://unpkg.com/adgate/js/lib.js"></script>
```

**Advanced Configuration**
```html
<script>
window.AdGateConfig = {
  sensitivity: 'high',
  theme: 'dark',
  whitelist: ['localhost']
};
</script>
<script src="https://unpkg.com/adgate/js/lib.js"></script>
```

---

## 🛠 Configuration Options

```javascript
window.AdGateConfig = {
  // Detection sensitivity
  sensitivity: 'medium',        // 'low', 'medium', 'high'
  
  // Retry interval in milliseconds
  retryInterval: 30000,         // Default: 30 seconds
  
  // Domains to skip detection
  whitelist: ['localhost', 'dev.example.com'],
  
  // UI theme
  theme: 'dark'                 // 'light' or 'dark'
};
```

### Sensitivity Levels

| Level | Description | Detection Rate | Performance |
|-------|-------------|----------------|-------------|
| `low` | Basic detection only | ~70% | Fastest |
| `medium` | Balanced approach | ~85% | Optimal |
| `high` | All methods enabled | ~95% | Slower |

---

## 🔍 Detection Methods

**Network Tests**
* Ad server connectivity
* Resource loading failures
* Fetch API monitoring

**DOM Analysis**
* Hidden element detection
* CSS property analysis
* Style injection tests

**Performance Tests**
* DOM manipulation timing
* Script execution delays
* Resource loading speed

**Advanced Detection**
* Mutation observer tracking
* Browser extension scanning
* Web worker blocking tests
* Error event monitoring

---

## 🌍 Browser Support

✅ Chrome 60+
✅ Firefox 55+
✅ Safari 12+
✅ Edge 79+
✅ Mobile browsers
✅ IE11 (limited)

---

## 📦 Integration Examples

**Basic HTML**

```html
<!DOCTYPE html>
<html>
<head>
  <title>My Website</title>
</head>
<body>
  <!-- Your content -->
  <script src="https://unpkg.com/adgate/js/lib.js"></script>
</body>
</html>
```

**WordPress**

```php
function add_adgate() {
    wp_enqueue_script('adgate', 'https://unpkg.com/adgate/js/lib.js', array(), '2.0.0', true);
    
    // Add configuration
    wp_add_inline_script('adgate', '
        window.AdGateConfig = {
            sensitivity: "high",
            theme: "dark",
            whitelist: ["' . $_SERVER['HTTP_HOST'] . '/wp-admin"]
        };
    ', 'before');
}
add_action('wp_enqueue_scripts', 'add_adgate');
```

**React/Next.js**

```jsx
import { useEffect } from 'react';

function MyApp() {
  useEffect(() => {
    // Configuration
    window.AdGateConfig = {
      sensitivity: 'medium',
      theme: 'light'
    };
    
    // Load script
    const script = document.createElement("script");
    script.src = "https://unpkg.com/adgate/js/lib.js";
    script.async = true;
    document.body.appendChild(script);
    
    return () => {
      document.body.removeChild(script);
    };
  }, []);

  return <div>Your app content</div>;
}
```

**Vue.js**

```vue
<template>
  <div id="app">
    <!-- Your content -->
  </div>
</template>

<script>
export default {
  mounted() {
    window.AdGateConfig = {
      sensitivity: 'high',
      retryInterval: 25000
    };
    
    const script = document.createElement('script');
    script.src = 'https://unpkg.com/adgate/js/lib.js';
    document.head.appendChild(script);
  }
}
</script>
```

---

## 🎨 Customization

**Theme Options**

```javascript
// Dark theme (default)
window.AdGateConfig = { theme: 'dark' };

// Light theme
window.AdGateConfig = { theme: 'light' };
```

**Whitelist Configuration**

```javascript
window.AdGateConfig = {
  whitelist: [
    'localhost',
    'dev.example.com',
    '192.168.1.100'
  ]
};
```

**Development Mode**

```javascript
// Skip detection in development
window.AdGateConfig = {
  whitelist: ['localhost', '127.0.0.1'],
  sensitivity: 'low'
};
```

---

## 📊 Analytics Integration

**Google Analytics 4**

```javascript
// Add after AdGate script
window.addEventListener('adblock-detected', function() {
  gtag('event', 'adblock_detected', {
    event_category: 'AdGate',
    event_label: 'Blocked Content'
  });
});
```

**Custom Analytics**

```javascript
window.AdGateConfig = {
  onDetect: function(method) {
    // Your analytics code
    analytics.track('Adblock Detected', {
      method: method,
      timestamp: Date.now()
    });
  }
};
```

---

## 🐞 Troubleshooting

**Script not working?**

1. Check browser console for errors
2. Verify script loads after DOM
3. Test in incognito mode
4. Check Content Security Policy rules

**Too many false positives?**

```javascript
window.AdGateConfig = {
  sensitivity: 'low',           // Reduce sensitivity
  retryInterval: 60000,         // Increase retry interval
  whitelist: ['your-domain.com'] // Add to whitelist
};
```

**Performance issues?**

```javascript
window.AdGateConfig = {
  sensitivity: 'medium',        // Use medium sensitivity
  retryInterval: 45000         // Increase retry interval
};
```

**Development Environment**

```javascript
// Disable in development
if (location.hostname === 'localhost') {
  window.AdGateConfig = { whitelist: ['localhost'] };
}
```

---

## 🔧 Advanced Usage

**Conditional Loading**

```javascript
// Only load on specific pages
if (window.location.pathname.includes('/premium-content/')) {
  window.AdGateConfig = { sensitivity: 'high' };
  
  const script = document.createElement('script');
  script.src = 'https://unpkg.com/adgate/js/lib.js';
  document.head.appendChild(script);
}
```

**Custom Event Handling**

```javascript
// Listen for detection events
document.addEventListener('adblock-status', function(e) {
  if (e.detail.detected) {
    console.log('Adblock detected via:', e.detail.method);
    // Your custom logic here
  }
});
```

---

## 🛡 Best Practices

**Performance**
- Load AdGate after critical content
- Use appropriate sensitivity levels
- Consider user experience impact

**User Experience**
- Provide clear instructions
- Offer alternative access methods
- Respect user privacy choices

**Development**
- Test across different browsers
- Use whitelist in development
- Monitor false positive rates

**Legal Compliance**
- Inform users about ad requirements
- Provide opt-out mechanisms where required
- Follow local privacy regulations

---

## 🤝 Contributing

PRs welcome! Please test thoroughly across browsers before submitting.

**Development Setup**
```bash
git clone https://github.com/kikkopy/adgate.git
cd adgate
npm install
npm test
```

## 📜 License

MIT License. Free for personal and commercial use.

---

**Created by [kikkopy](https://github.com/kikkopy)**
