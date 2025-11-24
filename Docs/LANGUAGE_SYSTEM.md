# Language Switcher Implementation Guide

## Current Status
✅ Basic infrastructure created:
- Translation dictionary (`assets/js/translations.js`)
- Language switcher JavaScript (`assets/js/main.js`)
- Language toggle button CSS
- LocalStorage persistence

## What's Working
1. **Language Toggle Button**: Added to footer (shows "EN" in Arabic mode, "ع" in English mode)
2. **State Persistence**: Language preference saved in localStorage
3. **RTL/LTR Switching**: Automatically changes text direction
4. **Translation System**: Ready to translate elements with `data-translate` attributes

## To Complete Full Implementation

### Step 1: Add data-translate attributes to HTML elements
Add `data-translate="key"` to elements you want to translate. Example:
```html
<h1 data-translate="heroTitle">الدرع - أمانك</h1>
<p data-translate="heroSubtitle">حيث تلتقي الحماية بالتكنولوجيا</p>
```

### Step 2: Key Elements to Translate
- Navigation links
- Hero section (title, subtitle, description, buttons)
- Service cards (titles and descriptions)
- About section
- CTA sections
- Footer sections

### Step 3: Test the System
1. Click the "EN" button in the footer
2. Page should switch to English
3. Refresh page - language should persist
4. Click "ع" to switch back to Arabic

## Quick Start for Full Implementation

If you want me to complete the full implementation, I can:
1. Add `data-translate` attributes to all text elements across all pages
2. Expand the translations dictionary with all content
3. Add smooth transitions for language switching
4. Create English versions of service descriptions

Would you like me to proceed with the complete implementation?

## Alternative Approach

For a simpler solution, I can create separate English pages:
- `index-en.html`
- `services/index-en.html`
- etc.

And the language switcher would navigate between Arabic and English versions.

Which approach would you prefer?
