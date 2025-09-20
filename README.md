# AdGate

Robust anti-adblock solution for modern websites. Lightweight, undetectable, and effective.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Size](https://img.shields.io/badge/size-<3KB-green.svg)
![JavaScript](https://img.shields.io/badge/javascript-ES6+-yellow.svg)

## Why AdGate?

Most anti-adblock solutions are easily bypassed or detected. AdGate uses 14 different detection methods with randomized timing and self-protection to ensure your content stays protected.

## Quick Setup

Add one line to your website:

```html
<script src="https://raw.githubusercontent.com/kikkopy/adgate/refs/heads/main/js/lib.js"></script>
```

That's it. AdGate will automatically detect adblocks and block navigation.

## Detection Methods

AdGate combines multiple detection techniques for maximum effectiveness:

**Basic Detection**
- Hidden element tests
- Network request monitoring  
- CSS property analysis
- Script loading failures

**Advanced Detection**
- DOM mutation observation
- Browser extension scanning
- Performance timing analysis
- Error event capturing

**Stealth Methods**
- Canvas fingerprint testing
- Web worker blocking
- Property getter traps
- CSS injection tests
- XHR request monitoring
- Fetch API hooking

## Browser Support

Works on all modern browsers including Chrome, Firefox, Safari, Edge, and mobile browsers.

## Integration Examples

**Basic HTML**
```html
<!DOCTYPE html>
<html>
<head>
    <title>My Website</title>
</head>
<body>
    <h1>Your content here</h1>
    
    <script src="https://raw.githubusercontent.com/kikkopy/adgate/refs/heads/main/js/lib.js"></script>
</body>
</html>
```

**WordPress**
```php
function add_adgate() {
    wp_enqueue_script('adgate', 'https://raw.githubusercontent.com/kikkopy/adgate/refs/heads/main/js/lib.js', array(), '1.0.0', true);
}
add_action('wp_enqueue_scripts', 'add_adgate');
```

**React/Next.js**
```jsx
import { useEffect } from 'react';

export default function MyComponent() {
    useEffect(() => {
        const script = document.createElement('script');
        script.src = 'https://raw.githubusercontent.com/kikkopy/adgate/refs/heads/main/js/lib.js';
        document.body.appendChild(script);
    }, []);
    
    return <div>Your content</div>;
}
```

## Customization

The popup uses inline styles for compatibility but can be customized by modifying the source code. Look for the `s()` function to change appearance and messaging.

**Custom styling:**
```javascript
// Modify colors and appearance
background: '#000000';
border: '2px solid #262626';
color: 'white';
```

**Custom messages:**
```javascript
// Change popup text
innerHTML: `
    <h2>Custom Title</h2>
    <p>Your message here</p>
`;
```

## Performance

- **Size**: Under 3KB minified
- **Speed**: Detection completes in under 2 seconds  
- **Impact**: Zero effect on page load performance
- **Memory**: Minimal resource usage

## How It Works

AdGate runs detection methods asynchronously with randomized intervals to avoid pattern detection. When an adblocker is found, it shows a professional popup with blur effect and prevents access until disabled.

The script protects itself from modification and continues monitoring even after initial detection.

## Analytics Integration

Track adblock usage with your analytics:

```javascript
// Google Analytics example
gtag('event', 'adblock_detected', {
    'event_category': 'AdGate',
    'value': 1
});
```

## Troubleshooting

**Not working?**
- Check console for errors
- Verify script loads after DOM
- Test in incognito mode
- Check Content Security Policy

**False positives?**
- Lower detection sensitivity in source
- Add loading delays
- Test with different browsers

## Contributing

Pull requests welcome. Please test thoroughly before submitting.

## License

MIT License. Free for personal and commercial use.

---

**Created by [kikkopy](https://github.com/kikkopy)**
