# HOWTOFRAMEWORK.COM - TEMPLATE REFERENCE
## Source of Truth for All Page Components
**Last Updated:** January 10, 2026
**Source File:** index.html (SHA: 24213aae3d433c10a0d291e4087eccbfa074aa56)

---

## ⚠️ CRITICAL: READ BEFORE EDITING ANY PAGE

When editing ANY page on howtoframework.com:
1. **DO NOT reconstruct header/footer from memory**
2. **COPY the exact HTML from this reference**
3. **Only modify page-specific content (title, meta, body)**

This prevents the "fix one thing, break another" pattern.

---

## 🚨 INFRASTRUCTURE THAT MUST NEVER BE DELETED

These elements are REQUIRED on every single page. If you're updating a page and these are missing, ADD THEM. If they exist, DO NOT REMOVE THEM.

### Google Analytics (REQUIRED - DO NOT DELETE)
```html
<!-- Google Analytics - REQUIRED ON EVERY PAGE -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-TXBXZ335ZR"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-TXBXZ335ZR');
</script>
```
**GA Property ID:** G-TXBXZ335ZR
**Why it matters:** Without this, we have ZERO visibility into site traffic. This is how we know if the money engine is working.

### Google Site Verification (REQUIRED - DO NOT DELETE)
```html
<meta name="google-site-verification" content="lLcSYm1T_e7bvoNuLK89qkB7t0-fj_nLDA3_FKvJcrc" />
```
**Why it matters:** Required for Search Console access. Deleting this breaks our SEO monitoring.

### Social Sharing Images (REQUIRED - DO NOT DELETE)
```html
<meta property="og:image" content="https://app.ragedesigner.com/wp-content/uploads/2025/11/strategic-thinking-academy-ragedesigner.png">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:image" content="https://app.ragedesigner.com/wp-content/uploads/2025/11/strategic-thinking-academy-ragedesigner.png">
```
**Why it matters:** Without these, social shares look unprofessional - no image, just text.

---

## 🎨 CSS VARIABLES (Required in every page)

```css
:root {
    --charcoal-blue: #1A2332;
    --logo-blue: #325d74;
    --orange: #E67E50;
    --primary: #E67E50;
    --white: #ffffff;
    --light-gray: #f5f5f5;
    --text-dark: #2d2d2d;
    --text-medium: #5a5a5a;
}
```

**Note:** howtoframework uses both `--orange` and `--primary` pointing to the same color (#E67E50) for compatibility.

---

## 📋 COMPLETE HEAD SECTION TEMPLATE

Every page MUST include ALL of these in `<head>`:

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[PAGE TITLE] | Strategic Thinking Academy</title>
    <meta name="description" content="[PAGE DESCRIPTION]">
    
    <!-- Google Site Verification - DO NOT DELETE -->
    <meta name="google-site-verification" content="lLcSYm1T_e7bvoNuLK89qkB7t0-fj_nLDA3_FKvJcrc" />
    
    <!-- Social Sharing - DO NOT DELETE -->
    <meta property="og:title" content="[PAGE TITLE]">
    <meta property="og:description" content="[PAGE DESCRIPTION]">
    <meta property="og:image" content="https://app.ragedesigner.com/wp-content/uploads/2025/11/strategic-thinking-academy-ragedesigner.png">
    <meta property="og:url" content="https://howtoframework.com/[PAGE-SLUG]">
    <meta property="og:type" content="website">
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:image" content="https://app.ragedesigner.com/wp-content/uploads/2025/11/strategic-thinking-academy-ragedesigner.png">
    
    <!-- Favicon -->
    <link rel="icon" type="image/png" href="https://app.ragedesigner.com/wp-content/uploads/2025/11/whatisaframework.png">
    
    <!-- Google Analytics - DO NOT DELETE -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-TXBXZ335ZR"></script>
    <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());
      gtag('config', 'G-TXBXZ335ZR');
    </script>
    
    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;600;700&display=swap" rel="stylesheet">
    
    <style>
        /* CSS goes here */
    </style>
</head>
```

**Default OG Image:** `https://app.ragedesigner.com/wp-content/uploads/2025/11/strategic-thinking-academy-ragedesigner.png`
**Google Analytics ID:** G-TXBXZ335ZR

---

## 🔝 CANONICAL HEADER (Desktop + Mobile)

### Header HTML Structure
```html
<nav id="main-header">
    <a href="/" class="logo-link"><img src="https://app.ragedesigner.com/wp-content/uploads/2025/11/sta-icon-1.png" alt="Strategic Thinking Academy" class="logo-icon"></a>
    <div class="nav-links desktop-nav">
        <a href="#curriculum">Curriculum</a>
        <a href="#pricing">Pricing</a>
        <a href="https://whatisaframework.com/interactive-lab.html">Interactive Lab</a>
        <a href="https://whatisaframework.com">What is a Framework?</a>
        <a href="#pricing" class="nav-cta">Get Started</a>
    </div>
    <button class="mobile-menu-toggle" aria-label="Toggle menu">
        <span class="hamburger-line"></span>
        <span class="hamburger-line"></span>
        <span class="hamburger-line"></span>
    </button>
</nav>

<div class="mobile-nav-drawer">
    <button class="mobile-nav-close" aria-label="Close menu">×</button>
    <nav class="mobile-nav">
        <a href="#curriculum" class="mobile-nav-link">Curriculum</a>
        <a href="#pricing" class="mobile-nav-link">Pricing</a>
        <a href="https://whatisaframework.com/interactive-lab.html" class="mobile-nav-link">Interactive Lab</a>
        <a href="https://whatisaframework.com" class="mobile-nav-link">What is a Framework?</a>
        <a href="#pricing" class="mobile-nav-cta">Get Started</a>
    </nav>
</div>
<div class="mobile-nav-overlay"></div>
```

### Header CSS (Required)
```css
nav#main-header { background: var(--white); padding: 16px 50px; border-bottom: 1px solid var(--light-gray); position: fixed; top: 0; left: 0; right: 0; z-index: 1000; box-shadow: 0 2px 8px rgba(0,0,0,0.04); display: flex; justify-content: space-between; align-items: center; transition: all 0.3s ease; }
nav#main-header.scrolled { padding: 12px 50px; box-shadow: 0 2px 20px rgba(26, 35, 50, 0.08); }
.logo-link { display: flex; align-items: center; text-decoration: none; }
.logo-icon { height: 48px; width: auto; transition: height 0.3s ease; }
nav#main-header.scrolled .logo-icon { height: 40px; }
.nav-links { display: flex; align-items: center; gap: 32px; }
.nav-links a:not(.nav-cta) { color: var(--text-medium); text-decoration: none; font-weight: 500; transition: color 0.2s; font-size: 16px; }
.nav-links a:not(.nav-cta):hover { color: var(--orange); }
.nav-cta { background: var(--orange); color: var(--white) !important; padding: 10px 24px; border-radius: 8px; font-weight: 600; transition: all 0.2s; text-decoration: none; border: 2px solid var(--orange); }
.nav-cta:hover { background: transparent; color: var(--orange) !important; transform: translateY(-1px); }
.mobile-menu-toggle { display: none; flex-direction: column; gap: 6px; background: none; border: none; padding: 8px; cursor: pointer; }
.hamburger-line { width: 28px; height: 3px; background: var(--charcoal-blue); border-radius: 2px; transition: all 0.3s ease; }
.mobile-menu-toggle:hover .hamburger-line { background: var(--orange); }
.mobile-menu-toggle.active .hamburger-line:nth-child(1) { transform: rotate(45deg) translateY(9px); }
.mobile-menu-toggle.active .hamburger-line:nth-child(2) { opacity: 0; }
.mobile-menu-toggle.active .hamburger-line:nth-child(3) { transform: rotate(-45deg) translateY(-9px); }
.mobile-nav-drawer { position: fixed; top: 0; right: -100%; width: 300px; height: 100vh; background: var(--charcoal-blue); padding: 48px 40px; transition: right 0.4s ease; z-index: 1002; }
.mobile-nav-drawer.active { right: 0; }
.mobile-nav-close { position: absolute; top: 16px; right: 16px; background: var(--orange); color: white; border: none; width: 40px; height: 40px; border-radius: 50%; font-size: 28px; cursor: pointer; transition: transform 0.3s ease; }
.mobile-nav-close:hover { transform: rotate(90deg); }
.mobile-nav { display: flex; flex-direction: column; gap: 16px; margin-top: 48px; }
.mobile-nav-link { color: white; text-decoration: none; font-size: 18px; font-weight: 500; padding: 16px; border-bottom: 1px solid rgba(255, 255, 255, 0.1); transition: all 0.3s ease; position: relative; }
.mobile-nav-link::before { content: ''; position: absolute; left: 0; top: 0; height: 100%; width: 4px; background: var(--orange); transform: translateX(-4px); transition: transform 0.3s ease; }
.mobile-nav-link:hover { padding-left: 24px; color: var(--orange); }
.mobile-nav-link:hover::before { transform: translateX(0); }
.mobile-nav-cta { margin-top: 24px; background: var(--orange); color: white !important; padding: 16px 24px; border-radius: 8px; text-align: center; font-weight: 600; text-decoration: none; transition: all 0.3s ease; border: 2px solid var(--orange); }
.mobile-nav-cta:hover { background: transparent; transform: translateY(-2px); }
.mobile-nav-overlay { position: fixed; top: 0; left: 0; right: 0; bottom: 0; background: rgba(26, 35, 50, 0.8); opacity: 0; visibility: hidden; transition: all 0.3s ease; z-index: 1001; }
.mobile-nav-overlay.active { opacity: 1; visibility: visible; }

@media (max-width: 768px) {
    body { padding-top: 70px; }
    nav#main-header { padding: 16px 24px; }
    nav#main-header.scrolled { padding: 12px 24px; }
    .logo-icon { height: 40px; }
    .nav-links.desktop-nav { display: none; }
    .mobile-menu-toggle { display: flex; }
}
```

---

## 🔻 CANONICAL FOOTER

### Footer HTML Structure
```html
<footer>
    <img src="https://app.ragedesigner.com/wp-content/uploads/2025/11/strategic-thinking-academy-ragedesigner.png" alt="Strategic Thinking Academy" class="footer-logo">
    <div class="ai-badge">🤖 This site is built and managed autonomously by AI</div>
    <div class="footer-links">
        <a href="https://whatisaframework.com">What is a Framework?</a> | 
        <a href="/ai.html">AI Reference</a>
    </div>
    <p>Built by <a href="https://ragedesigner.com">RageDesigner</a> | © 2026</p>
</footer>
```

### Footer CSS (Required)
```css
footer { padding: 56px 24px 32px; background: #0f151d; color: var(--white); text-align: center; }
.footer-logo { max-width: 300px; height: auto; margin: 0 auto 32px; display: block; }
footer p { opacity: 0.7; font-size: 14px; line-height: 1.8; color: var(--white); }
footer a { color: var(--primary); text-decoration: none; }
.footer-links { margin-bottom: 16px; }
.footer-links a { color: var(--white); margin: 0 16px; transition: color 0.3s ease; }
.footer-links a:hover { color: var(--primary); }
.ai-badge { display: inline-block; background: rgba(230, 126, 80, 0.15); border: 1px solid var(--orange); padding: 10px 20px; border-radius: 24px; font-size: 12px; margin-bottom: 20px; color: var(--primary); }

@media (max-width: 768px) {
    .footer-logo { max-width: 240px; }
}
```

### ⚠️ CRITICAL FOOTER NOTES:
- **Footer text color:** `var(--white)` (#ffffff)
- **RageDesigner link color:** `var(--primary)` (#E67E50 orange)
- **Footer background:** `#0f151d` (darker than charcoal-blue)
- **Footer links:** White text, hover to orange
- **Copyright year:** 2026 (update annually)

---

## 📜 MOBILE MENU JAVASCRIPT (Required)

```javascript
(function() {
    const header = document.getElementById('main-header');
    window.addEventListener('scroll', function() {
        if (window.pageYOffset > 50) { header.classList.add('scrolled'); }
        else { header.classList.remove('scrolled'); }
    });
    const mobileToggle = document.querySelector('.mobile-menu-toggle');
    const mobileDrawer = document.querySelector('.mobile-nav-drawer');
    const mobileOverlay = document.querySelector('.mobile-nav-overlay');
    const mobileClose = document.querySelector('.mobile-nav-close');
    function openMobileMenu() {
        mobileToggle.classList.add('active');
        mobileDrawer.classList.add('active');
        mobileOverlay.classList.add('active');
        document.body.style.overflow = 'hidden';
    }
    function closeMobileMenu() {
        mobileToggle.classList.remove('active');
        mobileDrawer.classList.remove('active');
        mobileOverlay.classList.remove('active');
        document.body.style.overflow = '';
    }
    if (mobileToggle) {
        mobileToggle.addEventListener('click', function() {
            if (mobileDrawer.classList.contains('active')) { closeMobileMenu(); }
            else { openMobileMenu(); }
        });
    }
    if (mobileClose) { mobileClose.addEventListener('click', closeMobileMenu); }
    if (mobileOverlay) { mobileOverlay.addEventListener('click', closeMobileMenu); }
    document.addEventListener('keydown', function(e) {
        if (e.key === 'Escape' && mobileDrawer && mobileDrawer.classList.contains('active')) {
            closeMobileMenu();
        }
    });
    document.querySelectorAll('.mobile-nav-link, .mobile-nav-cta').forEach(function(link) {
        link.addEventListener('click', closeMobileMenu);
    });
})();
```

---

## ✅ CHECKLIST: Before Deploying Any Page

### 🚨 INFRASTRUCTURE (Non-negotiable)
- [ ] Google Analytics code present (G-TXBXZ335ZR)
- [ ] Google site verification tag present
- [ ] og:image meta tag present
- [ ] twitter:image meta tag present

### Structure
- [ ] CSS variables include all required values
- [ ] Header HTML matches this reference exactly
- [ ] Footer HTML matches this reference exactly
- [ ] Footer text is WHITE (`var(--white)`)
- [ ] RageDesigner link is ORANGE (`var(--primary)`)
- [ ] Mobile menu JS included
- [ ] Logo URL: `https://app.ragedesigner.com/wp-content/uploads/2025/11/sta-icon-1.png`
- [ ] Copyright year is 2026

---

## 🚫 KNOWN BAD PATTERNS (Do Not Use)

### ❌ Missing Google Analytics (CRITICAL):
```html
<!-- BAD - page is invisible to analytics -->
<head>
    <title>Page Title</title>
    <!-- NO GA CODE = we can't track anything -->
</head>
```
**Impact:** Zero visibility into whether the money engine is working. Fix immediately.

### ❌ Missing og:image:
```html
<!-- BAD - no social sharing image -->
<head>
    <title>Page Title</title>
    <!-- missing og:image - causes ugly social shares -->
</head>
```

### ❌ Wrong Contact URL:
```html
<!-- BAD - missing app. prefix -->
<a href="https://ragedesigner.com/contact">Contact</a>

<!-- GOOD - correct URL -->
<a href="https://app.ragedesigner.com/contact">Contact</a>
```

### ❌ Wrong Footer (causes invisible text):
```css
/* BAD - footer p color inherits charcoal-blue */
footer p { color: var(--charcoal-blue); }
```

---

## 📁 FILE LOCATIONS

- **Logo (Header):** `https://app.ragedesigner.com/wp-content/uploads/2025/11/sta-icon-1.png`
- **Logo (Footer):** `https://app.ragedesigner.com/wp-content/uploads/2025/11/strategic-thinking-academy-ragedesigner.png`
- **Default OG Image:** `https://app.ragedesigner.com/wp-content/uploads/2025/11/strategic-thinking-academy-ragedesigner.png`
- **Favicon:** `https://app.ragedesigner.com/wp-content/uploads/2025/11/whatisaframework.png`

---

## 🔗 CROSS-SITE LINKS

This site links to:
- whatisaframework.com (What is a Framework?)
- whatisaframework.com/interactive-lab.html (Interactive Lab)
- ragedesigner.com (Built by attribution)
- app.ragedesigner.com/contact (Contact forms)

---

## 🔄 VERSION HISTORY

| Date | Change | Source |
|------|--------|--------|
| 2026-01-10 | Initial template reference created | index.html SHA: 24213aae |
| 2026-01-10 | Added prominent GA/infrastructure section to prevent deletion | Template update |

---

## ⚠️ KNOWN ISSUES TO FIX

1. **Missing og:image tags** - Need to add to index.html and all other pages
2. **Copyright year** - Footer shows 2025, should be 2026
3. **Contact CTAs** - Currently mailto, should link to app.ragedesigner.com/contact

---

*This is the source of truth. When in doubt, copy from here.*
