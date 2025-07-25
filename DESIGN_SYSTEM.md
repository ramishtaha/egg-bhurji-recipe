# Culinary Craft Design System

## Overview

The Culinary Craft Design System is a comprehensive, extensible framework designed to create consistent, accessible, and beautiful recipe experiences. This system supports various recipe types, cooking styles, and interactive features while maintaining visual cohesion across the entire platform.

## Table of Contents

1. [Design Principles](#design-principles)
2. [Color System](#color-system)
3. [Typography](#typography)
4. [Component Library](#component-library)
5. [Recipe Templates](#recipe-templates)
6. [Layout Patterns](#layout-patterns)
7. [Interactive Elements](#interactive-elements)
8. [Content Guidelines](#content-guidelines)
9. [Accessibility](#accessibility)
10. [Usage Guidelines](#usage-guidelines)
11. [Extension Patterns](#extension-patterns)

## Design Principles

### 1. **Clarity First**
Every recipe component should be immediately understandable, reducing cognitive load for users who are actively cooking.

### 2. **Progressive Enhancement**
Basic functionality works without JavaScript, with enhanced experiences layered on top.

### 3. **Mobile-First**
All components are designed primarily for mobile screens, then enhanced for larger displays.

### 4. **Consistent Interaction**
Similar interactions should behave identically across all recipes and contexts.

### 5. **Inclusive Design**
Components support various skill levels, dietary restrictions, and accessibility needs.

## Color System

### Primary Palette
- **Primary Orange**: `#d97706` - Main brand color, used for primary actions
- **Primary Dark**: `#c2670c` - Hover states and emphasis
- **Primary Light**: `#fbbf24` - Accent highlights and backgrounds

### Recipe Category Colors
```css
/* Main Courses */
--category-main: #dc2626;        /* Red */
--category-main-light: #fca5a5;

/* Breakfast */
--category-breakfast: #ca8a04;   /* Yellow */
--category-breakfast-light: #fde047;

/* Snacks */
--category-snacks: #16a34a;     /* Green */
--category-snacks-light: #86efac;

/* Desserts */
--category-desserts: #a855f7;   /* Purple */
--category-desserts-light: #d8b4fe;

/* Beverages */
--category-beverages: #0ea5e9;  /* Blue */
--category-beverages-light: #7dd3fc;

/* Appetizers */
--category-appetizers: #ea580c; /* Orange */
--category-appetizers-light: #fed7aa;
```

### Difficulty Level Colors
```css
--difficulty-easy: #16a34a;      /* Green */
--difficulty-medium: #ca8a04;    /* Yellow */
--difficulty-hard: #dc2626;      /* Red */
--difficulty-expert: #7c2d12;    /* Dark Red */
```

### Semantic Colors
```css
--success: #16a34a;
--warning: #ca8a04;
--error: #dc2626;
--info: #0ea5e9;
```

## Typography

### Font Stack
```css
--font-display: 'Playfair Display', serif;  /* Headlines, recipe titles */
--font-body: 'Inter', sans-serif;           /* Body text, ingredients */
--font-mono: 'JetBrains Mono', monospace;   /* Measurements, times */
```

### Scale
```css
/* Display Sizes - Recipe Titles */
.display-1 { font-size: 4.5rem; }   /* Hero recipe titles */
.display-2 { font-size: 3.75rem; }  /* Section headers */
.display-3 { font-size: 3rem; }     /* Sub-sections */

/* Heading Sizes */
.heading-1 { font-size: 2.25rem; }  /* Recipe card titles */
.heading-2 { font-size: 1.875rem; } /* Step headers */
.heading-3 { font-size: 1.5rem; }   /* Ingredient groups */
.heading-4 { font-size: 1.25rem; }  /* Sub-steps */

/* Body Sizes */
.body-large { font-size: 1.125rem; }    /* Important instructions */
.body-base { font-size: 1rem; }         /* Standard text */
.body-small { font-size: 0.875rem; }    /* Secondary info */
.caption { font-size: 0.75rem; }        /* Notes, disclaimers */
```

## Component Library

### Recipe Cards

#### Standard Recipe Card
```html
<article class="recipe-card" data-category="main-course" data-difficulty="medium">
    <div class="recipe-card-header">
        <div class="recipe-emoji">🍛</div>
        <h3 class="recipe-title">Recipe Name</h3>
        <p class="recipe-subtitle">Brief description</p>
    </div>
    
    <div class="recipe-stats">
        <div class="stat-item">
            <div class="stat-icon">⏱️</div>
            <div class="stat-value">30 min</div>
            <div class="stat-label">Total</div>
        </div>
        <!-- More stats -->
    </div>
    
    <div class="recipe-features">
        <!-- Feature highlights -->
    </div>
    
    <div class="recipe-card-footer">
        <a href="#" class="btn btn-primary">Start Cooking</a>
    </div>
</article>
```

#### Compact Recipe Card
For recipe collections and related recipes:
```html
<article class="recipe-card recipe-card-compact">
    <div class="recipe-thumbnail">
        <span class="recipe-emoji">🥚</span>
    </div>
    <div class="recipe-info">
        <h4 class="recipe-title">Recipe Name</h4>
        <div class="recipe-meta">
            <span class="time">15 min</span>
            <span class="difficulty">Easy</span>
        </div>
    </div>
</article>
```

### Interactive Elements

#### Difficulty Toggle Component
For recipes with easy and complex variations:
```html
<div class="difficulty-toggle">
    <span class="font-semibold">Quick & Easy</span>
    <label class="toggle-switch">
        <input type="checkbox" id="difficultyToggle">
        <span class="toggle-slider"></span>
    </label>
    <span class="font-semibold text-orange-600">Taste Focus</span>
</div>
```

#### Accordion Sections
For collapsible recipe sections:
```html
<div class="accordion-section">
    <button class="accordion-toggle">
        <span>Section Title</span>
        <span class="accordion-icon">▼</span>
    </button>
    <div class="accordion-content">
        <div class="accordion-body">
            <!-- Section content -->
        </div>
    </div>
</div>
```

#### Advanced Serving Calculator
Enhanced version with better styling:
```html
<div class="serving-calculator">
    <div class="serving-control">
        <button class="serving-btn">−</button>
        <span class="serving-display">
            <span id="serving-count">2</span> servings
        </span>
        <button class="serving-btn">+</button>
    </div>
</div>
```

#### Step Navigation
```html
<div class="step-navigation">
    <div class="step-progress">
        <div class="progress-bar">
            <div class="progress-fill" style="width: 30%"></div>
        </div>
        <span class="step-counter">Step 3 of 10</span>
    </div>
    
    <div class="step-controls">
        <button class="btn btn-ghost step-prev">← Previous</button>
        <button class="btn btn-primary step-next">Next →</button>
    </div>
</div>
```

#### Ingredient Checklist
```html
<div class="ingredient-checklist">
    <h4 class="checklist-title">Ingredients</h4>
    <div class="ingredient-group" data-group="vegetables">
        <h5 class="group-title">Vegetables</h5>
        <label class="ingredient-item">
            <input type="checkbox" class="ingredient-checkbox">
            <span class="checkmark"></span>
            <span class="quantity">2 large</span>
            <span class="ingredient">onions, finely chopped</span>
        </label>
    </div>
</div>
```

#### Ingredient Selection Widgets
For recipes requiring specific ingredient choices (like beef cuts, rice types, etc.):
```html
<div class="ingredient-selector">
    <div class="selector-buttons">
        <button class="btn btn-secondary selected" data-option="chuck">Beef Chuck</button>
        <button class="btn btn-ghost" data-option="short-ribs">Short Ribs</button>
        <button class="btn btn-ghost" data-option="brisket">Brisket</button>
        <button class="btn btn-ghost" data-option="stewing">Stewing Beef</button>
    </div>
    <div class="selection-details card glass-effect">
        <!-- Selection details populated by JavaScript -->
    </div>
</div>
```

### Recipe Page Layout

#### Basic Structure
```html
<main class="recipe-page">
    <!-- Hero Section -->
    <section class="recipe-hero">
        <div class="recipe-header">
            <div class="recipe-emoji">🍛</div>
            <h1 class="recipe-title">Recipe Name</h1>
            <p class="recipe-description">Description</p>
        </div>
        <div class="recipe-stats-grid">
            <!-- Stats -->
        </div>
    </section>
    
    <!-- Introduction (optional) -->
    <section class="recipe-intro">
        <!-- Background, tips, etc. -->
    </section>
    
    <!-- Interactive Calculator -->
    <section class="recipe-calculator">
        <!-- Serving size adjuster -->
    </section>
    
    <!-- Ingredients -->
    <section class="recipe-ingredients" id="ingredients">
        <!-- Ingredient groups -->
    </section>
    
    <!-- Instructions -->
    <section class="recipe-instructions" id="instructions">
        <!-- Step-by-step guide -->
    </section>
    
    <!-- Variations (optional) -->
    <section class="recipe-variations">
        <!-- Different approaches -->
    </section>
    
    <!-- Storage & Tips -->
    <section class="recipe-tips">
        <!-- Additional information -->
    </section>
</main>
```

## Recipe Templates

### Template 1: Standard Recipe
For most traditional recipes with straightforward preparation.

**Components:**
- Recipe hero with stats
- Ingredient checklist with groups
- Step-by-step instructions
- Tips and storage section

**Best for:** Traditional dishes, basic preparations

### Template 2: Masterclass Recipe
For complex recipes requiring detailed explanation and guidance.

**Components:**
- Extended hero with background information
- Technique explanations
- Multiple cooking methods
- Detailed troubleshooting
- Video integration points

**Best for:** Complex dishes, technique-heavy recipes, traditional methods

### Template 3: Quick Recipe
For simple, fast preparations.

**Components:**
- Compact hero
- Single ingredient list
- Condensed instructions
- Time-saving tips

**Best for:** Under 30-minute recipes, snacks, beverages

### Template 5: Advanced Interactive Recipe
For recipes with multiple cooking methods and complex customization options.

**Components:**
- Extended hero with difficulty toggle
- Interactive method switcher
- Advanced serving calculator
- Accordion-based instructions
- Method-specific content cards

**Best for:** Complex traditional dishes, biryani, recipes with multiple preparation methods

### Template 6: Quick & Complex Toggle Recipe
For recipes that can be simplified or made more complex based on user preference.

**Components:**
- Difficulty toggle switch
- Dynamic content switching
- Method-specific ingredient lists
- Progressive complexity options

**Best for:** Traditional dishes that can be simplified, recipes with authentic vs. quick versions

## Layout Patterns

### Container Sizes
```css
.container-sm { max-width: 640px; }   /* Single column content */
.container-md { max-width: 768px; }   /* Instructions, ingredients */
.container-lg { max-width: 1024px; }  /* Recipe cards grid */
.container-xl { max-width: 1280px; }  /* Homepage layouts */
```

### Grid Systems
```css
/* Recipe Cards */
.recipe-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 2rem;
}

/* Ingredient Groups */
.ingredient-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1.5rem;
}

/* Stats Display */
.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
    gap: 1rem;
}
```

## Interactive Elements

### Calculator Components
All recipes should include serving size calculators that automatically update quantities.

```javascript
// Basic calculator functionality
class ServingCalculator {
    constructor(baseServings, ingredients) {
        this.baseServings = baseServings;
        this.ingredients = ingredients;
        this.currentServings = baseServings;
    }
    
    updateServings(newServings) {
        const ratio = newServings / this.baseServings;
        this.currentServings = newServings;
        
        this.ingredients.forEach(ingredient => {
            ingredient.updateQuantity(ratio);
        });
    }
}
```

### Progressive Enhancement
- Basic functionality works without JavaScript
- Enhanced interactions require JavaScript
- Graceful degradation for all features

## Content Guidelines

### Recipe Naming
- **Format**: "The [Adjective] [Dish Name]"
- **Examples**: "The Ultimate Egg Bhurji", "The Bachelor's Beef Mandi"
- **Avoid**: Generic names like "Chicken Curry Recipe"

### Descriptions
- **Length**: 1-2 sentences for cards, 2-3 for full descriptions
- **Tone**: Friendly, encouraging, specific
- **Include**: Unique selling point, target audience, key benefit

### Emoji Usage
- **Recipe Categories**: Consistent emoji per dish type
- **Variations**: Different emoji for variations
- **Cultural Sensitivity**: Appropriate representation

### SEO Optimization
- **Title Structure**: Recipe Name | Guide Type | Site Name
- **Meta Descriptions**: Include key terms, cooking time, unique features
- **Structured Data**: Complete Recipe schema implementation

## Accessibility

### Color Contrast
- **Minimum Ratio**: 4.5:1 for normal text
- **Large Text**: 3:1 for headings and large text
- **Interactive Elements**: Clear focus indicators

### Keyboard Navigation
- **Tab Order**: Logical progression through interactive elements
- **Focus Management**: Clear visual focus indicators
- **Skip Links**: Jump to main content areas

### Screen Readers
- **Alt Text**: Descriptive text for all images
- **ARIA Labels**: For complex interactive components
- **Semantic HTML**: Proper heading hierarchy, lists, etc.

### Motion Sensitivity
- **Reduced Motion**: Respect `prefers-reduced-motion`
- **Auto-play**: No auto-playing videos or animations
- **Optional Effects**: User control over enhanced animations

## Usage Guidelines

### Adding New Recipes

#### 1. Choose Template
Select appropriate template based on recipe complexity and features needed.

#### 2. Set Up Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Standard meta tags -->
    <title>[Recipe Name] | [Guide Type] | Culinary Craft</title>
    <!-- SEO optimization -->
    <!-- Structured data -->
    <!-- CSS includes -->
</head>
<body>
    <!-- Standard navigation -->
    <!-- Recipe content using chosen template -->
    <!-- Standard footer -->
    <!-- JavaScript includes -->
</body>
</html>
```

#### 3. Content Creation
- Write clear, action-oriented instructions
- Use consistent terminology
- Include troubleshooting tips
- Add cultural context where appropriate

#### 4. Testing Checklist
- [ ] Mobile responsiveness
- [ ] Calculator functionality
- [ ] Accessibility compliance
- [ ] Cross-browser compatibility
- [ ] Performance optimization

### Customizing Components

#### Color Variations
```css
/* Category-specific overrides */
.recipe-card[data-category="breakfast"] {
    --accent-color: var(--category-breakfast);
}

.recipe-card[data-category="dessert"] {
    --accent-color: var(--category-desserts);
}
```

#### Layout Modifications
```css
/* Compact layout for mobile */
@media (max-width: 768px) {
    .recipe-stats {
        grid-template-columns: repeat(2, 1fr);
    }
}
```

## Extension Patterns

### Adding New Recipe Categories

1. **Define Category Colors**
```css
:root {
    --category-newtype: #hexcode;
    --category-newtype-light: #hexcode;
}
```

2. **Update Component Styles**
```css
.recipe-card[data-category="newtype"] {
    --accent-color: var(--category-newtype);
}
```

3. **Add Category Icon/Emoji**
Choose representative emoji and add to style guide.

### Creating New Templates

1. **Analyze Requirements**
   - What unique features does this recipe type need?
   - How does it differ from existing templates?
   - What interactive elements are required?

2. **Design Component Structure**
   - Reuse existing components where possible
   - Create new components only when necessary
   - Maintain consistent spacing and typography

3. **Implement Template**
   - Create HTML structure
   - Add CSS modifications
   - Include JavaScript functionality
   - Test across devices

### Adding Interactive Features

1. **Progressive Enhancement**
   - Ensure basic functionality without JavaScript
   - Layer enhanced features on top
   - Provide fallbacks for failures

2. **Consistent Patterns**
   - Use established interaction patterns
   - Maintain consistent visual feedback
   - Follow accessibility guidelines

3. **Performance Considerations**
   - Minimize JavaScript bundle size
   - Use efficient DOM manipulation
   - Implement lazy loading where appropriate

## Version History

### v1.0.0 (Current)
- Initial design system documentation
- Core component library
- Three recipe templates
- Basic interactive features

### Future Versions
- Video integration components
- Advanced filtering systems
- User preference management
- Nutrition information displays
- Recipe scaling algorithms

---

## Quick Reference

### File Structure
```
/recipes/
├── index.html              # Homepage
├── assets/
│   ├── design-system.css   # Core styles
│   └── site.webmanifest   # PWA config
└── recipes/
    ├── [recipe-name].html  # Individual recipes
    └── ...
```

### Essential Classes
- `.recipe-card` - Standard recipe preview
- `.btn-primary` - Main call-to-action
- `.ingredient-list` - Ingredient checklist
- `.step-navigation` - Instruction progress
- `.calculator-widget` - Serving adjustment

### CSS Variables
- `--primary-500` - Main brand color
- `--text-primary` - Main text color
- `--bg-card` - Card backgrounds
- `--radius-lg` - Standard border radius
- `--space-6` - Standard spacing unit

This design system provides a solid foundation for creating consistent, accessible, and beautiful recipe experiences while allowing for future growth and customization.
