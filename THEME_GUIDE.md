# Theme System Guide

This document outlines the consistent theming system implemented across all pages of the website.

## Overview

The website uses a unified dark tech-focused theme with bright accent colors that is consistently applied across all pages and components.

## Theme Components

### 1. ThemeProvider (`src/components/ThemeProvider.tsx`)
- Manages theme state (dark/light mode)
- Provides theme context to all components
- Handles theme persistence in localStorage
- Respects user's system preference

### 2. Layout Component (`src/components/Layout.tsx`)
- Provides consistent page structure
- Includes Navigation and Footer components
- Handles proper spacing and layout

### 3. GlobalStyles (`src/components/GlobalStyles.tsx`)
- Applies global CSS styles
- Custom scrollbar styling
- Focus and selection styles
- Smooth transitions and animations

### 4. PageContainer (`src/components/PageContainer.tsx`)
- Consistent page wrapper with animations
- Proper background and spacing
- Fade-in animations for page transitions

## Color System

### Primary Colors
- **Tech Primary**: Blue accent (`hsl(217 91% 60%)`)
- **Tech Secondary**: Green accent (`hsl(142 76% 36%)`)
- **Tech Accent**: Yellow accent (`hsl(39 100% 50%)`)

### Background Colors
- **Background**: Dark background (`hsl(240 10% 3.9%)`)
- **Card**: Slightly lighter background (`hsl(240 10% 6%)`)
- **Border**: Subtle borders (`hsl(240 4% 16%)`)

### Text Colors
- **Foreground**: Primary text (`hsl(0 0% 98%)`)
- **Muted**: Secondary text (`hsl(240 5% 64.9%)`)

## Typography

### Headings
- H1: `text-4xl md:text-6xl font-bold`
- H2: `text-3xl md:text-4xl font-bold`
- H3: `text-2xl md:text-3xl font-semibold`

### Body Text
- Body: `text-base md:text-lg`
- Small: `text-sm`

## Animations

### Key Animations
- `fade-in`: Smooth fade-in effect
- `scale-in`: Scale animation for cards
- `glow`: Pulsing glow effect
- `float`: Floating animation
- `gradient-shift`: Animated gradient backgrounds

## Components

### Button Variants
- `tech`: Primary gradient button with glow effect
- `hero`: Hero section button
- `accent`: Accent colored button
- `outline`: Bordered button
- `ghost`: Minimal button

### Card Styling
- Background: `bg-card`
- Border: `border border-border`
- Shadow: `shadow-card`
- Radius: `rounded-lg`

## Usage Examples

### Using the Layout Component
```tsx
import Layout from "@/components/Layout";

const MyPage = () => (
  <Layout>
    <div className="container mx-auto px-4 py-16">
      <h1 className="text-4xl font-bold text-foreground">
        My Page Content
      </h1>
    </div>
  </Layout>
);
```

### Using Theme Colors
```tsx
import { theme } from "@/lib/theme";

// In CSS
.my-element {
  background: var(--tech-primary);
  color: var(--foreground);
}
```

### Using Common Classes
```tsx
import { commonClasses } from "@/lib/theme";

<div className={commonClasses.card}>
  <h2 className={commonClasses.text.gradient}>
    Gradient Text
  </h2>
</div>
```

## Theme Toggle

The navigation includes a theme toggle button that allows users to switch between light and dark modes. The theme preference is saved in localStorage and respects the user's system preference.

## Responsive Design

All theme elements are responsive and adapt to different screen sizes:
- Mobile-first approach
- Responsive typography
- Adaptive spacing
- Mobile-optimized navigation

## Accessibility

The theme system includes:
- High contrast ratios
- Focus indicators
- Screen reader support
- Keyboard navigation
- Reduced motion support

## File Structure

```
src/
├── components/
│   ├── Layout.tsx
│   ├── ThemeProvider.tsx
│   ├── GlobalStyles.tsx
│   ├── PageContainer.tsx
│   └── Navigation.tsx
├── lib/
│   └── theme.ts
├── pages/
│   ├── Index.tsx
│   └── NotFound.tsx
└── App.tsx
```

## Best Practices

1. **Always use the Layout component** for new pages
2. **Use theme constants** from `src/lib/theme.ts`
3. **Apply consistent spacing** using the spacing system
4. **Use semantic color names** instead of hardcoded values
5. **Test in both light and dark modes**
6. **Ensure proper contrast ratios**
7. **Use animations sparingly** and consistently

## Adding New Pages

When adding new pages, follow this pattern:

```tsx
import Layout from "@/components/Layout";
import PageContainer from "@/components/PageContainer";

const NewPage = () => (
  <Layout>
    <PageContainer>
      <div className="container mx-auto px-4 py-16">
        {/* Page content */}
      </div>
    </PageContainer>
  </Layout>
);
```

This ensures consistent theming and layout across all pages. 