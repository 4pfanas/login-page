<div align="center">

# Login Page

### A dark, glassmorphism sign-in screen in a single HTML file.

Ambient glowing background, frosted-glass card, and polished form states. Front end only.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![Dependencies](https://img.shields.io/badge/dependencies-none-2f8f79)
![Status](https://img.shields.io/badge/status-UI_mockup-orange)

</div>

**Live demo:** https://4pfanas.github.io/login-page/


---

## Table of contents

1. [The idea](#the-idea)
2. [What it includes](#what-it-includes)
3. [How it works](#how-it-works)
4. [Design tokens](#design-tokens)
5. [Tech stack](#tech-stack)
6. [Project structure](#project-structure)
7. [Run it locally](#run-it-locally)
8. [Wiring it to a real backend](#wiring-it-to-a-real-backend)
9. [Limitations](#limitations)
10. [Roadmap](#roadmap)

---

## The idea

The sign-in screen is the first thing many users see, and it sets the tone for the whole product. This project is a reusable, self-contained login page: dark, modern, and calm, with the frosted-glass look that is popular in current dashboards and SaaS apps.

It is intentionally **a UI mockup**. There is no authentication logic, so it can be dropped in front of any backend, or used as a design reference.

## What it includes

- **Email and password fields** with proper `autocomplete` hints so password managers work.
- **"Remember me"** checkbox and a **"Forgot password?"** link.
- A prominent **Sign In** button.
- **"Or continue with"** divider with **Google** and **GitHub** buttons, using inline brand SVGs.
- A **"Don't have an account? Sign up"** footer link.
- A shield-and-tick **brand icon** drawn in inline SVG.
- Ambient **blurred colour blobs** and a **vignette** behind the card for depth.
- Hover, focus and placeholder styling on inputs and buttons.

## How it works

There is **no JavaScript**. The whole page is HTML and CSS.

- The `<form>` uses `onsubmit="return false;"` so pressing Sign In doesn't reload the page, which makes it safe to click around during a demo.
- The background is three absolutely positioned `div.blob` elements with heavy blur and a soft colour, layered under a `div.vignette` that darkens the edges.
- The card is a translucent panel (`rgba(255,255,255,0.04)`) with a thin translucent border and a large corner radius. A `backdrop-filter` blur on that panel produces the frosted-glass look.
- Focus and hover states are handled purely with CSS pseudo-classes (`:focus`, `:hover`), so keyboard users get clear feedback too.
- Icons for the brand mark, Google and GitHub are inline SVG, so the page needs no image files and stays a single request.

## Design tokens

Declared once as CSS custom properties, so re-theming is a small edit:

| Token | Value | Use |
|---|---|---|
| `--bg` | `#0D0D0D` | Page background |
| `--text` | `#F2F2F2` | Primary text |
| `--accent` | `#6C63FF` | Buttons and highlights (violet) |
| `--blue` | `#4A9EFF` | Secondary glow |
| `--glass` | `rgba(255,255,255,0.04)` | Card fill |
| `--border` | `rgba(255,255,255,0.07)` | Card and input outline |
| `--r` | `20px` | Corner radius |

## Tech stack

| Layer | Choice |
|---|---|
| Markup | HTML5, semantic form with labels tied to inputs |
| Styling | CSS3: custom properties, `backdrop-filter`, gradients, pseudo-classes |
| Icons | Inline SVG |
| Type | Inter (Google Fonts) |

## Project structure

```text
login-page/
├── index.html   # markup and styles
└── README.md
```

## Run it locally

```bash
git clone https://github.com/4pfanas/login-page.git
cd login-page
open index.html
```

## Wiring it to a real backend

The page is a front-end shell. To make it real:

1. Replace `onsubmit="return false;"` with a handler that sends the email and password to your API over HTTPS.
2. Never store the password client-side. Use a secure, HTTP-only session cookie or a token from your auth provider.
3. Point the Google and GitHub buttons at your OAuth flow (for example Auth.js, Supabase Auth, or Firebase Auth).
4. Add validation and error messages for wrong credentials, empty fields and rate limiting.

## Limitations

- **No real authentication.** Any input is accepted and nothing is sent anywhere.
- The social buttons are visual only.
- No error, loading or success states yet.

## Roadmap

- [ ] Inline validation and error messages
- [ ] Loading state on the Sign In button
- [ ] "Sign up" and "Forgot password" screens in the same style
- [ ] Show/hide password toggle
- [ ] Light theme
- [ ] Accessibility pass: contrast audit and screen-reader labels on social buttons

---

<div align="center">

Built by **[Anas Aslam](https://github.com/4pfanas)**

</div>
