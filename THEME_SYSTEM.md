# Theme System Documentation

## Overview
The website now supports both Light and Dark themes with persistent storage using localStorage.

## Features

### 🌞 Light Mode (Default)
- Clean, bright interface
- White backgrounds (#ffffff)
- Dark text (#1F2223)
- Purple accents (#8226BF)
- Perfect for daytime viewing

### 🌙 Dark Mode
- Easy on the eyes
- Dark backgrounds (#1F2223, #303436)
- Light text (#e0e0e0)
- Same purple accents for brand consistency
- Ideal for nighttime or low-light environments

## How It Works

### Theme Toggle Button
- Located in the header navigation
- Moon icon (🌙) = Switch to Dark Mode
- Sun icon (☀️) = Switch to Light Mode
- Smooth rotation animation on hover
- Accessible with keyboard navigation

### Persistent Storage
The theme preference is saved in the browser's localStorage:
```javascript
localStorage.setItem('theme', 'light'); // or 'dark'
```

This means:
- ✅ Theme persists across page refreshes
- ✅ Theme persists across different pages
- ✅ Theme persists even after closing the browser
- ✅ Each user has their own preference

### Implementation Details

#### CSS Variables
```css
:root {
    --bg-color: #ffffff;
    --card-bg: #ffffff;
    --text-color: #1F2223;
    /* ... */
}

[data-theme="dark"] {
    --bg-color: #1F2223;
    --card-bg: #303436;
    --text-color: #e0e0e0;
    /* ... */
}
```

#### JavaScript
```javascript
// Check saved preference or default to light
const currentTheme = localStorage.getItem('theme') || 'light';
html.setAttribute('data-theme', currentTheme);

// Toggle between themes
themeToggle.addEventListener('click', () => {
    const newTheme = currentTheme === 'light' ? 'dark' : 'light';
    html.setAttribute('data-theme', newTheme);
    localStorage.setItem('theme', newTheme);
});
```

## Color Mappings

### Light Theme
| Element | Color | Hex |
|---------|-------|-----|
| Background | White | #ffffff |
| Card Background | White | #ffffff |
| Text | Almost Black | #1F2223 |
| Light Areas | Light Gray | #f5f5f5 |

### Dark Theme
| Element | Color | Hex |
|---------|-------|-----|
| Background | Almost Black | #1F2223 |
| Card Background | Dark Gray | #303436 |
| Text | Light Gray | #e0e0e0 |
| Light Areas | Slate Blue | #434573 |

### Consistent Across Themes
| Element | Color | Hex |
|---------|-------|-----|
| Primary | Purple | #8226BF |
| Secondary | Deep Blue | #020659 |
| Accent | Slate Blue | #434573 |

## Transitions
All theme changes are smooth with 0.3s transitions on:
- Background colors
- Text colors
- Border colors
- Shadow colors

## Accessibility
- ✅ ARIA labels on toggle button
- ✅ Keyboard accessible
- ✅ High contrast in both modes
- ✅ Focus indicators maintained
- ✅ Screen reader friendly

## Browser Support
- ✅ Chrome/Edge (latest)
- ✅ Firefox (latest)
- ✅ Safari (latest)
- ✅ Opera (latest)
- ⚠️ IE11 (limited support, defaults to light)

## Testing
To test the theme system:
1. Click the theme toggle button in the header
2. Navigate to different pages - theme should persist
3. Refresh the page - theme should remain
4. Close and reopen the browser - theme should be remembered
5. Open in incognito/private mode - should default to light

## Customization
To change the default theme, modify this line in `main.js`:
```javascript
const currentTheme = localStorage.getItem('theme') || 'light'; // Change 'light' to 'dark'
```

## Future Enhancements
Potential improvements:
- Auto-detect system preference (prefers-color-scheme)
- Scheduled theme switching (day/night)
- Additional theme options (high contrast, etc.)
- Theme preview before applying
