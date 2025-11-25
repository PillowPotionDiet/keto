# Upsell/Downsell Page Modifications Guide

This document contains all the CSS modifications to be applied to upsell and downsell pages for consistent styling across desktop and mobile versions.

## Table of Contents
1. [White Space Removal](#white-space-removal)
2. [Step Images Sizing](#step-images-sizing)
3. [Order Confirmed Image (Upsell Only)](#order-confirmed-image-upsell1-only)
4. [Notification Swiper Mobile Modifications](#notification-swiper-mobile-modifications)

---

## 1. White Space Removal

### For Upsell (Has Order Confirmed Image)
Add this CSS in the `<style>` section, BEFORE the mobile adjustments section:

```css
/* Order Confirmed image - reduce top and bottom spacing */
.order_confirmed {
  margin-top: 0;
  margin-bottom: 0;
  display: block;
}
```

### For Upsell2, Upsell3...UpsellN and Downsell (No Order Confirmed Image)
Add this CSS in the `<style>` section, BEFORE the mobile adjustments section:

```css
/* Remove white space between top banner and step image */
.bonus-bg {
  margin-top: 0;
  padding-top: 0;
}

.step-container {
  margin-top: 0;
  padding-top: 0;
}
```

---

## 2. Step Images Sizing

### Mobile Version (320px)
Add this CSS INSIDE the existing mobile adjustments section `@media (max-width: 600px) { ... }`:

```css
/* Step image mobile styles */
.step-image {
  max-width: 320px;
  height: auto;
  margin-top: 0;
  display: block;
  margin-left: auto;
  margin-right: auto;
}
```

**Location:** Add this after the `.top-banner span:not(.caution-icon)` block, but BEFORE the closing `}` of the media query.

---

## 3. Order Confirmed Image (Upsell Only)

### Mobile Version (180px, no bottom space)
Add this CSS INSIDE the existing mobile adjustments section `@media (max-width: 600px) { ... }`:

```css
/* Order Confirmed image mobile styles */
.order_confirmed {
  max-width: 180px;
  /* reduced size */
  height: auto;
  margin-bottom: 0;
  /* remove bottom space */
  display: block;
  margin-left: auto;
  margin-right: auto;
}
```

**Location:** Add this after the `.top-banner span:not(.caution-icon)` block, but BEFORE the `.step-image` block.

---

## 4. Notification Swiper Mobile Modifications

### Mobile Version Adjustments
REPLACE the existing notification swiper mobile code with this:

**Find this code:**
```css
/* For mobile devices, increase bottom spacing */
@media (max-width: 600px) {
    .pn-container {
        bottom: 100px; /* increased from 20px */
    }
}
```

**Replace with:**
```css
/* For mobile devices, increase bottom spacing */
@media (max-width: 600px) {
      .pn-container {
        bottom: 20px;
        /* reduced bottom spacing */
      }

      .pn-card {
        margin-bottom: -10px;
      }
    }
```

---

## Complete Example for Upsell

```css
/* Order Confirmed image - reduce top and bottom spacing */
.order_confirmed {
  margin-top: 0;
  margin-bottom: 0;
  display: block;
}

/* MOBILE ADJUSTMENTS */
@media (max-width: 600px) {
  .top-banner {
    flex-direction: column;
    text-align: center;
    font-size: 14px;
    padding: 6px 5px;
    gap: 4px;
  }

  .caution-icon {
    display: block;
    margin-bottom: 4px;
  }

  .top-banner span:not(.caution-icon) {
    display: inline;
  }

  /* Order Confirmed image mobile styles */
  .order_confirmed {
    max-width: 180px;
    /* reduced size */
    height: auto;
    margin-bottom: 0;
    /* remove bottom space */
    display: block;
    margin-left: auto;
    margin-right: auto;
  }

  /* Step image mobile styles */
  .step-image {
    max-width: 320px;
    height: auto;
    margin-top: 0;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
}
```

---

## Complete Example for Upsell2/UpsellN/Downsell

```css
/* Remove white space between top banner and step image */
.bonus-bg {
  margin-top: 0;
  padding-top: 0;
}

.step-container {
  margin-top: 0;
  padding-top: 0;
}

/* MOBILE ADJUSTMENTS */
@media (max-width: 600px) {
  .top-banner {
    flex-direction: column;
    text-align: center;
    font-size: 14px;
    padding: 6px 5px;
    gap: 4px;
  }

  .caution-icon {
    display: block;
    margin-bottom: 4px;
  }

  .top-banner span:not(.caution-icon) {
    display: inline;
  }

  /* Step image mobile styles */
  .step-image {
    max-width: 320px;
    height: auto;
    margin-top: 0;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
}
```

---

## Notification Swiper Section

Find the notification swiper styles section (usually near the bottom of the file) and update the mobile code:

```css
/* For mobile devices, increase bottom spacing */
@media (max-width: 600px) {
      .pn-container {
        bottom: 20px;
        /* reduced bottom spacing */
      }

      .pn-card {
        margin-bottom: -10px;
      }
    }
```

---

## Summary of Changes

### All Upsell/Downsell Pages:
- ✅ White space removed between Product Qty banner and images
- ✅ Step images: 320px on mobile, centered, no top margin
- ✅ Notification swiper: bottom 20px, card margin-bottom -10px on mobile

### Upsell Only:
- ✅ Order Confirmed image: 180px on mobile, no bottom space
- ✅ Order Confirmed image: no top/bottom margins on desktop

### Upsell2/UpsellN/Downsell:
- ✅ bonus-bg and step-container: no top margins/padding

---

## Quick Reference Command

When starting a new project, provide this instruction:

> "Apply all modifications from UPSELL_DOWNSELL_MODIFICATIONS.md file to all upsell and downsell pages. Use Upsell template for pages with Order Confirmed image, and Upsell2/Downsell template for pages without Order Confirmed image."

---

**Version:** 1.0
**Last Updated:** October 31, 2025
**Project:** Keto DTC
