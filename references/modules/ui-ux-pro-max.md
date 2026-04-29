## Source: references/skills/ui-ux-pro-max/SKILL.md

---
name: ui-ux-pro-max
description: Design systems and component libraries with tokens, styles, and brand-level visual systems.
risk: unknown
source: community
date_added: 2026-02-27
---
# UI/UX Pro Max - Design Intelligence

Comprehensive design guide for web and mobile applications. Contains 50+ styles, 97 color palettes, 57 font pairings, 99 UX guidelines, and 25 chart types across 9 technology stacks. Searchable database with priority-based recommendations.

## When to Apply

Reference these guidelines when:
- Designing new UI components or pages
- Choosing color palettes and typography
- Reviewing code for UX issues
- Building landing pages or dashboards
- Implementing accessibility requirements

## Rule Categories by Priority

| Priority | Category | Impact | Domain |
|----------|----------|--------|--------|
| 1 | Accessibility | CRITICAL | `ux` |
| 2 | Touch & Interaction | CRITICAL | `ux` |
| 3 | Performance | HIGH | `ux` |
| 4 | Layout & Responsive | HIGH | `ux` |
| 5 | Typography & Color | MEDIUM | `typography`, `color` |
| 6 | Animation | MEDIUM | `ux` |
| 7 | Style Selection | MEDIUM | `style`, `product` |
| 8 | Charts & Data | LOW | `chart` |

## Quick Reference

### 1. Accessibility (CRITICAL)

- `color-contrast` - Minimum 4.5:1 ratio for normal text
- `focus-states` - Visible focus rings on interactive elements
- `alt-text` - Descriptive alt text for meaningful images
- `aria-labels` - aria-label for icon-only buttons
- `keyboard-nav` - Tab order matches visual order
- `form-labels` - Use label with for attribute

### 2. Touch & Interaction (CRITICAL)

- `touch-target-size` - Minimum 44x44px touch targets
- `hover-vs-tap` - Use click/tap for primary interactions
- `loading-buttons` - Disable button during async operations
- `error-feedback` - Clear error messages near problem
- `cursor-pointer` - Add cursor-pointer to clickable elements

### 3. Performance (HIGH)

- `image-optimization` - Use WebP, srcset, lazy loading
- `reduced-motion` - Check prefers-reduced-motion
- `content-jumping` - Reserve space for async content

### 4. Layout & Responsive (HIGH)

- `viewport-meta` - width=device-width initial-scale=1
- `readable-font-size` - Minimum 16px body text on mobile
- `horizontal-scroll` - Ensure content fits viewport width
- `z-index-management` - Define z-index scale (10, 20, 30, 50)

### 5. Typography & Color (MEDIUM)

- `line-height` - Use 1.5-1.75 for body text
- `line-length` - Limit to 65-75 characters per line
- `font-pairing` - Match heading/body font personalities

### 6. Animation (MEDIUM)

- `duration-timing` - Use 150-300ms for micro-interactions
- `transform-performance` - Use transform/opacity, not width/height
- `loading-states` - Skeleton screens or spinners

### 7. Style Selection (MEDIUM)

- `style-match` - Match style to product type
- `consistency` - Use same style across all pages
- `no-emoji-icons` - Use SVG icons, not emojis

### 8. Charts & Data (LOW)

- `chart-type` - Match chart type to data type
- `color-guidance` - Use accessible color palettes
- `data-table` - Provide table alternative for accessibility

## How to Use

Search specific domains using the CLI tool below.

---

## Prerequisites

Check if Python is installed:

```bash
python3 --version || python --version
```

If Python is not installed, install it based on user's OS:

**macOS:**
```bash
brew install python3
```

**Ubuntu/Debian:**
```bash
sudo apt update && sudo apt install python3
```

**Windows:**
```powershell
winget install Python.Python.3.12
```

---

## How to Use This Skill

When user requests UI/UX work (design, build, create, implement, review, fix, improve), follow this workflow:

### Step 1: Analyze User Requirements

Extract key information from user request:
- **Product type**: SaaS, e-commerce, portfolio, dashboard, landing page, etc.
- **Style keywords**: minimal, playful, professional, elegant, dark mode, etc.
- **Industry**: healthcare, fintech, gaming, education, etc.
- **Stack**: React, Vue, Next.js, or default to `html-tailwind`

### Step 2: Generate Design System (REQUIRED)

**Always start with `--design-system`** to get comprehensive recommendations with reasoning:

```bash
python3 .agent/skills/ui-ux-pro-max/scripts/search.py "<product_type> <industry> <keywords>" --design-system [-p "Project Name"]
```

This command:
1. Searches 5 domains in parallel (product, style, color, landing, typography)
2. Applies reasoning rules from `ui-reasoning.csv` to select best matches
3. Returns complete design system: pattern, style, colors, typography, effects
4. Includes anti-patterns to avoid

**Example:**
```bash
python3 .agent/skills/ui-ux-pro-max/scripts/search.py "beauty spa wellness service" --design-system -p "Serenity Spa"
```

### Step 3: Supplement with Detailed Searches (as needed)

After getting the design system, use domain searches to get additional details:

```bash
python3 .agent/skills/ui-ux-pro-max/scripts/search.py "<keyword>" --domain <domain> [-n <max_results>]
```

**When to use detailed searches:**

| Need | Domain | Example |
|------|--------|---------|
| More style options | `style` | `--domain style "glassmorphism dark"` |
| Chart recommendations | `chart` | `--domain chart "real-time dashboard"` |
| UX best practices | `ux` | `--domain ux "animation accessibility"` |
| Alternative fonts | `typography` | `--domain typography "elegant luxury"` |
| Landing structure | `landing` | `--domain landing "hero social-proof"` |

### Step 4: Stack Guidelines (Default: html-tailwind)

Get implementation-specific best practices. If user doesn't specify a stack, **default to `html-tailwind`**.

```bash
python3 .agent/skills/ui-ux-pro-max/scripts/search.py "<keyword>" --stack html-tailwind
```

Available stacks: `html-tailwind`, `react`, `nextjs`, `vue`, `svelte`, `swiftui`, `react-native`, `flutter`, `shadcn`

---

## Search Reference

### Available Domains

| Domain | Use For | Example Keywords |
|--------|---------|------------------|
| `product` | Product type recommendations | SaaS, e-commerce, portfolio, healthcare, beauty, service |
| `style` | UI styles, colors, effects | glassmorphism, minimalism, dark mode, brutalism |
| `typography` | Font pairings, Google Fonts | elegant, playful, professional, modern |
| `color` | Color palettes by product type | saas, ecommerce, healthcare, beauty, fintech, service |
| `landing` | Page structure, CTA strategies | hero, hero-centric, testimonial, pricing, social-proof |
| `chart` | Chart types, library recommendations | trend, comparison, timeline, funnel, pie |
| `ux` | Best practices, anti-patterns | animation, accessibility, z-index, loading |
| `react` | React/Next.js performance | waterfall, bundle, suspense, memo, rerender, cache |
| `web` | Web interface guidelines | aria, focus, keyboard, semantic, virtualize |
| `prompt` | AI prompts, CSS keywords | (style name) |

### Available Stacks

| Stack | Focus |
|-------|-------|
| `html-tailwind` | Tailwind utilities, responsive, a11y (DEFAULT) |
| `react` | State, hooks, performance, patterns |
| `nextjs` | SSR, routing, images, API routes |
| `vue` | Composition API, Pinia, Vue Router |
| `svelte` | Runes, stores, SvelteKit |
| `swiftui` | Views, State, Navigation, Animation |
| `react-native` | Components, Navigation, Lists |
| `flutter` | Widgets, State, Layout, Theming |
| `shadcn` | shadcn/ui components, theming, forms, patterns |

---

## Example Workflow

**User request:** "Làm landing page cho dịch vụ chăm sóc da chuyên nghiệp"

### Step 1: Analyze Requirements
- Product type: Beauty/Spa service
- Style keywords: elegant, professional, soft
- Industry: Beauty/Wellness
- Stack: html-tailwind (default)

### Step 2: Generate Design System (REQUIRED)

```bash
python3 .agent/skills/ui-ux-pro-max/scripts/search.py "beauty spa wellness service elegant" --design-system -p "Serenity Spa"
```

**Output:** Complete design system with pattern, style, colors, typography, effects, and anti-patterns.

### Step 3: Supplement with Detailed Searches (as needed)

```bash
# Get UX guidelines for animation and accessibility
python3 .agent/skills/ui-ux-pro-max/scripts/search.py "animation accessibility" --domain ux

# Get alternative typography options if needed
python3 .agent/skills/ui-ux-pro-max/scripts/search.py "elegant luxury serif" --domain typography
```

### Step 4: Stack Guidelines

```bash
python3 .agent/skills/ui-ux-pro-max/scripts/search.py "layout responsive form" --stack html-tailwind
```

**Then:** Synthesize design system + detailed searches and implement the design.

---

## Output Formats

The `--design-system` flag supports two output formats:

```bash
# ASCII box (default) - best for terminal display
python3 .agent/skills/ui-ux-pro-max/scripts/search.py "fintech crypto" --design-system

# Markdown - best for documentation
python3 .agent/skills/ui-ux-pro-max/scripts/search.py "fintech crypto" --design-system -f markdown
```

---

## Tips for Better Results

1. **Be specific with keywords** - "healthcare SaaS dashboard" > "app"
2. **Search multiple times** - Different keywords reveal different insights
3. **Combine domains** - Style + Typography + Color = Complete design system
4. **Always check UX** - Search "animation", "z-index", "accessibility" for common issues
5. **Use stack flag** - Get implementation-specific best practices
6. **Iterate** - If first search doesn't match, try different keywords

---

## Common Rules for Professional UI

These are frequently overlooked issues that make UI look unprofessional:

### Icons & Visual Elements

| Rule | Do | Don't |
|------|----|----- |
| **No emoji icons** | Use SVG icons (Heroicons, Lucide, Simple Icons) | Use emojis like 🎨 🚀 ⚙️ as UI icons |
| **Stable hover states** | Use color/opacity transitions on hover | Use scale transforms that shift layout |
| **Correct brand logos** | Research official SVG from Simple Icons | Guess or use incorrect logo paths |
| **Consistent icon sizing** | Use fixed viewBox (24x24) with w-6 h-6 | Mix different icon sizes randomly |

### Interaction & Cursor

| Rule | Do | Don't |
|------|----|----- |
| **Cursor pointer** | Add `cursor-pointer` to all clickable/hoverable cards | Leave default cursor on interactive elements |
| **Hover feedback** | Provide visual feedback (color, shadow, border) | No indication element is interactive |
| **Smooth transitions** | Use `transition-colors duration-200` | Instant state changes or too slow (>500ms) |

### Light/Dark Mode Contrast

| Rule | Do | Don't |
|------|----|----- |
| **Glass card light mode** | Use `bg-white/80` or higher opacity | Use `bg-white/10` (too transparent) |
| **Text contrast light** | Use `#0F172A` (slate-900) for text | Use `#94A3B8` (slate-400) for body text |
| **Muted text light** | Use `#475569` (slate-600) minimum | Use gray-400 or lighter |
| **Border visibility** | Use `border-gray-200` in light mode | Use `border-white/10` (invisible) |

### Layout & Spacing

| Rule | Do | Don't |
|------|----|----- |
| **Floating navbar** | Add `top-4 left-4 right-4` spacing | Stick navbar to `top-0 left-0 right-0` |
| **Content padding** | Account for fixed navbar height | Let content hide behind fixed elements |
| **Consistent max-width** | Use same `max-w-6xl` or `max-w-7xl` | Mix different container widths |

---

## Pre-Delivery Checklist

Before delivering UI code, verify these items:

### Visual Quality
- [ ] No emojis used as icons (use SVG instead)
- [ ] All icons from consistent icon set (Heroicons/Lucide)
- [ ] Brand logos are correct (verified from Simple Icons)
- [ ] Hover states don't cause layout shift
- [ ] Use theme colors directly (bg-primary) not var() wrapper

### Interaction
- [ ] All clickable elements have `cursor-pointer`
- [ ] Hover states provide clear visual feedback
- [ ] Transitions are smooth (150-300ms)
- [ ] Focus states visible for keyboard navigation

### Light/Dark Mode
- [ ] Light mode text has sufficient contrast (4.5:1 minimum)
- [ ] Glass/transparent elements visible in light mode
- [ ] Borders visible in both modes
- [ ] Test both modes before delivery

### Layout
- [ ] Floating elements have proper spacing from edges
- [ ] No content hidden behind fixed navbars
- [ ] Responsive at 375px, 768px, 1024px, 1440px
- [ ] No horizontal scroll on mobile

### Accessibility
- [ ] All images have alt text
- [ ] Form inputs have labels
- [ ] Color is not the only indicator
- [ ] `prefers-reduced-motion` respected

## When to Use
This skill is applicable to execute the workflow or actions described in the overview.

## Supplemental Guidance: Tailwind Design System

# Tailwind Design System

Build production-ready design systems with Tailwind CSS, including design tokens, component variants, responsive patterns, and accessibility.

## Use this skill when

- Creating a component library with Tailwind
- Implementing design tokens and theming
- Building responsive and accessible components
- Standardizing UI patterns across a codebase
- Migrating to or extending Tailwind CSS
- Setting up dark mode and color schemes

## Do not use this skill when

- The task is unrelated to tailwind design system
- You need a different domain or tool outside this scope

## Instructions

- Clarify goals, constraints, and required inputs.
- Apply relevant best practices and validate outcomes.
- Provide actionable steps and verification.
- If detailed examples are required, open `resources/implementation-playbook.md`.

## Resources

- `resources/implementation-playbook.md` for detailed patterns and examples.

## Supplemental Guidance: Radix Ui Design System

# Radix UI Design System

Build production-ready, accessible design systems using Radix UI primitives with full customization control and zero style opinions.

## Overview

Radix UI provides unstyled, accessible components (primitives) that you can customize to match any design system. This skill guides you through building scalable component libraries with Radix UI, focusing on accessibility-first design, theming architecture, and composable patterns.

**Key Strengths:**
- **Headless by design**: Full styling control without fighting defaults
- **Accessibility built-in**: WAI-ARIA compliant, keyboard navigation, screen reader support
- **Composable primitives**: Build complex components from simple building blocks
- **Framework agnostic**: Works with React, but styles work anywhere

## When to Use This Skill

- Creating a custom design system from scratch
- Building accessible UI component libraries
- Implementing complex interactive components (Dialog, Dropdown, Tabs, etc.)
- Migrating from styled component libraries to unstyled primitives
- Setting up theming systems with CSS variables or Tailwind
- Need full control over component behavior and styling
- Building applications requiring WCAG 2.1 AA/AAA compliance

## Do not use this skill when

- You need pre-styled components out of the box (use shadcn/ui, Mantine, etc.)
- Building simple static pages without interactivity
- The project doesn't use React 16.8+ (Radix requires hooks)
- You need components for frameworks other than React

---

## Core Principles

### 1. Accessibility First

Every Radix primitive is built with accessibility as the foundation:

- **Keyboard Navigation**: Full keyboard support (Tab, Arrow keys, Enter, Escape)
- **Screen Readers**: Proper ARIA attributes and live regions
- **Focus Management**: Automatic focus trapping and restoration
- **Disabled States**: Proper handling of disabled and aria-disabled

**Rule**: Never override accessibility features. Enhance, don't replace.

### 2. Headless Architecture

Radix provides **behavior**, you provide **appearance**:

```tsx
// ❌ Don't fight pre-styled components
<Button className="override-everything" />

// ✅ Radix gives you behavior, you add styling
<Dialog.Root>
  <Dialog.Trigger className="your-button-styles" />
  <Dialog.Content className="your-modal-styles" />
</Dialog.Root>
```

### 3. Composition Over Configuration

Build complex components from simple primitives:

```tsx
// Primitive components compose naturally
<Tabs.Root>
  <Tabs.List>
    <Tabs.Trigger value="tab1">Tab 1</Tabs.Trigger>
    <Tabs.Trigger value="tab2">Tab 2</Tabs.Trigger>
  </Tabs.List>
  <Tabs.Content value="tab1">Content 1</Tabs.Content>
  <Tabs.Content value="tab2">Content 2</Tabs.Content>
</Tabs.Root>
```

---

## Getting Started

### Installation

```bash
# Install individual primitives (recommended)
npm install @radix-ui/react-dialog @radix-ui/react-dropdown-menu

# Or install multiple at once
npm install @radix-ui/react-{dialog,dropdown-menu,tabs,tooltip}

# For styling (optional but common)
npm install clsx tailwind-merge class-variance-authority
```

### Basic Component Pattern

Every Radix component follows this pattern:

```tsx
import * as Dialog from '@radix-ui/react-dialog';

export function MyDialog() {
  return (
    <Dialog.Root>
      {/* Trigger the dialog */}
      <Dialog.Trigger asChild>
        <button className="trigger-styles">Open</button>
      </Dialog.Trigger>

      {/* Portal renders outside DOM hierarchy */}
      <Dialog.Portal>
        {/* Overlay (backdrop) */}
        <Dialog.Overlay className="overlay-styles" />
        
        {/* Content (modal) */}
        <Dialog.Content className="content-styles">
          <Dialog.Title>Title</Dialog.Title>
          <Dialog.Description>Description</Dialog.Description>
          
          {/* Your content here */}
          
          <Dialog.Close asChild>
            <button>Close</button>
          </Dialog.Close>
        </Dialog.Content>
      </Dialog.Portal>
    </Dialog.Root>
  );
}
```

---

## Theming Strategies

### Strategy 1: CSS Variables (Framework-Agnostic)

**Best for**: Maximum portability, SSR-friendly

```css
/* globals.css */
:root {
  --color-primary: 220 90% 56%;
  --color-surface: 0 0% 100%;
  --radius-base: 0.5rem;
  --shadow-lg: 0 10px 15px -3px rgb(0 0 0 / 0.1);
}

[data-theme="dark"] {
  --color-primary: 220 90% 66%;
  --color-surface: 222 47% 11%;
}
```

```tsx
// Component.tsx
<Dialog.Content 
  className="
    bg-[hsl(var(--color-surface))]
    rounded-[var(--radius-base)]
    shadow-[var(--shadow-lg)]
  "
/>
```

### Strategy 2: Tailwind + CVA (Class Variance Authority)

**Best for**: Tailwind projects, variant-heavy components

```tsx
// button.tsx
import { cva, type VariantProps } from 'class-variance-authority';
import { cn } from '@/lib/utils';

const buttonVariants = cva(
  // Base styles
  "inline-flex items-center justify-center rounded-md font-medium transition-colors focus-visible:outline-none disabled:pointer-events-none disabled:opacity-50",
  {
    variants: {
      variant: {
        default: "bg-primary text-primary-foreground hover:bg-primary/90",
        destructive: "bg-destructive text-destructive-foreground hover:bg-destructive/90",
        outline: "border border-input bg-background hover:bg-accent",
        ghost: "hover:bg-accent hover:text-accent-foreground",
      },
      size: {
        default: "h-10 px-4 py-2",
        sm: "h-9 rounded-md px-3",
        lg: "h-11 rounded-md px-8",
        icon: "h-10 w-10",
      },
    },
    defaultVariants: {
      variant: "default",
      size: "default",
    },
  }
);

interface ButtonProps extends VariantProps<typeof buttonVariants> {
  children: React.ReactNode;
}

export function Button({ variant, size, children }: ButtonProps) {
  return (
    <button className={cn(buttonVariants({ variant, size }))}>
      {children}
    </button>
  );
}
```

### Strategy 3: Stitches (CSS-in-JS)

**Best for**: Runtime theming, scoped styles

```tsx
import { styled } from '@stitches/react';
import * as Dialog from '@radix-ui/react-dialog';

const StyledContent = styled(Dialog.Content, {
  backgroundColor: '$surface',
  borderRadius: '$md',
  padding: '$6',
  
  variants: {
    size: {
      small: { width: '300px' },
      medium: { width: '500px' },
      large: { width: '700px' },
    },
  },
  
  defaultVariants: {
    size: 'medium',
  },
});
```

---

## Component Patterns

### Pattern 1: Compound Components with Context

**Use case**: Share state between primitive parts

```tsx
// Select.tsx
import * as Select from '@radix-ui/react-select';
import { CheckIcon, ChevronDownIcon } from '@radix-ui/react-icons';

export function CustomSelect({ items, placeholder, onValueChange }) {
  return (
    <Select.Root onValueChange={onValueChange}>
      <Select.Trigger className="select-trigger">
        <Select.Value placeholder={placeholder} />
        <Select.Icon>
          <ChevronDownIcon />
        </Select.Icon>
      </Select.Trigger>

      <Select.Portal>
        <Select.Content className="select-content">
          <Select.Viewport>
            {items.map((item) => (
              <Select.Item 
                key={item.value} 
                value={item.value}
                className="select-item"
              >
                <Select.ItemText>{item.label}</Select.ItemText>
                <Select.ItemIndicator>
                  <CheckIcon />
                </Select.ItemIndicator>
              </Select.Item>
            ))}
          </Select.Viewport>
        </Select.Content>
      </Select.Portal>
    </Select.Root>
  );
}
```

### Pattern 2: Polymorphic Components with `asChild`

**Use case**: Render as different elements without losing behavior

```tsx
// ✅ Render as Next.js Link but keep Radix behavior
<Dialog.Trigger asChild>
  <Link href="/settings">Open Settings</Link>
</Dialog.Trigger>

// ✅ Render as custom component
<DropdownMenu.Item asChild>
  <YourCustomButton icon={<Icon />}>Action</YourCustomButton>
</DropdownMenu.Item>
```

**Why `asChild` matters**: Prevents nested button/link issues in accessibility tree.

### Pattern 3: Controlled vs Uncontrolled

```tsx
// Uncontrolled (Radix manages state)
<Tabs.Root defaultValue="tab1">
  <Tabs.Trigger value="tab1">Tab 1</Tabs.Trigger>
</Tabs.Root>

// Controlled (You manage state)
const [activeTab, setActiveTab] = useState('tab1');

<Tabs.Root value={activeTab} onValueChange={setActiveTab}>
  <Tabs.Trigger value="tab1">Tab 1</Tabs.Trigger>
</Tabs.Root>
```

**Rule**: Use controlled when you need to sync with external state (URL, Redux, etc.).

### Pattern 4: Animation with Framer Motion

```tsx
import * as Dialog from '@radix-ui/react-dialog';
import { motion, AnimatePresence } from 'framer-motion';

export function AnimatedDialog({ open, onOpenChange }) {
  return (
    <Dialog.Root open={open} onOpenChange={onOpenChange}>
      <Dialog.Portal forceMount>
        <AnimatePresence>
          {open && (
            <>
              <Dialog.Overlay asChild>
                <motion.div
                  initial={{ opacity: 0 }}
                  animate={{ opacity: 1 }}
                  exit={{ opacity: 0 }}
                  className="dialog-overlay"
                />
              </Dialog.Overlay>
              
              <Dialog.Content asChild>
                <motion.div
                  initial={{ opacity: 0, scale: 0.95 }}
                  animate={{ opacity: 1, scale: 1 }}
                  exit={{ opacity: 0, scale: 0.95 }}
                  className="dialog-content"
                >
                  {/* Content */}
                </motion.div>
              </Dialog.Content>
            </>
          )}
        </AnimatePresence>
      </Dialog.Portal>
    </Dialog.Root>
  );
}
```

---

## Common Primitives Reference

### Dialog (Modal)

```tsx
<Dialog.Root> {/* State container */}
  <Dialog.Trigger /> {/* Opens dialog */}
  <Dialog.Portal> {/* Renders in portal */}
    <Dialog.Overlay /> {/* Backdrop */}
    <Dialog.Content> {/* Modal content */}
      <Dialog.Title /> {/* Required for a11y */}
      <Dialog.Description /> {/* Required for a11y */}
      <Dialog.Close /> {/* Closes dialog */}
    </Dialog.Content>
  </Dialog.Portal>
</Dialog.Root>
```

### Dropdown Menu

```tsx
<DropdownMenu.Root>
  <DropdownMenu.Trigger />
  <DropdownMenu.Portal>
    <DropdownMenu.Content>
      <DropdownMenu.Item />
      <DropdownMenu.Separator />
      <DropdownMenu.CheckboxItem />
      <DropdownMenu.RadioGroup>
        <DropdownMenu.RadioItem />
      </DropdownMenu.RadioGroup>
      <DropdownMenu.Sub> {/* Nested menus */}
        <DropdownMenu.SubTrigger />
        <DropdownMenu.SubContent />
      </DropdownMenu.Sub>
    </DropdownMenu.Content>
  </DropdownMenu.Portal>
</DropdownMenu.Root>
```

### Tabs

```tsx
<Tabs.Root defaultValue="tab1">
  <Tabs.List>
    <Tabs.Trigger value="tab1" />
    <Tabs.Trigger value="tab2" />
  </Tabs.List>
  <Tabs.Content value="tab1" />
  <Tabs.Content value="tab2" />
</Tabs.Root>
```

### Tooltip

```tsx
<Tooltip.Provider delayDuration={200}>
  <Tooltip.Root>
    <Tooltip.Trigger />
    <Tooltip.Portal>
      <Tooltip.Content side="top" align="center">
        Tooltip text
        <Tooltip.Arrow />
      </Tooltip.Content>
    </Tooltip.Portal>
  </Tooltip.Root>
</Tooltip.Provider>
```

### Popover

```tsx
<Popover.Root>
  <Popover.Trigger />
  <Popover.Portal>
    <Popover.Content side="bottom" align="start">
      Content
      <Popover.Arrow />
      <Popover.Close />
    </Popover.Content>
  </Popover.Portal>
</Popover.Root>
```

---

## Accessibility Checklist

### Every Component Must Have:

- [ ] **Focus Management**: Visible focus indicators on all interactive elements
- [ ] **Keyboard Navigation**: Full keyboard support (Tab, Arrows, Enter, Esc)
- [ ] **ARIA Labels**: Meaningful labels for screen readers
- [ ] **Color Contrast**: WCAG AA minimum (4.5:1 for text, 3:1 for UI)
- [ ] **Error States**: Clear error messages with `aria-invalid` and `aria-describedby`
- [ ] **Loading States**: Proper `aria-busy` during async operations

### Dialog-Specific:
- [ ] `Dialog.Title` is present (required for screen readers)
- [ ] `Dialog.Description` provides context
- [ ] Focus trapped inside modal when open
- [ ] Escape key closes dialog
- [ ] Focus returns to trigger on close

### Dropdown-Specific:
- [ ] Arrow keys navigate items
- [ ] Type-ahead search works
- [ ] First/last item wrapping behavior
- [ ] Selected state indicated visually and with ARIA

---

## Best Practices

### ✅ Do This

1. **Always use `asChild` to avoid wrapper divs**
   ```tsx
   <Dialog.Trigger asChild>
     <button>Open</button>
   </Dialog.Trigger>
   ```

2. **Provide semantic HTML**
   ```tsx
   <Dialog.Content asChild>
     <article role="dialog" aria-labelledby="title">
       {/* content */}
     </article>
   </Dialog.Content>
   ```

3. **Use CSS variables for theming**
   ```css
   .dialog-content {
     background: hsl(var(--surface));
     color: hsl(var(--on-surface));
   }
   ```

4. **Compose primitives for complex components**
   ```tsx
   function CommandPalette() {
     return (
       <Dialog.Root>
         <Dialog.Content>
           <Combobox /> {/* Radix Combobox inside Dialog */}
         </Dialog.Content>
       </Dialog.Root>
     );
   }
   ```

### ❌ Don't Do This

1. **Don't skip accessibility parts**
   ```tsx
   // ❌ Missing Title and Description
   <Dialog.Content>
     <div>Content</div>
   </Dialog.Content>
   ```

2. **Don't fight the primitives**
   ```tsx
   // ❌ Overriding internal behavior
   <Dialog.Content onClick={(e) => e.stopPropagation()}>
   ```

3. **Don't mix controlled and uncontrolled**
   ```tsx
   // ❌ Inconsistent state management
   <Tabs.Root defaultValue="tab1" value={activeTab}>
   ```

4. **Don't ignore keyboard navigation**
   ```tsx
   // ❌ Disabling keyboard behavior
   <DropdownMenu.Item onKeyDown={(e) => e.preventDefault()}>
   ```

---

## Real-World Examples

### Example 1: Command Palette (Combo Dialog)

```tsx
import * as Dialog from '@radix-ui/react-dialog';
import { Command } from 'cmdk';

export function CommandPalette() {
  const [open, setOpen] = useState(false);

  useEffect(() => {
    const down = (e: KeyboardEvent) => {
      if (e.key === 'k' && (e.metaKey || e.ctrlKey)) {
        e.preventDefault();
        setOpen((open) => !open);
      }
    };
    document.addEventListener('keydown', down);
    return () => document.removeEventListener('keydown', down);
  }, []);

  return (
    <Dialog.Root open={open} onOpenChange={setOpen}>
      <Dialog.Portal>
        <Dialog.Overlay className="fixed inset-0 bg-black/50" />
        <Dialog.Content className="fixed left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2">
          <Command>
            <Command.Input placeholder="Type a command..." />
            <Command.List>
              <Command.Empty>No results found.</Command.Empty>
              <Command.Group heading="Suggestions">
                <Command.Item>Calendar</Command.Item>
                <Command.Item>Search Emoji</Command.Item>
              </Command.Group>
            </Command.List>
          </Command>
        </Dialog.Content>
      </Dialog.Portal>
    </Dialog.Root>
  );
}
```

### Example 2: Dropdown Menu with Icons

```tsx
import * as DropdownMenu from '@radix-ui/react-dropdown-menu';
import { DotsHorizontalIcon } from '@radix-ui/react-icons';

export function ActionsMenu() {
  return (
    <DropdownMenu.Root>
      <DropdownMenu.Trigger asChild>
        <button className="icon-button" aria-label="Actions">
          <DotsHorizontalIcon />
        </button>
      </DropdownMenu.Trigger>

      <DropdownMenu.Portal>
        <DropdownMenu.Content className="dropdown-content" align="end">
          <DropdownMenu.Item className="dropdown-item">
            Edit
          </DropdownMenu.Item>
          <DropdownMenu.Item className="dropdown-item">
            Duplicate
          </DropdownMenu.Item>
          <DropdownMenu.Separator className="dropdown-separator" />
          <DropdownMenu.Item className="dropdown-item text-red-500">
            Delete
          </DropdownMenu.Item>
        </DropdownMenu.Content>
      </DropdownMenu.Portal>
    </DropdownMenu.Root>
  );
}
```

### Example 3: Form with Radix Select + React Hook Form

```tsx
import * as Select from '@radix-ui/react-select';
import { useForm, Controller } from 'react-hook-form';

interface FormData {
  country: string;
}

export function CountryForm() {
  const { control, handleSubmit } = useForm<FormData>();

  return (
    <form onSubmit={handleSubmit((data) => console.log(data))}>
      <Controller
        name="country"
        control={control}
        render={({ field }) => (
          <Select.Root onValueChange={field.onChange} value={field.value}>
            <Select.Trigger className="select-trigger">
              <Select.Value placeholder="Select a country" />
              <Select.Icon />
            </Select.Trigger>
            
            <Select.Portal>
              <Select.Content className="select-content">
                <Select.Viewport>
                  <Select.Item value="us">United States</Select.Item>
                  <Select.Item value="ca">Canada</Select.Item>
                  <Select.Item value="uk">United Kingdom</Select.Item>
                </Select.Viewport>
              </Select.Content>
            </Select.Portal>
          </Select.Root>
        )}
      />
      <button type="submit">Submit</button>
    </form>
  );
}
```

---

## Troubleshooting

### Problem: Dialog doesn't close on Escape key

**Cause**: `onEscapeKeyDown` event prevented or `open` state not synced

**Solution**:
```tsx
<Dialog.Root open={open} onOpenChange={setOpen}>
  {/* Don't prevent default on escape */}
</Dialog.Root>
```

### Problem: Dropdown menu positioning is off

**Cause**: Parent container has `overflow: hidden` or transform

**Solution**:
```tsx
// Use Portal to render outside overflow container
<DropdownMenu.Portal>
  <DropdownMenu.Content />
</DropdownMenu.Portal>
```

### Problem: Animations don't work

**Cause**: Portal content unmounts immediately

**Solution**:
```tsx
// Use forceMount + AnimatePresence
<Dialog.Portal forceMount>
  <AnimatePresence>
    {open && <Dialog.Content />}
  </AnimatePresence>
</Dialog.Portal>
```

### Problem: TypeScript errors with `asChild`

**Cause**: Type inference issues with polymorphic components

**Solution**:
```tsx
// Explicitly type your component
<Dialog.Trigger asChild>
  <button type="button">Open</button>
</Dialog.Trigger>
```

---

## Performance Optimization

### 1. Code Splitting

```tsx
// Lazy load heavy primitives
const Dialog = lazy(() => import('@radix-ui/react-dialog'));
const DropdownMenu = lazy(() => import('@radix-ui/react-dropdown-menu'));
```

### 2. Portal Container Reuse

```tsx
// Create portal container once
<Tooltip.Provider>
  {/* All tooltips share portal container */}
  <Tooltip.Root>...</Tooltip.Root>
  <Tooltip.Root>...</Tooltip.Root>
</Tooltip.Provider>
```

### 3. Memoization

```tsx
// Memoize expensive render functions
const SelectItems = memo(({ items }) => (
  items.map((item) => <Select.Item key={item.value} value={item.value} />)
));
```

---

## Integration with Popular Tools

### shadcn/ui (Built on Radix)

shadcn/ui is a collection of copy-paste components built with Radix + Tailwind.

```bash
npx shadcn-ui@latest init
npx shadcn-ui@latest add dialog
```

**When to use shadcn vs raw Radix**:
- Use shadcn: Quick prototyping, standard designs
- Use raw Radix: Full customization, unique designs

### Radix Themes (Official Styled System)

```tsx
import { Theme, Button, Dialog } from '@radix-ui/themes';

function App() {
  return (
    <Theme accentColor="crimson" grayColor="sand">
      <Button>Click me</Button>
    </Theme>
  );
}
```

---

## Related Skills

- `@tailwind-design-system` - Tailwind + Radix integration patterns
- `@react-patterns` - React composition patterns
- `@frontend-design` - Overall frontend architecture
- `@accessibility-compliance` - WCAG compliance testing

---

## Resources

### Official Documentation
- [Radix UI Docs](https://www.radix-ui.com/primitives)
- [Radix Colors](https://www.radix-ui.com/colors) - Accessible color system
- [Radix Icons](https://www.radix-ui.com/icons) - Icon library

### Community Resources
- [shadcn/ui](https://ui.shadcn.com) - Component collection
- [Radix UI Discord](https://discord.com/invite/7Xb99uG) - Community support
- [CVA Documentation](https://cva.style/docs) - Variant management

### Examples
- [Radix Playground](https://www.radix-ui.com/primitives/docs/overview/introduction#try-it-out)
- [shadcn/ui Source](https://github.com/shadcn-ui/ui) - Production examples

---

## Quick Reference

### Installation
```bash
npm install @radix-ui/react-{primitive-name}
```

### Basic Pattern
```tsx
<Primitive.Root>
  <Primitive.Trigger />
  <Primitive.Portal>
    <Primitive.Content />
  </Primitive.Portal>
</Primitive.Root>
```

### Key Props
- `asChild` - Render as child element
- `defaultValue` - Uncontrolled default
- `value` / `onValueChange` - Controlled state
- `open` / `onOpenChange` - Open state
- `side` / `align` - Positioning

---

**Remember**: Radix gives you **behavior**, you give it **beauty**. Accessibility is built-in, customization is unlimited.

## Supplemental Guidance: Core Components

# Core Components

## Design System Overview

Use components from your core library instead of raw platform components. This ensures consistent styling and behavior.

## Design Tokens

**NEVER hard-code values. Always use design tokens.**

### Spacing Tokens

```tsx
// CORRECT - Use tokens
<Box padding="$4" marginBottom="$2" />

// WRONG - Hard-coded values
<Box padding={16} marginBottom={8} />
```

| Token | Value |
|-------|-------|
| `$1` | 4px |
| `$2` | 8px |
| `$3` | 12px |
| `$4` | 16px |
| `$6` | 24px |
| `$8` | 32px |

### Color Tokens

```tsx
// CORRECT - Semantic tokens
<Text color="$textPrimary" />
<Box backgroundColor="$backgroundSecondary" />

// WRONG - Hard-coded colors
<Text color="#333333" />
<Box backgroundColor="rgb(245, 245, 245)" />
```

| Semantic Token | Use For |
|----------------|---------|
| `$textPrimary` | Main text |
| `$textSecondary` | Supporting text |
| `$textTertiary` | Disabled/hint text |
| `$primary500` | Brand/accent color |
| `$statusError` | Error states |
| `$statusSuccess` | Success states |

### Typography Tokens

```tsx
<Text fontSize="$lg" fontWeight="$semibold" />
```

| Token | Size |
|-------|------|
| `$xs` | 12px |
| `$sm` | 14px |
| `$md` | 16px |
| `$lg` | 18px |
| `$xl` | 20px |
| `$2xl` | 24px |

## Core Components

### Box

Base layout component with token support:

```tsx
<Box
  padding="$4"
  backgroundColor="$backgroundPrimary"
  borderRadius="$lg"
>
  {children}
</Box>
```

### HStack / VStack

Horizontal and vertical flex layouts:

```tsx
<HStack gap="$3" alignItems="center">
  <Icon name="user" />
  <Text>Username</Text>
</HStack>

<VStack gap="$4" padding="$4">
  <Heading>Title</Heading>
  <Text>Content</Text>
</VStack>
```

### Text

Typography with token support:

```tsx
<Text
  fontSize="$lg"
  fontWeight="$semibold"
  color="$textPrimary"
>
  Hello World
</Text>
```

### Button

Interactive button with variants:

```tsx
<Button
  onPress={handlePress}
  variant="solid"
  size="md"
  isLoading={loading}
  isDisabled={disabled}
>
  Click Me
</Button>
```

| Variant | Use For |
|---------|---------|
| `solid` | Primary actions |
| `outline` | Secondary actions |
| `ghost` | Tertiary/subtle actions |
| `link` | Inline actions |

### Input

Form input with validation:

```tsx
<Input
  value={value}
  onChangeText={setValue}
  placeholder="Enter text"
  error={touched ? errors.field : undefined}
  label="Field Name"
/>
```

### Card

Content container:

```tsx
<Card padding="$4" gap="$3">
  <CardHeader>
    <Heading size="sm">Card Title</Heading>
  </CardHeader>
  <CardBody>
    <Text>Card content</Text>
  </CardBody>
</Card>
```

## Layout Patterns

### Screen Layout

```tsx
const MyScreen = () => (
  <Screen>
    <ScreenHeader title="Page Title" />
    <ScreenContent padding="$4">
      {/* Content */}
    </ScreenContent>
  </Screen>
);
```

### Form Layout

```tsx
<VStack gap="$4" padding="$4">
  <Input label="Name" {...nameProps} />
  <Input label="Email" {...emailProps} />
  <Button isLoading={loading}>Submit</Button>
</VStack>
```

### List Item Layout

```tsx
<HStack
  padding="$4"
  gap="$3"
  alignItems="center"
  borderBottomWidth={1}
  borderColor="$borderLight"
>
  <Avatar source={{ uri: imageUrl }} size="md" />
  <VStack flex={1}>
    <Text fontWeight="$semibold">{title}</Text>
    <Text color="$textSecondary" fontSize="$sm">{subtitle}</Text>
  </VStack>
  <Icon name="chevron-right" color="$textTertiary" />
</HStack>
```

## Anti-Patterns

```tsx
// WRONG - Hard-coded values
<View style={{ padding: 16, backgroundColor: '#fff' }}>

// CORRECT - Design tokens
<Box padding="$4" backgroundColor="$backgroundPrimary">


// WRONG - Raw platform components
import { View, Text } from 'react-native';

// CORRECT - Core components
import { Box, Text } from 'components/core';


// WRONG - Inline styles
<Text style={{ fontSize: 18, fontWeight: '600' }}>

// CORRECT - Token props
<Text fontSize="$lg" fontWeight="$semibold">
```

## Component Props Pattern

When creating components, use token-based props:

```tsx
interface CardProps {
  padding?: '$2' | '$4' | '$6';
  variant?: 'elevated' | 'outlined' | 'filled';
  children: React.ReactNode;
}

const Card = ({ padding = '$4', variant = 'elevated', children }: CardProps) => (
  <Box
    padding={padding}
    backgroundColor="$backgroundPrimary"
    borderRadius="$lg"
    {...variantStyles[variant]}
  >
    {children}
  </Box>
);
```

## Integration with Other Skills

- **react-ui-patterns**: Use core components for UI states
- **testing-patterns**: Mock core components in tests
- **storybook**: Document component variants

## When to Use
This skill is applicable to execute the workflow or actions described in the overview.

## Supplemental Guidance: Ui Skills

# Ui Skills

## Overview

Opinionated, evolving constraints to guide agents when building interfaces

## When to Use This Skill

Use this skill when you need to work with opinionated, evolving constraints to guide agents when building interfaces.

## Instructions

This skill provides guidance and patterns for opinionated, evolving constraints to guide agents when building interfaces.

For more information, see the [source repository](https://github.com/ibelick/ui-skills).

## Supplemental Guidance: Design Md

# Stitch DESIGN.md Skill

You are an expert Design Systems Lead. Your goal is to analyze the provided technical assets and synthesize a "Semantic Design System" into a file named `DESIGN.md`.

## When to Use This Skill

Use this skill when:
- Analyzing Stitch projects
- Creating DESIGN.md files
- Synthesizing semantic design systems
- Working with Stitch design language
- Generating design documentation for Stitch projects

## Overview

This skill helps you create `DESIGN.md` files that serve as the "source of truth" for prompting Stitch to generate new screens that align perfectly with existing design language. Stitch interprets design through "Visual Descriptions" supported by specific color values.

## Prerequisites

- Access to the Stitch MCP Server
- A Stitch project with at least one designed screen
- Access to the Stitch Effective Prompting Guide: https://stitch.withgoogle.com/docs/learn/prompting/

## The Goal

The `DESIGN.md` file will serve as the "source of truth" for prompting Stitch to generate new screens that align perfectly with the existing design language. Stitch interprets design through "Visual Descriptions" supported by specific color values.

## Retrieval and Networking

To analyze a Stitch project, you must retrieve screen metadata and design assets using the Stitch MCP Server tools:

1. **Namespace discovery**: Run `list_tools` to find the Stitch MCP prefix. Use this prefix (e.g., `mcp_stitch:`) for all subsequent calls.

2. **Project lookup** (if Project ID is not provided):
   - Call `[prefix]:list_projects` with `filter: "view=owned"` to retrieve all user projects
   - Identify the target project by title or URL pattern
   - Extract the Project ID from the `name` field (e.g., `projects/13534454087919359824`)

3. **Screen lookup** (if Screen ID is not provided):
   - Call `[prefix]:list_screens` with the `projectId` (just the numeric ID, not the full path)
   - Review screen titles to identify the target screen (e.g., "Home", "Landing Page")
   - Extract the Screen ID from the screen's `name` field

4. **Metadata fetch**: 
   - Call `[prefix]:get_screen` with both `projectId` and `screenId` (both as numeric IDs only)
   - This returns the complete screen object including:
     - `screenshot.downloadUrl` - Visual reference of the design
     - `htmlCode.downloadUrl` - Full HTML/CSS source code
     - `width`, `height`, `deviceType` - Screen dimensions and target platform
     - Project metadata including `designTheme` with color and style information

5. **Asset download**:
   - Use `web_fetch` or `read_url_content` to download the HTML code from `htmlCode.downloadUrl`
   - Optionally download the screenshot from `screenshot.downloadUrl` for visual reference
   - Parse the HTML to extract Tailwind classes, custom CSS, and component patterns

6. **Project metadata extraction**:
   - Call `[prefix]:get_project` with the project `name` (full path: `projects/{id}`) to get:
     - `designTheme` object with color mode, fonts, roundness, custom colors
     - Project-level design guidelines and descriptions
     - Device type preferences and layout principles

## Analysis & Synthesis Instructions

### 1. Extract Project Identity (JSON)
- Locate the Project Title
- Locate the specific Project ID (e.g., from the `name` field in the JSON)

### 2. Define the Atmosphere (Image/HTML)
Evaluate the screenshot and HTML structure to capture the overall "vibe." Use evocative adjectives to describe the mood (e.g., "Airy," "Dense," "Minimalist," "Utilitarian").

### 3. Map the Color Palette (Tailwind Config/JSON)
Identify the key colors in the system. For each color, provide:
- A descriptive, natural language name that conveys its character (e.g., "Deep Muted Teal-Navy")
- The specific hex code in parentheses for precision (e.g., "#294056")
- Its specific functional role (e.g., "Used for primary actions")

### 4. Translate Geometry & Shape (CSS/Tailwind)
Convert technical `border-radius` and layout values into physical descriptions:
- Describe `rounded-full` as "Pill-shaped"
- Describe `rounded-lg` as "Subtly rounded corners"
- Describe `rounded-none` as "Sharp, squared-off edges"

### 5. Describe Depth & Elevation
Explain how the UI handles layers. Describe the presence and quality of shadows (e.g., "Flat," "Whisper-soft diffused shadows," or "Heavy, high-contrast drop shadows").

## Output Guidelines

- **Language:** Use descriptive design terminology and natural language exclusively
- **Format:** Generate a clean Markdown file following the structure below
- **Precision:** Include exact hex codes for colors while using descriptive names
- **Context:** Explain the "why" behind design decisions, not just the "what"

## Output Format (DESIGN.md Structure)

```markdown
# Design System: [Project Title]
**Project ID:** [Insert Project ID Here]

## 1. Visual Theme & Atmosphere
(Description of the mood, density, and aesthetic philosophy.)

## 2. Color Palette & Roles
(List colors by Descriptive Name + Hex Code + Functional Role.)

## 3. Typography Rules
(Description of font family, weight usage for headers vs. body, and letter-spacing character.)

## 4. Component Stylings
* **Buttons:** (Shape description, color assignment, behavior).
* **Cards/Containers:** (Corner roundness description, background color, shadow depth).
* **Inputs/Forms:** (Stroke style, background).

## 5. Layout Principles
(Description of whitespace strategy, margins, and grid alignment.)
```

## Usage Example

To use this skill for the Furniture Collection project:

1. **Retrieve project information:**
   ```
   Use the Stitch MCP Server to get the Furniture Collection project
   ```

2. **Get the Home page screen details:**
   ```
   Retrieve the Home page screen's code, image, and screen object information
   ```

3. **Reference best practices:**
   ```
   Review the Stitch Effective Prompting Guide at:
   https://stitch.withgoogle.com/docs/learn/prompting/
   ```

4. **Analyze and synthesize:**
   - Extract all relevant design tokens from the screen
   - Translate technical values into descriptive language
   - Organize information according to the DESIGN.md structure

5. **Generate the file:**
   - Create `DESIGN.md` in the project directory
   - Follow the prescribed format exactly
   - Ensure all color codes are accurate
   - Use evocative, designer-friendly language

## Best Practices

- **Be Descriptive:** Avoid generic terms like "blue" or "rounded." Use "Ocean-deep Cerulean (#0077B6)" or "Gently curved edges"
- **Be Functional:** Always explain what each design element is used for
- **Be Consistent:** Use the same terminology throughout the document
- **Be Visual:** Help readers visualize the design through your descriptions
- **Be Precise:** Include exact values (hex codes, pixel values) in parentheses after natural language descriptions

## Tips for Success

1. **Start with the big picture:** Understand the overall aesthetic before diving into details
2. **Look for patterns:** Identify consistent spacing, sizing, and styling patterns
3. **Think semantically:** Name colors by their purpose, not just their appearance
4. **Consider hierarchy:** Document how visual weight and importance are communicated
5. **Reference the guide:** Use language and patterns from the Stitch Effective Prompting Guide

## Common Pitfalls to Avoid

- ❌ Using technical jargon without translation (e.g., "rounded-xl" instead of "generously rounded corners")
- ❌ Omitting color codes or using only descriptive names
- ❌ Forgetting to explain functional roles of design elements
- ❌ Being too vague in atmosphere descriptions
- ❌ Ignoring subtle design details like shadows or spacing patterns

## Supplemental Guidance: Brand Guidelines Anthropic

# Anthropic Brand Styling

## Overview

To access Anthropic's official brand identity and style resources, use this skill.

**Keywords**: branding, corporate identity, visual identity, post-processing, styling, brand colors, typography, Anthropic brand, visual formatting, visual design

## Brand Guidelines

### Colors

**Main Colors:**

- Dark: `#141413` - Primary text and dark backgrounds
- Light: `#faf9f5` - Light backgrounds and text on dark
- Mid Gray: `#b0aea5` - Secondary elements
- Light Gray: `#e8e6dc` - Subtle backgrounds

**Accent Colors:**

- Orange: `#d97757` - Primary accent
- Blue: `#6a9bcc` - Secondary accent
- Green: `#788c5d` - Tertiary accent

### Typography

- **Headings**: Poppins (with Arial fallback)
- **Body Text**: Lora (with Georgia fallback)
- **Note**: Fonts should be pre-installed in your environment for best results

## Features

### Smart Font Application

- Applies Poppins font to headings (24pt and larger)
- Applies Lora font to body text
- Automatically falls back to Arial/Georgia if custom fonts unavailable
- Preserves readability across all systems

### Text Styling

- Headings (24pt+): Poppins font
- Body text: Lora font
- Smart color selection based on background
- Preserves text hierarchy and formatting

### Shape and Accent Colors

- Non-text shapes use accent colors
- Cycles through orange, blue, and green accents
- Maintains visual interest while staying on-brand

## Technical Details

### Font Management

- Uses system-installed Poppins and Lora fonts when available
- Provides automatic fallback to Arial (headings) and Georgia (body)
- No font installation required - works with existing system fonts
- For best results, pre-install Poppins and Lora fonts in your environment

### Color Application

- Uses RGB color values for precise brand matching
- Applied via python-pptx's RGBColor class
- Maintains color fidelity across different systems

## When to Use
This skill is applicable to execute the workflow or actions described in the overview.

---

## Merged Reference (legacy variant)

---
name: ui-ux-pro-max
description: "UI/UX design intelligence. 50 styles, 21 palettes, 50 font pairings, 20 charts, 9 stacks (React, Next.js, Vue, Svelte, SwiftUI, React Native, Flutter, Tailwind, shadcn/ui). Actions: plan, build, create, design, implement, review, fix, improve, optimize, enhance, refactor, check UI/UX code. Projects: website, landing page, dashboard, admin panel, e-commerce, SaaS, portfolio, blog, mobile app, .html, .tsx, .vue, .svelte. Elements: button, modal, navbar, sidebar, card, table, form, chart. Styles: glassmorphism, claymorphism, minimalism, brutalism, neumorphism, bento grid, dark mode, responsive, skeuomorphism, flat design. Topics: color palette, accessibility, animation, layout, typography, font pairing, spacing, hover, shadow, gradient. Integrations: shadcn/ui MCP for component search and examples."
---

# UI/UX Pro Max - Design Intelligence

Comprehensive design guide for web and mobile applications. Contains 50+ styles, 97 color palettes, 57 font pairings, 99 UX guidelines, and 25 chart types across 9 technology stacks. Searchable database with priority-based recommendations.

## When to Apply

Reference these guidelines when:
- Designing new UI components or pages
- Choosing color palettes and typography
- Reviewing code for UX issues
- Building landing pages or dashboards
- Implementing accessibility requirements

## Rule Categories by Priority

| Priority | Category | Impact | Domain |
|----------|----------|--------|--------|
| 1 | Accessibility | CRITICAL | `ux` |
| 2 | Touch & Interaction | CRITICAL | `ux` |
| 3 | Performance | HIGH | `ux` |
| 4 | Layout & Responsive | HIGH | `ux` |
| 5 | Typography & Color | MEDIUM | `typography`, `color` |
| 6 | Animation | MEDIUM | `ux` |
| 7 | Style Selection | MEDIUM | `style`, `product` |
| 8 | Charts & Data | LOW | `chart` |

## Quick Reference

### 1. Accessibility (CRITICAL)

- `color-contrast` - Minimum 4.5:1 ratio for normal text
- `focus-states` - Visible focus rings on interactive elements
- `alt-text` - Descriptive alt text for meaningful images
- `aria-labels` - aria-label for icon-only buttons
- `keyboard-nav` - Tab order matches visual order
- `form-labels` - Use label with for attribute

### 2. Touch & Interaction (CRITICAL)

- `touch-target-size` - Minimum 44x44px touch targets
- `hover-vs-tap` - Use click/tap for primary interactions
- `loading-buttons` - Disable button during async operations
- `error-feedback` - Clear error messages near problem
- `cursor-pointer` - Add cursor-pointer to clickable elements

### 3. Performance (HIGH)

- `image-optimization` - Use WebP, srcset, lazy loading
- `reduced-motion` - Check prefers-reduced-motion
- `content-jumping` - Reserve space for async content

### 4. Layout & Responsive (HIGH)

- `viewport-meta` - width=device-width initial-scale=1
- `readable-font-size` - Minimum 16px body text on mobile
- `horizontal-scroll` - Ensure content fits viewport width
- `z-index-management` - Define z-index scale (10, 20, 30, 50)

### 5. Typography & Color (MEDIUM)

- `line-height` - Use 1.5-1.75 for body text
- `line-length` - Limit to 65-75 characters per line
- `font-pairing` - Match heading/body font personalities

### 6. Animation (MEDIUM)

- `duration-timing` - Use 150-300ms for micro-interactions
- `transform-performance` - Use transform/opacity, not width/height
- `loading-states` - Skeleton screens or spinners

### 7. Style Selection (MEDIUM)

- `style-match` - Match style to product type
- `consistency` - Use same style across all pages
- `no-emoji-icons` - Use SVG icons, not emojis

### 8. Charts & Data (LOW)

- `chart-type` - Match chart type to data type
- `color-guidance` - Use accessible color palettes
- `data-table` - Provide table alternative for accessibility

## How to Use

Search specific domains using the CLI tool below.

---

## Prerequisites

Check if Python is installed:

```bash
python3 --version || python --version
```

If Python is not installed, install it based on user's OS:

**macOS:**
```bash
brew install python3
```

**Ubuntu/Debian:**
```bash
sudo apt update && sudo apt install python3
```

**Windows:**
```powershell
winget install Python.Python.3.12
```

---

## How to Use This Skill

When user requests UI/UX work (design, build, create, implement, review, fix, improve), follow this workflow:

### Step 1: Analyze User Requirements

Extract key information from user request:
- **Product type**: SaaS, e-commerce, portfolio, dashboard, landing page, etc.
- **Style keywords**: minimal, playful, professional, elegant, dark mode, etc.
- **Industry**: healthcare, fintech, gaming, education, etc.
- **Stack**: React, Vue, Next.js, or default to `html-tailwind`

### Step 2: Generate Design System (REQUIRED)

**Always start with `--design-system`** to get comprehensive recommendations with reasoning:

```bash
python3 skills/ui-ux-pro-max/scripts/search.py "<product_type> <industry> <keywords>" --design-system [-p "Project Name"]
```

This command:
1. Searches 5 domains in parallel (product, style, color, landing, typography)
2. Applies reasoning rules from `ui-reasoning.csv` to select best matches
3. Returns complete design system: pattern, style, colors, typography, effects
4. Includes anti-patterns to avoid

**Example:**
```bash
python3 skills/ui-ux-pro-max/scripts/search.py "beauty spa wellness service" --design-system -p "Serenity Spa"
```

### Step 2b: Persist Design System (Master + Overrides Pattern)

To save the design system for **hierarchical retrieval across sessions**, add `--persist`:

```bash
python3 skills/ui-ux-pro-max/scripts/search.py "<query>" --design-system --persist -p "Project Name"
```

This creates:
- `design-system/MASTER.md` — Global Source of Truth with all design rules
- `design-system/pages/` — Folder for page-specific overrides

**With page-specific override:**
```bash
python3 skills/ui-ux-pro-max/scripts/search.py "<query>" --design-system --persist -p "Project Name" --page "dashboard"
```

This also creates:
- `design-system/pages/dashboard.md` — Page-specific deviations from Master

**How hierarchical retrieval works:**
1. When building a specific page (e.g., "Checkout"), first check `design-system/pages/checkout.md`
2. If the page file exists, its rules **override** the Master file
3. If not, use `design-system/MASTER.md` exclusively

**Context-aware retrieval prompt:**
```
I am building the [Page Name] page. Please read design-system/MASTER.md.
Also check if design-system/pages/[page-name].md exists.
If the page file exists, prioritize its rules.
If not, use the Master rules exclusively.
Now, generate the code...
```

### Step 3: Supplement with Detailed Searches (as needed)

After getting the design system, use domain searches to get additional details:

```bash
python3 skills/ui-ux-pro-max/scripts/search.py "<keyword>" --domain <domain> [-n <max_results>]
```

**When to use detailed searches:**

| Need | Domain | Example |
|------|--------|---------|
| More style options | `style` | `--domain style "glassmorphism dark"` |
| Chart recommendations | `chart` | `--domain chart "real-time dashboard"` |
| UX best practices | `ux` | `--domain ux "animation accessibility"` |
| Alternative fonts | `typography` | `--domain typography "elegant luxury"` |
| Landing structure | `landing` | `--domain landing "hero social-proof"` |

### Step 4: Stack Guidelines (Default: html-tailwind)

Get implementation-specific best practices. If user doesn't specify a stack, **default to `html-tailwind`**.

```bash
python3 skills/ui-ux-pro-max/scripts/search.py "<keyword>" --stack html-tailwind
```

Available stacks: `html-tailwind`, `react`, `nextjs`, `vue`, `svelte`, `swiftui`, `react-native`, `flutter`, `shadcn`, `jetpack-compose`

---

## Search Reference

### Available Domains

| Domain | Use For | Example Keywords |
|--------|---------|------------------|
| `product` | Product type recommendations | SaaS, e-commerce, portfolio, healthcare, beauty, service |
| `style` | UI styles, colors, effects | glassmorphism, minimalism, dark mode, brutalism |
| `typography` | Font pairings, Google Fonts | elegant, playful, professional, modern |
| `color` | Color palettes by product type | saas, ecommerce, healthcare, beauty, fintech, service |
| `landing` | Page structure, CTA strategies | hero, hero-centric, testimonial, pricing, social-proof |
| `chart` | Chart types, library recommendations | trend, comparison, timeline, funnel, pie |
| `ux` | Best practices, anti-patterns | animation, accessibility, z-index, loading |
| `react` | React/Next.js performance | waterfall, bundle, suspense, memo, rerender, cache |
| `web` | Web interface guidelines | aria, focus, keyboard, semantic, virtualize |
| `prompt` | AI prompts, CSS keywords | (style name) |

### Available Stacks

| Stack | Focus |
|-------|-------|
| `html-tailwind` | Tailwind utilities, responsive, a11y (DEFAULT) |
| `react` | State, hooks, performance, patterns |
| `nextjs` | SSR, routing, images, API routes |
| `vue` | Composition API, Pinia, Vue Router |
| `svelte` | Runes, stores, SvelteKit |
| `swiftui` | Views, State, Navigation, Animation |
| `react-native` | Components, Navigation, Lists |
| `flutter` | Widgets, State, Layout, Theming |
| `shadcn` | shadcn/ui components, theming, forms, patterns |
| `jetpack-compose` | Composables, Modifiers, State Hoisting, Recomposition |

---

## Example Workflow

**User request:** "Làm landing page cho dịch vụ chăm sóc da chuyên nghiệp"

### Step 1: Analyze Requirements
- Product type: Beauty/Spa service
- Style keywords: elegant, professional, soft
- Industry: Beauty/Wellness
- Stack: html-tailwind (default)

### Step 2: Generate Design System (REQUIRED)

```bash
python3 skills/ui-ux-pro-max/scripts/search.py "beauty spa wellness service elegant" --design-system -p "Serenity Spa"
```

**Output:** Complete design system with pattern, style, colors, typography, effects, and anti-patterns.

### Step 3: Supplement with Detailed Searches (as needed)

```bash
# Get UX guidelines for animation and accessibility
python3 skills/ui-ux-pro-max/scripts/search.py "animation accessibility" --domain ux

# Get alternative typography options if needed
python3 skills/ui-ux-pro-max/scripts/search.py "elegant luxury serif" --domain typography
```

### Step 4: Stack Guidelines

```bash
python3 skills/ui-ux-pro-max/scripts/search.py "layout responsive form" --stack html-tailwind
```

**Then:** Synthesize design system + detailed searches and implement the design.

---

## Output Formats

The `--design-system` flag supports two output formats:

```bash
# ASCII box (default) - best for terminal display
python3 skills/ui-ux-pro-max/scripts/search.py "fintech crypto" --design-system

# Markdown - best for documentation
python3 skills/ui-ux-pro-max/scripts/search.py "fintech crypto" --design-system -f markdown
```

---

## Tips for Better Results

1. **Be specific with keywords** - "healthcare SaaS dashboard" > "app"
2. **Search multiple times** - Different keywords reveal different insights
3. **Combine domains** - Style + Typography + Color = Complete design system
4. **Always check UX** - Search "animation", "z-index", "accessibility" for common issues
5. **Use stack flag** - Get implementation-specific best practices
6. **Iterate** - If first search doesn't match, try different keywords

---

## Common Rules for Professional UI

These are frequently overlooked issues that make UI look unprofessional:

### Icons & Visual Elements

| Rule | Do | Don't |
|------|----|----- |
| **No emoji icons** | Use SVG icons (Heroicons, Lucide, Simple Icons) | Use emojis like 🎨 🚀 ⚙️ as UI icons |
| **Stable hover states** | Use color/opacity transitions on hover | Use scale transforms that shift layout |
| **Correct brand logos** | Research official SVG from Simple Icons | Guess or use incorrect logo paths |
| **Consistent icon sizing** | Use fixed viewBox (24x24) with w-6 h-6 | Mix different icon sizes randomly |

### Interaction & Cursor

| Rule | Do | Don't |
|------|----|----- |
| **Cursor pointer** | Add `cursor-pointer` to all clickable/hoverable cards | Leave default cursor on interactive elements |
| **Hover feedback** | Provide visual feedback (color, shadow, border) | No indication element is interactive |
| **Smooth transitions** | Use `transition-colors duration-200` | Instant state changes or too slow (>500ms) |

### Light/Dark Mode Contrast

| Rule | Do | Don't |
|------|----|----- |
| **Glass card light mode** | Use `bg-white/80` or higher opacity | Use `bg-white/10` (too transparent) |
| **Text contrast light** | Use `#0F172A` (slate-900) for text | Use `#94A3B8` (slate-400) for body text |
| **Muted text light** | Use `#475569` (slate-600) minimum | Use gray-400 or lighter |
| **Border visibility** | Use `border-gray-200` in light mode | Use `border-white/10` (invisible) |

### Layout & Spacing

| Rule | Do | Don't |
|------|----|----- |
| **Floating navbar** | Add `top-4 left-4 right-4` spacing | Stick navbar to `top-0 left-0 right-0` |
| **Content padding** | Account for fixed navbar height | Let content hide behind fixed elements |
| **Consistent max-width** | Use same `max-w-6xl` or `max-w-7xl` | Mix different container widths |

---

## Pre-Delivery Checklist

Before delivering UI code, verify these items:

### Visual Quality
- [ ] No emojis used as icons (use SVG instead)
- [ ] All icons from consistent icon set (Heroicons/Lucide)
- [ ] Brand logos are correct (verified from Simple Icons)
- [ ] Hover states don't cause layout shift
- [ ] Use theme colors directly (bg-primary) not var() wrapper

### Interaction
- [ ] All clickable elements have `cursor-pointer`
- [ ] Hover states provide clear visual feedback
- [ ] Transitions are smooth (150-300ms)
- [ ] Focus states visible for keyboard navigation

### Light/Dark Mode
- [ ] Light mode text has sufficient contrast (4.5:1 minimum)
- [ ] Glass/transparent elements visible in light mode
- [ ] Borders visible in both modes
- [ ] Test both modes before delivery

### Layout
- [ ] Floating elements have proper spacing from edges
- [ ] No content hidden behind fixed navbars
- [ ] Responsive at 375px, 768px, 1024px, 1440px
- [ ] No horizontal scroll on mobile

### Accessibility
- [ ] All images have alt text
- [ ] Form inputs have labels
- [ ] Color is not the only indicator
- [ ] `prefers-reduced-motion` respected

---

## Merged Frontend Design Skill

---
name: frontend-design
description: Create distinctive, production-grade frontend interfaces with high design quality. Use this skill when the user asks to build web components, pages, artifacts, posters, or applications (examples include websites, landing pages, dashboards, React components, HTML/CSS layouts, or when styling/beautifying any web UI). Generates creative, polished code and UI design that avoids generic AI aesthetics.
license: Complete terms in LICENSE.txt
---

This skill guides creation of distinctive, production-grade frontend interfaces that avoid generic "AI slop" aesthetics. Implement real working code with exceptional attention to aesthetic details and creative choices.

The user provides frontend requirements: a component, page, application, or interface to build. They may include context about the purpose, audience, or technical constraints.

## Design Thinking

Before coding, understand the context and commit to a BOLD aesthetic direction:
- **Purpose**: What problem does this interface solve? Who uses it?
- **Tone**: Pick an extreme: brutally minimal, maximalist chaos, retro-futuristic, organic/natural, luxury/refined, playful/toy-like, editorial/magazine, brutalist/raw, art deco/geometric, soft/pastel, industrial/utilitarian, etc. There are so many flavors to choose from. Use these for inspiration but design one that is true to the aesthetic direction.
- **Constraints**: Technical requirements (framework, performance, accessibility).
- **Differentiation**: What makes this UNFORGETTABLE? What's the one thing someone will remember?

**CRITICAL**: Choose a clear conceptual direction and execute it with precision. Bold maximalism and refined minimalism both work - the key is intentionality, not intensity.

Then implement working code (HTML/CSS/JS, React, Vue, etc.) that is:
- Production-grade and functional
- Visually striking and memorable
- Cohesive with a clear aesthetic point-of-view
- Meticulously refined in every detail

## Frontend Aesthetics Guidelines

Focus on:
- **Typography**: Choose fonts that are beautiful, unique, and interesting. Avoid generic fonts like Arial and Inter; opt instead for distinctive choices that elevate the frontend's aesthetics; unexpected, characterful font choices. Pair a distinctive display font with a refined body font.
- **Color & Theme**: Commit to a cohesive aesthetic. Use CSS variables for consistency. Dominant colors with sharp accents outperform timid, evenly-distributed palettes.
- **Motion**: Use animations for effects and micro-interactions. Prioritize CSS-only solutions for HTML. Use Motion library for React when available. Focus on high-impact moments: one well-orchestrated page load with staggered reveals (animation-delay) creates more delight than scattered micro-interactions. Use scroll-triggering and hover states that surprise.
- **Spatial Composition**: Unexpected layouts. Asymmetry. Overlap. Diagonal flow. Grid-breaking elements. Generous negative space OR controlled density.
- **Backgrounds & Visual Details**: Create atmosphere and depth rather than defaulting to solid colors. Add contextual effects and textures that match the overall aesthetic. Apply creative forms like gradient meshes, noise textures, geometric patterns, layered transparencies, dramatic shadows, decorative borders, custom cursors, and grain overlays.

NEVER use generic AI-generated aesthetics like overused font families (Inter, Roboto, Arial, system fonts), cliched color schemes (particularly purple gradients on white backgrounds), predictable layouts and component patterns, and cookie-cutter design that lacks context-specific character.

Interpret creatively and make unexpected choices that feel genuinely designed for the context. No design should be the same. Vary between light and dark themes, different fonts, different aesthetics. NEVER converge on common choices (Space Grotesk, for example) across generations.

**IMPORTANT**: Match implementation complexity to the aesthetic vision. Maximalist designs need elaborate code with extensive animations and effects. Minimalist or refined designs need restraint, precision, and careful attention to spacing, typography, and subtle details. Elegance comes from executing the vision well.

Remember: AI assistant is capable of extraordinary creative work. Don't hold back, show what can truly be created when thinking outside the box and committing fully to a distinctive vision.

## Source: references/skills/ui-ux-pro-max/references/legacy/brand-guidelines-provider/SKILL.md

---
name: brand-guidelines-provider
description: "Applies Anthropic's official brand colors and typography to any sort of artifact that may benefit from having Anthropic's look-and-feel. Use it when brand colors or style guidelines, visual formatt..."
risk: unknown
source: community
date_added: "2026-02-27"
---

# Anthropic Brand Styling

## Overview

To access Anthropic's official brand identity and style resources, use this skill.

**Keywords**: branding, corporate identity, visual identity, post-processing, styling, brand colors, typography, Anthropic brand, visual formatting, visual design

## Brand Guidelines

### Colors

**Main Colors:**

- Dark: `#141413` - Primary text and dark backgrounds
- Light: `#faf9f5` - Light backgrounds and text on dark
- Mid Gray: `#b0aea5` - Secondary elements
- Light Gray: `#e8e6dc` - Subtle backgrounds

**Accent Colors:**

- Orange: `#d97757` - Primary accent
- Blue: `#6a9bcc` - Secondary accent
- Green: `#788c5d` - Tertiary accent

### Typography

- **Headings**: Poppins (with Arial fallback)
- **Body Text**: Lora (with Georgia fallback)
- **Note**: Fonts should be pre-installed in your environment for best results

## Features

### Smart Font Application

- Applies Poppins font to headings (24pt and larger)
- Applies Lora font to body text
- Automatically falls back to Arial/Georgia if custom fonts unavailable
- Preserves readability across all systems

### Text Styling

- Headings (24pt+): Poppins font
- Body text: Lora font
- Smart color selection based on background
- Preserves text hierarchy and formatting

### Shape and Accent Colors

- Non-text shapes use accent colors
- Cycles through orange, blue, and green accents
- Maintains visual interest while staying on-brand

## Technical Details

### Font Management

- Uses system-installed Poppins and Lora fonts when available
- Provides automatic fallback to Arial (headings) and Georgia (body)
- No font installation required - works with existing system fonts
- For best results, pre-install Poppins and Lora fonts in your environment

### Color Application

- Uses RGB color values for precise brand matching
- Applied via python-pptx's RGBColor class
- Maintains color fidelity across different systems

## When to Use
This skill is applicable to execute the workflow or actions described in the overview.

## Source: references/skills/ui-ux-pro-max/references/legacy/core-components/SKILL.md

---
name: core-components
description: "Core component library and design system patterns. Use when building UI, using design tokens, or working with the component library."
risk: unknown
source: community
date_added: "2026-02-27"
---

# Core Components

## Design System Overview

Use components from your core library instead of raw platform components. This ensures consistent styling and behavior.

## Design Tokens

**NEVER hard-code values. Always use design tokens.**

### Spacing Tokens

```tsx
// CORRECT - Use tokens
<Box padding="$4" marginBottom="$2" />

// WRONG - Hard-coded values
<Box padding={16} marginBottom={8} />
```

| Token | Value |
|-------|-------|
| `$1` | 4px |
| `$2` | 8px |
| `$3` | 12px |
| `$4` | 16px |
| `$6` | 24px |
| `$8` | 32px |

### Color Tokens

```tsx
// CORRECT - Semantic tokens
<Text color="$textPrimary" />
<Box backgroundColor="$backgroundSecondary" />

// WRONG - Hard-coded colors
<Text color="#333333" />
<Box backgroundColor="rgb(245, 245, 245)" />
```

| Semantic Token | Use For |
|----------------|---------|
| `$textPrimary` | Main text |
| `$textSecondary` | Supporting text |
| `$textTertiary` | Disabled/hint text |
| `$primary500` | Brand/accent color |
| `$statusError` | Error states |
| `$statusSuccess` | Success states |

### Typography Tokens

```tsx
<Text fontSize="$lg" fontWeight="$semibold" />
```

| Token | Size |
|-------|------|
| `$xs` | 12px |
| `$sm` | 14px |
| `$md` | 16px |
| `$lg` | 18px |
| `$xl` | 20px |
| `$2xl` | 24px |

## Core Components

### Box

Base layout component with token support:

```tsx
<Box
  padding="$4"
  backgroundColor="$backgroundPrimary"
  borderRadius="$lg"
>
  {children}
</Box>
```

### HStack / VStack

Horizontal and vertical flex layouts:

```tsx
<HStack gap="$3" alignItems="center">
  <Icon name="user" />
  <Text>Username</Text>
</HStack>

<VStack gap="$4" padding="$4">
  <Heading>Title</Heading>
  <Text>Content</Text>
</VStack>
```

### Text

Typography with token support:

```tsx
<Text
  fontSize="$lg"
  fontWeight="$semibold"
  color="$textPrimary"
>
  Hello World
</Text>
```

### Button

Interactive button with variants:

```tsx
<Button
  onPress={handlePress}
  variant="solid"
  size="md"
  isLoading={loading}
  isDisabled={disabled}
>
  Click Me
</Button>
```

| Variant | Use For |
|---------|---------|
| `solid` | Primary actions |
| `outline` | Secondary actions |
| `ghost` | Tertiary/subtle actions |
| `link` | Inline actions |

### Input

Form input with validation:

```tsx
<Input
  value={value}
  onChangeText={setValue}
  placeholder="Enter text"
  error={touched ? errors.field : undefined}
  label="Field Name"
/>
```

### Card

Content container:

```tsx
<Card padding="$4" gap="$3">
  <CardHeader>
    <Heading size="sm">Card Title</Heading>
  </CardHeader>
  <CardBody>
    <Text>Card content</Text>
  </CardBody>
</Card>
```

## Layout Patterns

### Screen Layout

```tsx
const MyScreen = () => (
  <Screen>
    <ScreenHeader title="Page Title" />
    <ScreenContent padding="$4">
      {/* Content */}
    </ScreenContent>
  </Screen>
);
```

### Form Layout

```tsx
<VStack gap="$4" padding="$4">
  <Input label="Name" {...nameProps} />
  <Input label="Email" {...emailProps} />
  <Button isLoading={loading}>Submit</Button>
</VStack>
```

### List Item Layout

```tsx
<HStack
  padding="$4"
  gap="$3"
  alignItems="center"
  borderBottomWidth={1}
  borderColor="$borderLight"
>
  <Avatar source={{ uri: imageUrl }} size="md" />
  <VStack flex={1}>
    <Text fontWeight="$semibold">{title}</Text>
    <Text color="$textSecondary" fontSize="$sm">{subtitle}</Text>
  </VStack>
  <Icon name="chevron-right" color="$textTertiary" />
</HStack>
```

## Anti-Patterns

```tsx
// WRONG - Hard-coded values
<View style={{ padding: 16, backgroundColor: '#fff' }}>

// CORRECT - Design tokens
<Box padding="$4" backgroundColor="$backgroundPrimary">


// WRONG - Raw platform components
import { View, Text } from 'react-native';

// CORRECT - Core components
import { Box, Text } from 'components/core';


// WRONG - Inline styles
<Text style={{ fontSize: 18, fontWeight: '600' }}>

// CORRECT - Token props
<Text fontSize="$lg" fontWeight="$semibold">
```

## Component Props Pattern

When creating components, use token-based props:

```tsx
interface CardProps {
  padding?: '$2' | '$4' | '$6';
  variant?: 'elevated' | 'outlined' | 'filled';
  children: React.ReactNode;
}

const Card = ({ padding = '$4', variant = 'elevated', children }: CardProps) => (
  <Box
    padding={padding}
    backgroundColor="$backgroundPrimary"
    borderRadius="$lg"
    {...variantStyles[variant]}
  >
    {children}
  </Box>
);
```

## Integration with Other Skills

- **react-ui-patterns**: Use core components for UI states
- **testing-patterns**: Mock core components in tests
- **storybook**: Document component variants

## When to Use
This skill is applicable to execute the workflow or actions described in the overview.

## Source: references/skills/ui-ux-pro-max/references/legacy/design-md/SKILL.md

---
name: design-md
description: "Analyze Stitch projects and synthesize a semantic design system into DESIGN.md files"
risk: safe
source: "https://github.com/google-labs-code/stitch-skills/tree/main/skills/design-md"
date_added: "2026-02-27"
---

# Stitch DESIGN.md Skill

You are an expert Design Systems Lead. Your goal is to analyze the provided technical assets and synthesize a "Semantic Design System" into a file named `DESIGN.md`.

## When to Use This Skill

Use this skill when:
- Analyzing Stitch projects
- Creating DESIGN.md files
- Synthesizing semantic design systems
- Working with Stitch design language
- Generating design documentation for Stitch projects

## Overview

This skill helps you create `DESIGN.md` files that serve as the "source of truth" for prompting Stitch to generate new screens that align perfectly with existing design language. Stitch interprets design through "Visual Descriptions" supported by specific color values.

## Prerequisites

- Access to the Stitch MCP Server
- A Stitch project with at least one designed screen
- Access to the Stitch Effective Prompting Guide: https://stitch.withgoogle.com/docs/learn/prompting/

## The Goal

The `DESIGN.md` file will serve as the "source of truth" for prompting Stitch to generate new screens that align perfectly with the existing design language. Stitch interprets design through "Visual Descriptions" supported by specific color values.

## Retrieval and Networking

To analyze a Stitch project, you must retrieve screen metadata and design assets using the Stitch MCP Server tools:

1. **Namespace discovery**: Run `list_tools` to find the Stitch MCP prefix. Use this prefix (e.g., `mcp_stitch:`) for all subsequent calls.

2. **Project lookup** (if Project ID is not provided):
   - Call `[prefix]:list_projects` with `filter: "view=owned"` to retrieve all user projects
   - Identify the target project by title or URL pattern
   - Extract the Project ID from the `name` field (e.g., `projects/13534454087919359824`)

3. **Screen lookup** (if Screen ID is not provided):
   - Call `[prefix]:list_screens` with the `projectId` (just the numeric ID, not the full path)
   - Review screen titles to identify the target screen (e.g., "Home", "Landing Page")
   - Extract the Screen ID from the screen's `name` field

4. **Metadata fetch**: 
   - Call `[prefix]:get_screen` with both `projectId` and `screenId` (both as numeric IDs only)
   - This returns the complete screen object including:
     - `screenshot.downloadUrl` - Visual reference of the design
     - `htmlCode.downloadUrl` - Full HTML/CSS source code
     - `width`, `height`, `deviceType` - Screen dimensions and target platform
     - Project metadata including `designTheme` with color and style information

5. **Asset download**:
   - Use `web_fetch` or `read_url_content` to download the HTML code from `htmlCode.downloadUrl`
   - Optionally download the screenshot from `screenshot.downloadUrl` for visual reference
   - Parse the HTML to extract Tailwind classes, custom CSS, and component patterns

6. **Project metadata extraction**:
   - Call `[prefix]:get_project` with the project `name` (full path: `projects/{id}`) to get:
     - `designTheme` object with color mode, fonts, roundness, custom colors
     - Project-level design guidelines and descriptions
     - Device type preferences and layout principles

## Analysis & Synthesis Instructions

### 1. Extract Project Identity (JSON)
- Locate the Project Title
- Locate the specific Project ID (e.g., from the `name` field in the JSON)

### 2. Define the Atmosphere (Image/HTML)
Evaluate the screenshot and HTML structure to capture the overall "vibe." Use evocative adjectives to describe the mood (e.g., "Airy," "Dense," "Minimalist," "Utilitarian").

### 3. Map the Color Palette (Tailwind Config/JSON)
Identify the key colors in the system. For each color, provide:
- A descriptive, natural language name that conveys its character (e.g., "Deep Muted Teal-Navy")
- The specific hex code in parentheses for precision (e.g., "#294056")
- Its specific functional role (e.g., "Used for primary actions")

### 4. Translate Geometry & Shape (CSS/Tailwind)
Convert technical `border-radius` and layout values into physical descriptions:
- Describe `rounded-full` as "Pill-shaped"
- Describe `rounded-lg` as "Subtly rounded corners"
- Describe `rounded-none` as "Sharp, squared-off edges"

### 5. Describe Depth & Elevation
Explain how the UI handles layers. Describe the presence and quality of shadows (e.g., "Flat," "Whisper-soft diffused shadows," or "Heavy, high-contrast drop shadows").

## Output Guidelines

- **Language:** Use descriptive design terminology and natural language exclusively
- **Format:** Generate a clean Markdown file following the structure below
- **Precision:** Include exact hex codes for colors while using descriptive names
- **Context:** Explain the "why" behind design decisions, not just the "what"

## Output Format (DESIGN.md Structure)

```markdown
# Design System: [Project Title]
**Project ID:** [Insert Project ID Here]

## 1. Visual Theme & Atmosphere
(Description of the mood, density, and aesthetic philosophy.)

## 2. Color Palette & Roles
(List colors by Descriptive Name + Hex Code + Functional Role.)

## 3. Typography Rules
(Description of font family, weight usage for headers vs. body, and letter-spacing character.)

## 4. Component Stylings
* **Buttons:** (Shape description, color assignment, behavior).
* **Cards/Containers:** (Corner roundness description, background color, shadow depth).
* **Inputs/Forms:** (Stroke style, background).

## 5. Layout Principles
(Description of whitespace strategy, margins, and grid alignment.)
```

## Usage Example

To use this skill for the Furniture Collection project:

1. **Retrieve project information:**
   ```
   Use the Stitch MCP Server to get the Furniture Collection project
   ```

2. **Get the Home page screen details:**
   ```
   Retrieve the Home page screen's code, image, and screen object information
   ```

3. **Reference best practices:**
   ```
   Review the Stitch Effective Prompting Guide at:
   https://stitch.withgoogle.com/docs/learn/prompting/
   ```

4. **Analyze and synthesize:**
   - Extract all relevant design tokens from the screen
   - Translate technical values into descriptive language
   - Organize information according to the DESIGN.md structure

5. **Generate the file:**
   - Create `DESIGN.md` in the project directory
   - Follow the prescribed format exactly
   - Ensure all color codes are accurate
   - Use evocative, designer-friendly language

## Best Practices

- **Be Descriptive:** Avoid generic terms like "blue" or "rounded." Use "Ocean-deep Cerulean (#0077B6)" or "Gently curved edges"
- **Be Functional:** Always explain what each design element is used for
- **Be Consistent:** Use the same terminology throughout the document
- **Be Visual:** Help readers visualize the design through your descriptions
- **Be Precise:** Include exact values (hex codes, pixel values) in parentheses after natural language descriptions

## Tips for Success

1. **Start with the big picture:** Understand the overall aesthetic before diving into details
2. **Look for patterns:** Identify consistent spacing, sizing, and styling patterns
3. **Think semantically:** Name colors by their purpose, not just their appearance
4. **Consider hierarchy:** Document how visual weight and importance are communicated
5. **Reference the guide:** Use language and patterns from the Stitch Effective Prompting Guide

## Common Pitfalls to Avoid

- ❌ Using technical jargon without translation (e.g., "rounded-xl" instead of "generously rounded corners")
- ❌ Omitting color codes or using only descriptive names
- ❌ Forgetting to explain functional roles of design elements
- ❌ Being too vague in atmosphere descriptions
- ❌ Ignoring subtle design details like shadows or spacing patterns

## Source: references/skills/ui-ux-pro-max/references/legacy/radix-ui-design-system/SKILL.md

---
name: radix-ui-design-system
description: "Build accessible design systems with Radix UI primitives. Headless component customization, theming strategies, and compound component patterns for production-grade UI libraries."
risk: safe
source: self
date_added: "2026-02-27"
---

# Radix UI Design System

Build production-ready, accessible design systems using Radix UI primitives with full customization control and zero style opinions.

## Overview

Radix UI provides unstyled, accessible components (primitives) that you can customize to match any design system. This skill guides you through building scalable component libraries with Radix UI, focusing on accessibility-first design, theming architecture, and composable patterns.

**Key Strengths:**
- **Headless by design**: Full styling control without fighting defaults
- **Accessibility built-in**: WAI-ARIA compliant, keyboard navigation, screen reader support
- **Composable primitives**: Build complex components from simple building blocks
- **Framework agnostic**: Works with React, but styles work anywhere

## When to Use This Skill

- Creating a custom design system from scratch
- Building accessible UI component libraries
- Implementing complex interactive components (Dialog, Dropdown, Tabs, etc.)
- Migrating from styled component libraries to unstyled primitives
- Setting up theming systems with CSS variables or Tailwind
- Need full control over component behavior and styling
- Building applications requiring WCAG 2.1 AA/AAA compliance

## Do not use this skill when

- You need pre-styled components out of the box (use shadcn/ui, Mantine, etc.)
- Building simple static pages without interactivity
- The project doesn't use React 16.8+ (Radix requires hooks)
- You need components for frameworks other than React

---

## Core Principles

### 1. Accessibility First

Every Radix primitive is built with accessibility as the foundation:

- **Keyboard Navigation**: Full keyboard support (Tab, Arrow keys, Enter, Escape)
- **Screen Readers**: Proper ARIA attributes and live regions
- **Focus Management**: Automatic focus trapping and restoration
- **Disabled States**: Proper handling of disabled and aria-disabled

**Rule**: Never override accessibility features. Enhance, don't replace.

### 2. Headless Architecture

Radix provides **behavior**, you provide **appearance**:

```tsx
// ❌ Don't fight pre-styled components
<Button className="override-everything" />

// ✅ Radix gives you behavior, you add styling
<Dialog.Root>
  <Dialog.Trigger className="your-button-styles" />
  <Dialog.Content className="your-modal-styles" />
</Dialog.Root>
```

### 3. Composition Over Configuration

Build complex components from simple primitives:

```tsx
// Primitive components compose naturally
<Tabs.Root>
  <Tabs.List>
    <Tabs.Trigger value="tab1">Tab 1</Tabs.Trigger>
    <Tabs.Trigger value="tab2">Tab 2</Tabs.Trigger>
  </Tabs.List>
  <Tabs.Content value="tab1">Content 1</Tabs.Content>
  <Tabs.Content value="tab2">Content 2</Tabs.Content>
</Tabs.Root>
```

---

## Getting Started

### Installation

```bash
# Install individual primitives (recommended)
npm install @radix-ui/react-dialog @radix-ui/react-dropdown-menu

# Or install multiple at once
npm install @radix-ui/react-{dialog,dropdown-menu,tabs,tooltip}

# For styling (optional but common)
npm install clsx tailwind-merge class-variance-authority
```

### Basic Component Pattern

Every Radix component follows this pattern:

```tsx
import * as Dialog from '@radix-ui/react-dialog';

export function MyDialog() {
  return (
    <Dialog.Root>
      {/* Trigger the dialog */}
      <Dialog.Trigger asChild>
        <button className="trigger-styles">Open</button>
      </Dialog.Trigger>

      {/* Portal renders outside DOM hierarchy */}
      <Dialog.Portal>
        {/* Overlay (backdrop) */}
        <Dialog.Overlay className="overlay-styles" />
        
        {/* Content (modal) */}
        <Dialog.Content className="content-styles">
          <Dialog.Title>Title</Dialog.Title>
          <Dialog.Description>Description</Dialog.Description>
          
          {/* Your content here */}
          
          <Dialog.Close asChild>
            <button>Close</button>
          </Dialog.Close>
        </Dialog.Content>
      </Dialog.Portal>
    </Dialog.Root>
  );
}
```

---

## Theming Strategies

### Strategy 1: CSS Variables (Framework-Agnostic)

**Best for**: Maximum portability, SSR-friendly

```css
/* globals.css */
:root {
  --color-primary: 220 90% 56%;
  --color-surface: 0 0% 100%;
  --radius-base: 0.5rem;
  --shadow-lg: 0 10px 15px -3px rgb(0 0 0 / 0.1);
}

[data-theme="dark"] {
  --color-primary: 220 90% 66%;
  --color-surface: 222 47% 11%;
}
```

```tsx
// Component.tsx
<Dialog.Content 
  className="
    bg-[hsl(var(--color-surface))]
    rounded-[var(--radius-base)]
    shadow-[var(--shadow-lg)]
  "
/>
```

### Strategy 2: Tailwind + CVA (Class Variance Authority)

**Best for**: Tailwind projects, variant-heavy components

```tsx
// button.tsx
import { cva, type VariantProps } from 'class-variance-authority';
import { cn } from '@/lib/utils';

const buttonVariants = cva(
  // Base styles
  "inline-flex items-center justify-center rounded-md font-medium transition-colors focus-visible:outline-none disabled:pointer-events-none disabled:opacity-50",
  {
    variants: {
      variant: {
        default: "bg-primary text-primary-foreground hover:bg-primary/90",
        destructive: "bg-destructive text-destructive-foreground hover:bg-destructive/90",
        outline: "border border-input bg-background hover:bg-accent",
        ghost: "hover:bg-accent hover:text-accent-foreground",
      },
      size: {
        default: "h-10 px-4 py-2",
        sm: "h-9 rounded-md px-3",
        lg: "h-11 rounded-md px-8",
        icon: "h-10 w-10",
      },
    },
    defaultVariants: {
      variant: "default",
      size: "default",
    },
  }
);

interface ButtonProps extends VariantProps<typeof buttonVariants> {
  children: React.ReactNode;
}

export function Button({ variant, size, children }: ButtonProps) {
  return (
    <button className={cn(buttonVariants({ variant, size }))}>
      {children}
    </button>
  );
}
```

### Strategy 3: Stitches (CSS-in-JS)

**Best for**: Runtime theming, scoped styles

```tsx
import { styled } from '@stitches/react';
import * as Dialog from '@radix-ui/react-dialog';

const StyledContent = styled(Dialog.Content, {
  backgroundColor: '$surface',
  borderRadius: '$md',
  padding: '$6',
  
  variants: {
    size: {
      small: { width: '300px' },
      medium: { width: '500px' },
      large: { width: '700px' },
    },
  },
  
  defaultVariants: {
    size: 'medium',
  },
});
```

---

## Component Patterns

### Pattern 1: Compound Components with Context

**Use case**: Share state between primitive parts

```tsx
// Select.tsx
import * as Select from '@radix-ui/react-select';
import { CheckIcon, ChevronDownIcon } from '@radix-ui/react-icons';

export function CustomSelect({ items, placeholder, onValueChange }) {
  return (
    <Select.Root onValueChange={onValueChange}>
      <Select.Trigger className="select-trigger">
        <Select.Value placeholder={placeholder} />
        <Select.Icon>
          <ChevronDownIcon />
        </Select.Icon>
      </Select.Trigger>

      <Select.Portal>
        <Select.Content className="select-content">
          <Select.Viewport>
            {items.map((item) => (
              <Select.Item 
                key={item.value} 
                value={item.value}
                className="select-item"
              >
                <Select.ItemText>{item.label}</Select.ItemText>
                <Select.ItemIndicator>
                  <CheckIcon />
                </Select.ItemIndicator>
              </Select.Item>
            ))}
          </Select.Viewport>
        </Select.Content>
      </Select.Portal>
    </Select.Root>
  );
}
```

### Pattern 2: Polymorphic Components with `asChild`

**Use case**: Render as different elements without losing behavior

```tsx
// ✅ Render as Next.js Link but keep Radix behavior
<Dialog.Trigger asChild>
  <Link href="/settings">Open Settings</Link>
</Dialog.Trigger>

// ✅ Render as custom component
<DropdownMenu.Item asChild>
  <YourCustomButton icon={<Icon />}>Action</YourCustomButton>
</DropdownMenu.Item>
```

**Why `asChild` matters**: Prevents nested button/link issues in accessibility tree.

### Pattern 3: Controlled vs Uncontrolled

```tsx
// Uncontrolled (Radix manages state)
<Tabs.Root defaultValue="tab1">
  <Tabs.Trigger value="tab1">Tab 1</Tabs.Trigger>
</Tabs.Root>

// Controlled (You manage state)
const [activeTab, setActiveTab] = useState('tab1');

<Tabs.Root value={activeTab} onValueChange={setActiveTab}>
  <Tabs.Trigger value="tab1">Tab 1</Tabs.Trigger>
</Tabs.Root>
```

**Rule**: Use controlled when you need to sync with external state (URL, Redux, etc.).

### Pattern 4: Animation with Framer Motion

```tsx
import * as Dialog from '@radix-ui/react-dialog';
import { motion, AnimatePresence } from 'framer-motion';

export function AnimatedDialog({ open, onOpenChange }) {
  return (
    <Dialog.Root open={open} onOpenChange={onOpenChange}>
      <Dialog.Portal forceMount>
        <AnimatePresence>
          {open && (
            <>
              <Dialog.Overlay asChild>
                <motion.div
                  initial={{ opacity: 0 }}
                  animate={{ opacity: 1 }}
                  exit={{ opacity: 0 }}
                  className="dialog-overlay"
                />
              </Dialog.Overlay>
              
              <Dialog.Content asChild>
                <motion.div
                  initial={{ opacity: 0, scale: 0.95 }}
                  animate={{ opacity: 1, scale: 1 }}
                  exit={{ opacity: 0, scale: 0.95 }}
                  className="dialog-content"
                >
                  {/* Content */}
                </motion.div>
              </Dialog.Content>
            </>
          )}
        </AnimatePresence>
      </Dialog.Portal>
    </Dialog.Root>
  );
}
```

---

## Common Primitives Reference

### Dialog (Modal)

```tsx
<Dialog.Root> {/* State container */}
  <Dialog.Trigger /> {/* Opens dialog */}
  <Dialog.Portal> {/* Renders in portal */}
    <Dialog.Overlay /> {/* Backdrop */}
    <Dialog.Content> {/* Modal content */}
      <Dialog.Title /> {/* Required for a11y */}
      <Dialog.Description /> {/* Required for a11y */}
      <Dialog.Close /> {/* Closes dialog */}
    </Dialog.Content>
  </Dialog.Portal>
</Dialog.Root>
```

### Dropdown Menu

```tsx
<DropdownMenu.Root>
  <DropdownMenu.Trigger />
  <DropdownMenu.Portal>
    <DropdownMenu.Content>
      <DropdownMenu.Item />
      <DropdownMenu.Separator />
      <DropdownMenu.CheckboxItem />
      <DropdownMenu.RadioGroup>
        <DropdownMenu.RadioItem />
      </DropdownMenu.RadioGroup>
      <DropdownMenu.Sub> {/* Nested menus */}
        <DropdownMenu.SubTrigger />
        <DropdownMenu.SubContent />
      </DropdownMenu.Sub>
    </DropdownMenu.Content>
  </DropdownMenu.Portal>
</DropdownMenu.Root>
```

### Tabs

```tsx
<Tabs.Root defaultValue="tab1">
  <Tabs.List>
    <Tabs.Trigger value="tab1" />
    <Tabs.Trigger value="tab2" />
  </Tabs.List>
  <Tabs.Content value="tab1" />
  <Tabs.Content value="tab2" />
</Tabs.Root>
```

### Tooltip

```tsx
<Tooltip.Provider delayDuration={200}>
  <Tooltip.Root>
    <Tooltip.Trigger />
    <Tooltip.Portal>
      <Tooltip.Content side="top" align="center">
        Tooltip text
        <Tooltip.Arrow />
      </Tooltip.Content>
    </Tooltip.Portal>
  </Tooltip.Root>
</Tooltip.Provider>
```

### Popover

```tsx
<Popover.Root>
  <Popover.Trigger />
  <Popover.Portal>
    <Popover.Content side="bottom" align="start">
      Content
      <Popover.Arrow />
      <Popover.Close />
    </Popover.Content>
  </Popover.Portal>
</Popover.Root>
```

---

## Accessibility Checklist

### Every Component Must Have:

- [ ] **Focus Management**: Visible focus indicators on all interactive elements
- [ ] **Keyboard Navigation**: Full keyboard support (Tab, Arrows, Enter, Esc)
- [ ] **ARIA Labels**: Meaningful labels for screen readers
- [ ] **Color Contrast**: WCAG AA minimum (4.5:1 for text, 3:1 for UI)
- [ ] **Error States**: Clear error messages with `aria-invalid` and `aria-describedby`
- [ ] **Loading States**: Proper `aria-busy` during async operations

### Dialog-Specific:
- [ ] `Dialog.Title` is present (required for screen readers)
- [ ] `Dialog.Description` provides context
- [ ] Focus trapped inside modal when open
- [ ] Escape key closes dialog
- [ ] Focus returns to trigger on close

### Dropdown-Specific:
- [ ] Arrow keys navigate items
- [ ] Type-ahead search works
- [ ] First/last item wrapping behavior
- [ ] Selected state indicated visually and with ARIA

---

## Best Practices

### ✅ Do This

1. **Always use `asChild` to avoid wrapper divs**
   ```tsx
   <Dialog.Trigger asChild>
     <button>Open</button>
   </Dialog.Trigger>
   ```

2. **Provide semantic HTML**
   ```tsx
   <Dialog.Content asChild>
     <article role="dialog" aria-labelledby="title">
       {/* content */}
     </article>
   </Dialog.Content>
   ```

3. **Use CSS variables for theming**
   ```css
   .dialog-content {
     background: hsl(var(--surface));
     color: hsl(var(--on-surface));
   }
   ```

4. **Compose primitives for complex components**
   ```tsx
   function CommandPalette() {
     return (
       <Dialog.Root>
         <Dialog.Content>
           <Combobox /> {/* Radix Combobox inside Dialog */}
         </Dialog.Content>
       </Dialog.Root>
     );
   }
   ```

### ❌ Don't Do This

1. **Don't skip accessibility parts**
   ```tsx
   // ❌ Missing Title and Description
   <Dialog.Content>
     <div>Content</div>
   </Dialog.Content>
   ```

2. **Don't fight the primitives**
   ```tsx
   // ❌ Overriding internal behavior
   <Dialog.Content onClick={(e) => e.stopPropagation()}>
   ```

3. **Don't mix controlled and uncontrolled**
   ```tsx
   // ❌ Inconsistent state management
   <Tabs.Root defaultValue="tab1" value={activeTab}>
   ```

4. **Don't ignore keyboard navigation**
   ```tsx
   // ❌ Disabling keyboard behavior
   <DropdownMenu.Item onKeyDown={(e) => e.preventDefault()}>
   ```

---

## Real-World Examples

### Example 1: Command Palette (Combo Dialog)

```tsx
import * as Dialog from '@radix-ui/react-dialog';
import { Command } from 'cmdk';

export function CommandPalette() {
  const [open, setOpen] = useState(false);

  useEffect(() => {
    const down = (e: KeyboardEvent) => {
      if (e.key === 'k' && (e.metaKey || e.ctrlKey)) {
        e.preventDefault();
        setOpen((open) => !open);
      }
    };
    document.addEventListener('keydown', down);
    return () => document.removeEventListener('keydown', down);
  }, []);

  return (
    <Dialog.Root open={open} onOpenChange={setOpen}>
      <Dialog.Portal>
        <Dialog.Overlay className="fixed inset-0 bg-black/50" />
        <Dialog.Content className="fixed left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2">
          <Command>
            <Command.Input placeholder="Type a command..." />
            <Command.List>
              <Command.Empty>No results found.</Command.Empty>
              <Command.Group heading="Suggestions">
                <Command.Item>Calendar</Command.Item>
                <Command.Item>Search Emoji</Command.Item>
              </Command.Group>
            </Command.List>
          </Command>
        </Dialog.Content>
      </Dialog.Portal>
    </Dialog.Root>
  );
}
```

### Example 2: Dropdown Menu with Icons

```tsx
import * as DropdownMenu from '@radix-ui/react-dropdown-menu';
import { DotsHorizontalIcon } from '@radix-ui/react-icons';

export function ActionsMenu() {
  return (
    <DropdownMenu.Root>
      <DropdownMenu.Trigger asChild>
        <button className="icon-button" aria-label="Actions">
          <DotsHorizontalIcon />
        </button>
      </DropdownMenu.Trigger>

      <DropdownMenu.Portal>
        <DropdownMenu.Content className="dropdown-content" align="end">
          <DropdownMenu.Item className="dropdown-item">
            Edit
          </DropdownMenu.Item>
          <DropdownMenu.Item className="dropdown-item">
            Duplicate
          </DropdownMenu.Item>
          <DropdownMenu.Separator className="dropdown-separator" />
          <DropdownMenu.Item className="dropdown-item text-red-500">
            Delete
          </DropdownMenu.Item>
        </DropdownMenu.Content>
      </DropdownMenu.Portal>
    </DropdownMenu.Root>
  );
}
```

### Example 3: Form with Radix Select + React Hook Form

```tsx
import * as Select from '@radix-ui/react-select';
import { useForm, Controller } from 'react-hook-form';

interface FormData {
  country: string;
}

export function CountryForm() {
  const { control, handleSubmit } = useForm<FormData>();

  return (
    <form onSubmit={handleSubmit((data) => console.log(data))}>
      <Controller
        name="country"
        control={control}
        render={({ field }) => (
          <Select.Root onValueChange={field.onChange} value={field.value}>
            <Select.Trigger className="select-trigger">
              <Select.Value placeholder="Select a country" />
              <Select.Icon />
            </Select.Trigger>
            
            <Select.Portal>
              <Select.Content className="select-content">
                <Select.Viewport>
                  <Select.Item value="us">United States</Select.Item>
                  <Select.Item value="ca">Canada</Select.Item>
                  <Select.Item value="uk">United Kingdom</Select.Item>
                </Select.Viewport>
              </Select.Content>
            </Select.Portal>
          </Select.Root>
        )}
      />
      <button type="submit">Submit</button>
    </form>
  );
}
```

---

## Troubleshooting

### Problem: Dialog doesn't close on Escape key

**Cause**: `onEscapeKeyDown` event prevented or `open` state not synced

**Solution**:
```tsx
<Dialog.Root open={open} onOpenChange={setOpen}>
  {/* Don't prevent default on escape */}
</Dialog.Root>
```

### Problem: Dropdown menu positioning is off

**Cause**: Parent container has `overflow: hidden` or transform

**Solution**:
```tsx
// Use Portal to render outside overflow container
<DropdownMenu.Portal>
  <DropdownMenu.Content />
</DropdownMenu.Portal>
```

### Problem: Animations don't work

**Cause**: Portal content unmounts immediately

**Solution**:
```tsx
// Use forceMount + AnimatePresence
<Dialog.Portal forceMount>
  <AnimatePresence>
    {open && <Dialog.Content />}
  </AnimatePresence>
</Dialog.Portal>
```

### Problem: TypeScript errors with `asChild`

**Cause**: Type inference issues with polymorphic components

**Solution**:
```tsx
// Explicitly type your component
<Dialog.Trigger asChild>
  <button type="button">Open</button>
</Dialog.Trigger>
```

---

## Performance Optimization

### 1. Code Splitting

```tsx
// Lazy load heavy primitives
const Dialog = lazy(() => import('@radix-ui/react-dialog'));
const DropdownMenu = lazy(() => import('@radix-ui/react-dropdown-menu'));
```

### 2. Portal Container Reuse

```tsx
// Create portal container once
<Tooltip.Provider>
  {/* All tooltips share portal container */}
  <Tooltip.Root>...</Tooltip.Root>
  <Tooltip.Root>...</Tooltip.Root>
</Tooltip.Provider>
```

### 3. Memoization

```tsx
// Memoize expensive render functions
const SelectItems = memo(({ items }) => (
  items.map((item) => <Select.Item key={item.value} value={item.value} />)
));
```

---

## Integration with Popular Tools

### shadcn/ui (Built on Radix)

shadcn/ui is a collection of copy-paste components built with Radix + Tailwind.

```bash
npx shadcn-ui@latest init
npx shadcn-ui@latest add dialog
```

**When to use shadcn vs raw Radix**:
- Use shadcn: Quick prototyping, standard designs
- Use raw Radix: Full customization, unique designs

### Radix Themes (Official Styled System)

```tsx
import { Theme, Button, Dialog } from '@radix-ui/themes';

function App() {
  return (
    <Theme accentColor="crimson" grayColor="sand">
      <Button>Click me</Button>
    </Theme>
  );
}
```

---

## Related Skills

- `@tailwind-design-system` - Tailwind + Radix integration patterns
- `@react-patterns` - React composition patterns
- `@frontend-design` - Overall frontend architecture
- `@accessibility-compliance` - WCAG compliance testing

---

## Resources

### Official Documentation
- [Radix UI Docs](https://www.radix-ui.com/primitives)
- [Radix Colors](https://www.radix-ui.com/colors) - Accessible color system
- [Radix Icons](https://www.radix-ui.com/icons) - Icon library

### Community Resources
- [shadcn/ui](https://ui.shadcn.com) - Component collection
- [Radix UI Discord](https://discord.com/invite/7Xb99uG) - Community support
- [CVA Documentation](https://cva.style/docs) - Variant management

### Examples
- [Radix Playground](https://www.radix-ui.com/primitives/docs/overview/introduction#try-it-out)
- [shadcn/ui Source](https://github.com/shadcn-ui/ui) - Production examples

---

## Quick Reference

### Installation
```bash
npm install @radix-ui/react-{primitive-name}
```

### Basic Pattern
```tsx
<Primitive.Root>
  <Primitive.Trigger />
  <Primitive.Portal>
    <Primitive.Content />
  </Primitive.Portal>
</Primitive.Root>
```

### Key Props
- `asChild` - Render as child element
- `defaultValue` - Uncontrolled default
- `value` / `onValueChange` - Controlled state
- `open` / `onOpenChange` - Open state
- `side` / `align` - Positioning

---

**Remember**: Radix gives you **behavior**, you give it **beauty**. Accessibility is built-in, customization is unlimited.

## Source: references/skills/ui-ux-pro-max/references/legacy/tailwind-design-system/SKILL.md

---
name: tailwind-design-system
description: "Build scalable design systems with Tailwind CSS, design tokens, component libraries, and responsive patterns. Use when creating component libraries, implementing design systems, or standardizing UI..."
risk: unknown
source: community
date_added: "2026-02-27"
---

# Tailwind Design System

Build production-ready design systems with Tailwind CSS, including design tokens, component variants, responsive patterns, and accessibility.

## Use this skill when

- Creating a component library with Tailwind
- Implementing design tokens and theming
- Building responsive and accessible components
- Standardizing UI patterns across a codebase
- Migrating to or extending Tailwind CSS
- Setting up dark mode and color schemes

## Do not use this skill when

- The task is unrelated to tailwind design system
- You need a different domain or tool outside this scope

## Instructions

- Clarify goals, constraints, and required inputs.
- Apply relevant best practices and validate outcomes.
- Provide actionable steps and verification.
- If detailed examples are required, open `resources/implementation-playbook.md`.

## Resources

- `resources/implementation-playbook.md` for detailed patterns and examples.

## Source: references/skills/ui-ux-pro-max/references/legacy/ui-skills/SKILL.md

---
name: ui-skills
description: "Opinionated, evolving constraints to guide agents when building interfaces"
risk: safe
source: "https://github.com/ibelick/ui-skills"
date_added: "2026-02-27"
---

# Ui Skills

## Overview

Opinionated, evolving constraints to guide agents when building interfaces

## When to Use This Skill

Use this skill when you need to work with opinionated, evolving constraints to guide agents when building interfaces.

## Instructions

This skill provides guidance and patterns for opinionated, evolving constraints to guide agents when building interfaces.

For more information, see the [source repository](https://github.com/ibelick/ui-skills).

## Source: references/skills/ui-ux-pro-max/references/legacy/ui-ux-pro-max-skill-main/SKILL.md

---
name: ui-ux-pro-max
description: "UI/UX design intelligence. 50 styles, 21 palettes, 50 font pairings, 20 charts, 9 stacks (React, Next.js, Vue, Svelte, SwiftUI, React Native, Flutter, Tailwind, shadcn/ui). Actions: plan, build, create, design, implement, review, fix, improve, optimize, enhance, refactor, check UI/UX code. Projects: website, landing page, dashboard, admin panel, e-commerce, SaaS, portfolio, blog, mobile app, .html, .tsx, .vue, .svelte. Elements: button, modal, navbar, sidebar, card, table, form, chart. Styles: glassmorphism, claymorphism, minimalism, brutalism, neumorphism, bento grid, dark mode, responsive, skeuomorphism, flat design. Topics: color palette, accessibility, animation, layout, typography, font pairing, spacing, hover, shadow, gradient. Integrations: shadcn/ui MCP for component search and examples."
---

# UI/UX Pro Max - Design Intelligence

Comprehensive design guide for web and mobile applications. Contains 50+ styles, 97 color palettes, 57 font pairings, 99 UX guidelines, and 25 chart types across 9 technology stacks. Searchable database with priority-based recommendations.

## When to Apply

Reference these guidelines when:
- Designing new UI components or pages
- Choosing color palettes and typography
- Reviewing code for UX issues
- Building landing pages or dashboards
- Implementing accessibility requirements

## Rule Categories by Priority

| Priority | Category | Impact | Domain |
|----------|----------|--------|--------|
| 1 | Accessibility | CRITICAL | `ux` |
| 2 | Touch & Interaction | CRITICAL | `ux` |
| 3 | Performance | HIGH | `ux` |
| 4 | Layout & Responsive | HIGH | `ux` |
| 5 | Typography & Color | MEDIUM | `typography`, `color` |
| 6 | Animation | MEDIUM | `ux` |
| 7 | Style Selection | MEDIUM | `style`, `product` |
| 8 | Charts & Data | LOW | `chart` |

## Quick Reference

### 1. Accessibility (CRITICAL)

- `color-contrast` - Minimum 4.5:1 ratio for normal text
- `focus-states` - Visible focus rings on interactive elements
- `alt-text` - Descriptive alt text for meaningful images
- `aria-labels` - aria-label for icon-only buttons
- `keyboard-nav` - Tab order matches visual order
- `form-labels` - Use label with for attribute

### 2. Touch & Interaction (CRITICAL)

- `touch-target-size` - Minimum 44x44px touch targets
- `hover-vs-tap` - Use click/tap for primary interactions
- `loading-buttons` - Disable button during async operations
- `error-feedback` - Clear error messages near problem
- `cursor-pointer` - Add cursor-pointer to clickable elements

### 3. Performance (HIGH)

- `image-optimization` - Use WebP, srcset, lazy loading
- `reduced-motion` - Check prefers-reduced-motion
- `content-jumping` - Reserve space for async content

### 4. Layout & Responsive (HIGH)

- `viewport-meta` - width=device-width initial-scale=1
- `readable-font-size` - Minimum 16px body text on mobile
- `horizontal-scroll` - Ensure content fits viewport width
- `z-index-management` - Define z-index scale (10, 20, 30, 50)

### 5. Typography & Color (MEDIUM)

- `line-height` - Use 1.5-1.75 for body text
- `line-length` - Limit to 65-75 characters per line
- `font-pairing` - Match heading/body font personalities

### 6. Animation (MEDIUM)

- `duration-timing` - Use 150-300ms for micro-interactions
- `transform-performance` - Use transform/opacity, not width/height
- `loading-states` - Skeleton screens or spinners

### 7. Style Selection (MEDIUM)

- `style-match` - Match style to product type
- `consistency` - Use same style across all pages
- `no-emoji-icons` - Use SVG icons, not emojis

### 8. Charts & Data (LOW)

- `chart-type` - Match chart type to data type
- `color-guidance` - Use accessible color palettes
- `data-table` - Provide table alternative for accessibility

## How to Use

Search specific domains using the CLI tool below.

---

## Prerequisites

Check if Python is installed:

```bash
python3 --version || python --version
```

If Python is not installed, install it based on user's OS:

**macOS:**
```bash
brew install python3
```

**Ubuntu/Debian:**
```bash
sudo apt update && sudo apt install python3
```

**Windows:**
```powershell
winget install Python.Python.3.12
```

---

## How to Use This Skill

When user requests UI/UX work (design, build, create, implement, review, fix, improve), follow this workflow:

### Step 1: Analyze User Requirements

Extract key information from user request:
- **Product type**: SaaS, e-commerce, portfolio, dashboard, landing page, etc.
- **Style keywords**: minimal, playful, professional, elegant, dark mode, etc.
- **Industry**: healthcare, fintech, gaming, education, etc.
- **Stack**: React, Vue, Next.js, or default to `html-tailwind`

### Step 2: Generate Design System (REQUIRED)

**Always start with `--design-system`** to get comprehensive recommendations with reasoning:

```bash
python3 skills/ui-ux-pro-max/scripts/search.py "<product_type> <industry> <keywords>" --design-system [-p "Project Name"]
```

This command:
1. Searches 5 domains in parallel (product, style, color, landing, typography)
2. Applies reasoning rules from `ui-reasoning.csv` to select best matches
3. Returns complete design system: pattern, style, colors, typography, effects
4. Includes anti-patterns to avoid

**Example:**
```bash
python3 skills/ui-ux-pro-max/scripts/search.py "beauty spa wellness service" --design-system -p "Serenity Spa"
```

### Step 2b: Persist Design System (Master + Overrides Pattern)

To save the design system for **hierarchical retrieval across sessions**, add `--persist`:

```bash
python3 skills/ui-ux-pro-max/scripts/search.py "<query>" --design-system --persist -p "Project Name"
```

This creates:
- `design-system/MASTER.md` — Global Source of Truth with all design rules
- `design-system/pages/` — Folder for page-specific overrides

**With page-specific override:**
```bash
python3 skills/ui-ux-pro-max/scripts/search.py "<query>" --design-system --persist -p "Project Name" --page "dashboard"
```

This also creates:
- `design-system/pages/dashboard.md` — Page-specific deviations from Master

**How hierarchical retrieval works:**
1. When building a specific page (e.g., "Checkout"), first check `design-system/pages/checkout.md`
2. If the page file exists, its rules **override** the Master file
3. If not, use `design-system/MASTER.md` exclusively

**Context-aware retrieval prompt:**
```
I am building the [Page Name] page. Please read design-system/MASTER.md.
Also check if design-system/pages/[page-name].md exists.
If the page file exists, prioritize its rules.
If not, use the Master rules exclusively.
Now, generate the code...
```

### Step 3: Supplement with Detailed Searches (as needed)

After getting the design system, use domain searches to get additional details:

```bash
python3 skills/ui-ux-pro-max/scripts/search.py "<keyword>" --domain <domain> [-n <max_results>]
```

**When to use detailed searches:**

| Need | Domain | Example |
|------|--------|---------|
| More style options | `style` | `--domain style "glassmorphism dark"` |
| Chart recommendations | `chart` | `--domain chart "real-time dashboard"` |
| UX best practices | `ux` | `--domain ux "animation accessibility"` |
| Alternative fonts | `typography` | `--domain typography "elegant luxury"` |
| Landing structure | `landing` | `--domain landing "hero social-proof"` |

### Step 4: Stack Guidelines (Default: html-tailwind)

Get implementation-specific best practices. If user doesn't specify a stack, **default to `html-tailwind`**.

```bash
python3 skills/ui-ux-pro-max/scripts/search.py "<keyword>" --stack html-tailwind
```

Available stacks: `html-tailwind`, `react`, `nextjs`, `vue`, `svelte`, `swiftui`, `react-native`, `flutter`, `shadcn`, `jetpack-compose`

---

## Search Reference

### Available Domains

| Domain | Use For | Example Keywords |
|--------|---------|------------------|
| `product` | Product type recommendations | SaaS, e-commerce, portfolio, healthcare, beauty, service |
| `style` | UI styles, colors, effects | glassmorphism, minimalism, dark mode, brutalism |
| `typography` | Font pairings, Google Fonts | elegant, playful, professional, modern |
| `color` | Color palettes by product type | saas, ecommerce, healthcare, beauty, fintech, service |
| `landing` | Page structure, CTA strategies | hero, hero-centric, testimonial, pricing, social-proof |
| `chart` | Chart types, library recommendations | trend, comparison, timeline, funnel, pie |
| `ux` | Best practices, anti-patterns | animation, accessibility, z-index, loading |
| `react` | React/Next.js performance | waterfall, bundle, suspense, memo, rerender, cache |
| `web` | Web interface guidelines | aria, focus, keyboard, semantic, virtualize |
| `prompt` | AI prompts, CSS keywords | (style name) |

### Available Stacks

| Stack | Focus |
|-------|-------|
| `html-tailwind` | Tailwind utilities, responsive, a11y (DEFAULT) |
| `react` | State, hooks, performance, patterns |
| `nextjs` | SSR, routing, images, API routes |
| `vue` | Composition API, Pinia, Vue Router |
| `svelte` | Runes, stores, SvelteKit |
| `swiftui` | Views, State, Navigation, Animation |
| `react-native` | Components, Navigation, Lists |
| `flutter` | Widgets, State, Layout, Theming |
| `shadcn` | shadcn/ui components, theming, forms, patterns |
| `jetpack-compose` | Composables, Modifiers, State Hoisting, Recomposition |

---

## Example Workflow

**User request:** "Làm landing page cho dịch vụ chăm sóc da chuyên nghiệp"

### Step 1: Analyze Requirements
- Product type: Beauty/Spa service
- Style keywords: elegant, professional, soft
- Industry: Beauty/Wellness
- Stack: html-tailwind (default)

### Step 2: Generate Design System (REQUIRED)

```bash
python3 skills/ui-ux-pro-max/scripts/search.py "beauty spa wellness service elegant" --design-system -p "Serenity Spa"
```

**Output:** Complete design system with pattern, style, colors, typography, effects, and anti-patterns.

### Step 3: Supplement with Detailed Searches (as needed)

```bash
# Get UX guidelines for animation and accessibility
python3 skills/ui-ux-pro-max/scripts/search.py "animation accessibility" --domain ux

# Get alternative typography options if needed
python3 skills/ui-ux-pro-max/scripts/search.py "elegant luxury serif" --domain typography
```

### Step 4: Stack Guidelines

```bash
python3 skills/ui-ux-pro-max/scripts/search.py "layout responsive form" --stack html-tailwind
```

**Then:** Synthesize design system + detailed searches and implement the design.

---

## Output Formats

The `--design-system` flag supports two output formats:

```bash
# ASCII box (default) - best for terminal display
python3 skills/ui-ux-pro-max/scripts/search.py "fintech crypto" --design-system

# Markdown - best for documentation
python3 skills/ui-ux-pro-max/scripts/search.py "fintech crypto" --design-system -f markdown
```

---

## Tips for Better Results

1. **Be specific with keywords** - "healthcare SaaS dashboard" > "app"
2. **Search multiple times** - Different keywords reveal different insights
3. **Combine domains** - Style + Typography + Color = Complete design system
4. **Always check UX** - Search "animation", "z-index", "accessibility" for common issues
5. **Use stack flag** - Get implementation-specific best practices
6. **Iterate** - If first search doesn't match, try different keywords

---

## Common Rules for Professional UI

These are frequently overlooked issues that make UI look unprofessional:

### Icons & Visual Elements

| Rule | Do | Don't |
|------|----|----- |
| **No emoji icons** | Use SVG icons (Heroicons, Lucide, Simple Icons) | Use emojis like 🎨 🚀 ⚙️ as UI icons |
| **Stable hover states** | Use color/opacity transitions on hover | Use scale transforms that shift layout |
| **Correct brand logos** | Research official SVG from Simple Icons | Guess or use incorrect logo paths |
| **Consistent icon sizing** | Use fixed viewBox (24x24) with w-6 h-6 | Mix different icon sizes randomly |

### Interaction & Cursor

| Rule | Do | Don't |
|------|----|----- |
| **Cursor pointer** | Add `cursor-pointer` to all clickable/hoverable cards | Leave default cursor on interactive elements |
| **Hover feedback** | Provide visual feedback (color, shadow, border) | No indication element is interactive |
| **Smooth transitions** | Use `transition-colors duration-200` | Instant state changes or too slow (>500ms) |

### Light/Dark Mode Contrast

| Rule | Do | Don't |
|------|----|----- |
| **Glass card light mode** | Use `bg-white/80` or higher opacity | Use `bg-white/10` (too transparent) |
| **Text contrast light** | Use `#0F172A` (slate-900) for text | Use `#94A3B8` (slate-400) for body text |
| **Muted text light** | Use `#475569` (slate-600) minimum | Use gray-400 or lighter |
| **Border visibility** | Use `border-gray-200` in light mode | Use `border-white/10` (invisible) |

### Layout & Spacing

| Rule | Do | Don't |
|------|----|----- |
| **Floating navbar** | Add `top-4 left-4 right-4` spacing | Stick navbar to `top-0 left-0 right-0` |
| **Content padding** | Account for fixed navbar height | Let content hide behind fixed elements |
| **Consistent max-width** | Use same `max-w-6xl` or `max-w-7xl` | Mix different container widths |

---

## Pre-Delivery Checklist

Before delivering UI code, verify these items:

### Visual Quality
- [ ] No emojis used as icons (use SVG instead)
- [ ] All icons from consistent icon set (Heroicons/Lucide)
- [ ] Brand logos are correct (verified from Simple Icons)
- [ ] Hover states don't cause layout shift
- [ ] Use theme colors directly (bg-primary) not var() wrapper

### Interaction
- [ ] All clickable elements have `cursor-pointer`
- [ ] Hover states provide clear visual feedback
- [ ] Transitions are smooth (150-300ms)
- [ ] Focus states visible for keyboard navigation

### Light/Dark Mode
- [ ] Light mode text has sufficient contrast (4.5:1 minimum)
- [ ] Glass/transparent elements visible in light mode
- [ ] Borders visible in both modes
- [ ] Test both modes before delivery

### Layout
- [ ] Floating elements have proper spacing from edges
- [ ] No content hidden behind fixed navbars
- [ ] Responsive at 375px, 768px, 1024px, 1440px
- [ ] No horizontal scroll on mobile

### Accessibility
- [ ] All images have alt text
- [ ] Form inputs have labels
- [ ] Color is not the only indicator
- [ ] `prefers-reduced-motion` respected

