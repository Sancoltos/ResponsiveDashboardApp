# Responsive Dashboard App - Technical Documentation
## Student Information
- **Name:** Adam Walters
- **Student ID:** N01701019
- **Course:** CPAN 213
- **Lab:** Lab 4 - Responsive Layouts with Flexbox
- **Date:** October 7th, 2025
---

## Responsive Design Implementation

### Breakpoint Strategy
to have 5 breakpoints for the best layouts across all the devices. So a small phone gets 1 column, medium and large get 2 and so on.

**Breakpoints Defined:**
- Small phones: < 350px width - 1 column layout
- Medium phones: 350-400px - 2 column layout
- Large phones: 400-500px - 2 column layout
- Tablets: 500-768px - 3 column layout
- Large tablets: > 768px - 4 column layout

**Design Decisions:**
These breakpoints were chosen to ensure content is legible and layouts remain clean across devices of different sizes.

### Grid System Implementation
This file directly deals with calculating the number of columns based on the current screen size.

**Column Calculation Logic:**

The grid automatically calculates the colomns based on the device width and its orientation. It 
use the getGridColumns() function to get a colomn count based on breakpoint

**Orientation Handling:**
When the orientation of the phone changes this is detected with a listner which will then update the layout.

### Typography Scaling
Font sizes scaled dynamicaly based on the screen width ensuing the text remains readable across all devices

**Scaling Formula:**
The rf() function calculates font sizes by multiplying the desired size by the ratio of current screen width to 320px and round to the nearest pixel

**Typography Scale:**
- h1: [28]pt
- h2: [24]pt
- h3: [20]pt
- body: [16]pt
- caption: [14]pt

### Spacing System
[Document spacing scale and usage]

**Spacing Values:**
- xs: [1%]
- sm: [2%]
- md: [4%]
- lg: [6%]
- xl: [8%]
---
## Platform-Specific Implementations

### iOS Specific Styling
[List iOS-specific styles used]
- Shadow implementation using shadowColor, shadowOffset, shadowOpacity
- Border radius preferences
- Status bar height adjustments

### Android Specific Styling
[List Android-specific styles used]
- Elevation for shadows
- Material Design color scheme
- Status bar translucent handling

---
## Component Architecture

### Widget System Design
[Explain the BaseWidget pattern and reusability]

### Component Hierarchy
DashboardScreen
├── DashboardHeader
│ ├── Menu Button
│ ├── Title/Subtitle
│ └── Notification/Profile Buttons
├── ResponsiveGrid
│ └── StatisticWidgets (4x)
└── BaseWidget
└── Quick Actions (4x)
---
## Performance Optimizations Applied

### StyleSheet Optimization
- Used StyleSheet.create() for all styles
- Avoided inline styles where possible
- Pre-calculated style objects for variants


### Render Optimization
- Memoization of expensive calculations
- Proper key props on mapped components
- Conditional rendering optimization


### Performance Measurements
- Scrolling: [60] FPS
- Orientation change: [60] FPS
- Widget interaction: [55] FPS
- Pull-to-refresh: [55] FPS
---
## Challenges Encountered and Solutions

### Challenge 1: Apk not injecting
**Problem:** as the metro bundler tries to inject the apk i fails
**Solution:** rerun the bundler after the emulator has fully started
**Learning:** sometimes a problem that is a head scratcher is actually a very easy fix

### Challenge 2: app icons 
**Problem:** app icons do not load and have a backup x icon
**Solution:** solution was to tell the build gradle in android app to copy icon fonts from node
**Learning:** this one took me a while but stackoverflow saves the day again

---

## Testing Results

### Device Testing Matrix

| Device Type | Screen Size | Orientation | Columns | Result |
|-------------|-------------|-------------|---------|--------|
| iPhone 15   | 393x852     | Portrait    | 2       | ✅ Pass |
| iPhone 15   | 852x393     | Landscape   | 2       | ✅ Pass |
| iPad Pro    | 1024x1366   | Portrait    | 3       | ✅ Pass |
| iPad Pro    | 1366x1024   | Landscape   | 4       | ✅ Pass |
| Pixel 7     | 412x915     | Portrait    | 2       | ✅ Pass |
| Pixel Tablet| 1600x2560   | Portrait    | 3       | ✅ Pass |

### Functionality Testing
- [ ] Responsive grid adjusts to screen size ✅
- [ ] Orientation changes handled correctly ✅
- [ ] Pull-to-refresh works smoothly ✅
- [ ] All widgets display correctly ✅
- [ ] Platform-specific styling applied ✅
- [ ] Performance maintained at 60fps ✅
- [ ] Accessibility labels present ✅
- [ ] No console errors or warnings ✅
---
## Code Quality Checklist
- [ ] All components properly commented
- [ ] Consistent naming conventions used
- [ ] No unused imports or variables
- [ ] Proper file organization
- [ ] ESLint rules followed
- [ ] Code formatted with Prettier
- [ ] No hardcoded values (using theme system)
- [ ] Accessibility props included
---
## Reflection

### What I Learned

So far what I have learned is react-native is complex but also not that bad once you start to get
the hang of it. It tends to be a very finiky language that has alot of quicks but can be pretty
powerfull. Im excitied to keep learning and see what is next 

### Skills Gained
- Responsive design for mobile applications
- Flexbox mastery for complex layouts
- Platform-specific styling techniques
- Performance optimization strategies
- Deeper react-native understanding

### Areas for Improvement

I need to improve on how long it takes me to read code. it takes me a very long
time to understand what im readding and that can cost a lot of time in my day. I 
know Im learning but I will keep pushing myself and eventually ill get there

### Application to Future Projects

these skills will apply by being able to write code faster as well and overall be a better programmer
---
**End of Documentation**