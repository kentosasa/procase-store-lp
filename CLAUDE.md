# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Japanese landing page (LP) for **PROCASE STORE** - a 3D printed custom board game piece manufacturing service. The project is a static single-page website targeting indie board game creators (同人ボードゲーム作家) who need small-batch custom game pieces (100+ pieces minimum).

**Key Business Model:**
- Design fee: ¥5,000 (3D modeling from images)
- Single-color pieces: ¥50/piece
- Two-color pieces: ¥100/piece
- Minimum order: 100 pieces
- 9 available PLA colors (white, black, red, yellow, green, light blue, orange, beige, brown)
- Free design revisions (up to 2 times)
- Shipping via Yamato Transport (ヤマト運輸)

## Architecture

**Static HTML/CSS Landing Page:**
- `index.html` - Single-page LP with inline JavaScript for smooth scrolling and sticky CTA
- `style.css` - All styling including hero gradient, color palette, pricing tables, and responsive design
- `img/` - Product images and hero background
- `ogp-image.png`, `apple-touch-icon.png`, `favicon.ico` - SEO/social media assets

**LP Structure (in order):**
1. Hero section with purple gradient background (`hero-bg.png`)
2. Problem/pain points section with clickable anchor links to solutions
3. 5 reasons to choose PROCASE (with `id` anchors: `#reason-1` through `#reason-4`, plus `#pricing`, `#flow`)
4. Portfolio/case studies section
5. Pricing section with detailed examples
6. Production flow (8-step process)
7. Contact section with Google Forms CTAs
8. Fixed bottom CTA buttons (single-color & two-color plans)

**Key Interactive Features:**
- Smooth scrolling to section anchors
- Problem items in section 2 are clickable `<a>` tags that scroll to corresponding solution sections
- Fixed CTA buttons at bottom that disappear when user reaches contact section
- Hover effects on CTA buttons (text scales 1.15x)
- Hover effects on problem items (translateY, box-shadow, border-left)

## Design System

**Color Palette:**
- Primary purple gradient: `#667eea` → `#764ba2`
- Hero CTA button: White background `#fff` with purple text `#667eea` (for visibility against gradient)
- Fixed CTA buttons: Semi-transparent backgrounds
- 9 product colors defined in CSS (`.color-circle.white`, `.black`, `.red`, `.yellow`, `.green`, `.lightblue`, `.orange`, `.beige`, `.brown`)

**Typography:**
- Japanese sans-serif stack: `'Helvetica Neue', 'Arial', 'Hiragino Kaku Gothic ProN', 'Hiragino Sans', 'Meiryo', sans-serif`
- H2: 2.5rem, centered
- H3: 1.8rem
- Body: 1rem, line-height 1.8

**Responsive Design:**
- Max container width: 1200px
- Mobile breakpoints implemented with media queries
- Images use standard `<img>` tags with lazy loading attribute

## Content Management

**Reference Documents:**
- `claude_boss_role.md` - Defines the project management approach (auto-execute tasks until A+ production quality)
- `lp_detailed_copy.md` - Complete Japanese copywriting for all LP sections (source of truth for content)

**Important Content Rules:**
1. All text must be in Japanese
2. Color count is now **9 colors** (updated from 8) - always use "9色" not "8色"
3. Delivery method is specifically **ヤマト運輸** (Yamato Transport) - do not mention tracking numbers
4. Design revisions are "2回まで無料" (up to 2 times free)
5. Minimum order is 100 pieces, additional orders in 50-piece increments
6. Never use emojis unless explicitly requested by user

## Git Workflow

**Commit Message Style:**
- Japanese commit messages with descriptive titles
- Include bullet points for multiple changes
- Always add Claude Code attribution footer:
  ```
  🤖 Generated with [Claude Code](https://claude.com/claude-code)

  Co-Authored-By: Claude <noreply@anthropic.com>
  ```

**Branch:** `master` (main branch)

## Quality Standards (from claude_boss_role.md)

The project aims for **A+ production quality**, meaning:
- Production-ready for business deployment
- SEO-optimized structure (meta tags, OGP, JSON-LD schema)
- Compelling, user-engaging LP design
- High conversion focus with clear CTAs

## Image Generation

When images need to be created (e.g., OGP, favicons), use Python with Pillow:
- OGP images: 1200x630px
- Favicon: 32x32px ICO format
- Apple touch icon: 180x180px PNG
- Default design: Dark purple gradient matching hero section

## Special Notes

1. **File Path Encoding:** Repository path contains Japanese characters (`オーダーメイド/lp制作 駒`). Always use absolute paths.

2. **Clickable Problem Section:** Section 2 problem items are `<a href="#reason-X">` tags that navigate to solutions. Maintain this interactive pattern when editing.

3. **White CTA Button:** The hero section CTA button uses white background specifically for visibility against the dark purple gradient - this is intentional design.

4. **Fixed CTA Logic:** The fixed bottom CTA buttons use JavaScript to hide when user scrolls to `#contact` section. Do not modify this behavior without user approval.

5. **Color Count:** As of the latest commit, the service offers **9 colors** (brown was recently added). Update all references from "8色" to "9色" when editing.

6. **Shipping Info:** Delivery is via ヤマト運輸. Do not mention tracking numbers per user request.
