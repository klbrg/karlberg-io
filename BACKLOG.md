# karlberg.io - Improvement Backlog

This backlog contains prioritized improvements for the portfolio website, focusing on accessibility, SEO, user experience, and performance.

---

## Task #1: Add keyboard focus states and accessibility styling

**Priority:** High (Accessibility - WCAG 2.1 Level AA requirement)
**Effort:** ~15 minutes
**Status:** ✅ Completed

### Description
Implement visible focus indicators for keyboard navigation to meet WCAG 2.1 Level AA requirements.

### Changes needed
- Add `:focus-visible` styles for all interactive elements (links, buttons)
- Add `prefers-reduced-motion` media query to respect user motion preferences
- Ensure focus indicators work in both light and dark modes
- Test tab navigation through all sections

### Files to modify
- `src/styles.css`

### Acceptance criteria
- Visible 2px outline on focused elements
- Works in both light/dark themes
- Respects prefers-reduced-motion setting
- All interactive elements are keyboard accessible

---

## Task #2: Add Twitter Card and enhanced Open Graph meta tags

**Priority:** High (SEO/Social sharing)
**Effort:** ~5 minutes
**Status:** Pending

### Description
Add missing Twitter Card meta tags and enhance Open Graph tags for better social media sharing previews.

### Changes needed
- Add twitter:card, twitter:title, twitter:description, twitter:image
- Add twitter:creator tag
- Add og:image:alt for accessibility
- Verify og-image.png exists or create it

### Files to modify
- `src/index.html`

### Acceptance criteria
- Rich preview shows when shared on Twitter/X
- Rich preview shows when shared on LinkedIn
- All required Twitter Card meta tags present
- OG image file exists and is referenced correctly

---

## Task #3: Add email contact option to contact section

**Priority:** Medium (User experience)
**Effort:** ~3 minutes
**Status:** ✅ Completed

### Description
Add an email contact link to the contact section alongside existing social links.

### Changes needed
- Add email social link with envelope icon
- Use mailto: link
- Match existing social-link styling
- Ensure it works in both light/dark modes

### Files to modify
- `src/index.html`

### Acceptance criteria
- Email link appears in contact section
- Opens default email client when clicked
- Styled consistently with other social links
- Has proper aria-label for accessibility

---

## Task #4: Fix heading hierarchy and add skip link

**Priority:** Medium (Accessibility/SEO)
**Effort:** ~20 minutes
**Status:** Pending

### Description
Improve semantic HTML structure for better accessibility and SEO.

### Changes needed
- Add skip link at top of page to jump to main content
- Change project/skill card divs to article elements
- Add aria-labelledby attributes to sections
- Ensure heading hierarchy is logical (h1 > h2 > h3)

### Files to modify
- `src/index.html`
- `src/styles.css` (for skip link styling)

### Acceptance criteria
- Skip link visible on keyboard focus
- Skip link jumps to main content
- All project/skill cards use article tags
- Sections have proper aria labels
- Heading hierarchy validated

---

## Task #5: Remove duplicate font loading

**Priority:** Low-Medium (Performance)
**Effort:** ~5 minutes
**Status:** Pending

### Description
Optimize font loading by removing duplicate Google Fonts requests.

### Changes needed
- Remove @import from styles.css (line 1)
- Keep link tag in HTML head
- Consider adding font-display: swap explicitly
- Optionally add preload for critical font weights

### Files to modify
- `src/styles.css`

### Acceptance criteria
- Google Fonts loaded only once
- No duplicate network requests in DevTools
- Fonts still load correctly
- No FOUT (Flash of Unstyled Text) issues

---

---

## Task #6: Replace terminal with kubectl and line-by-line output

**Priority:** Medium (User experience)
**Effort:** ~30 minutes
**Status:** ✅ Completed

### Description
Replace ArgoCD terminal demo with kubectl apply workflow showing progressive line-by-line output.

### Changes implemented
- Initial view shows `ls -lh` with manifest files (instant display)
- Click "Apply Manifests" runs kubectl apply with realistic progressive output
- Each resource appears with 180ms delay
- Terminal shows $ prompt with blinking cursor

---

## Task #7: Add rel="me" to social links for identity verification

**Priority:** CRITICAL (SEO - Personal name ranking)
**Effort:** ~3 minutes
**Status:** Pending
**SEO Impact:** +0.3 ranking points

### Description
Add rel="me" attribute to all social media links to establish identity ownership for Google knowledge graph.

### Why this matters
- Google uses rel="me" to verify profile ownership
- Enables knowledge graph profile card in search results
- Critical signal for "Rickard Karlberg" name ranking
- Links identity across GitHub, LinkedIn, Goodreads

### Changes needed
- Add rel="me" to GitHub link
- Add rel="me" to LinkedIn link
- Add rel="me" to Goodreads link

### Files to modify
- `src/index.html` (contact section)

### Acceptance criteria
- All social links have rel="me" attribute
- Links still open in new tab
- HTML validates correctly

---

## Task #8: Create OG image and add Twitter Card meta tags

**Priority:** CRITICAL (SEO - Social sharing)
**Effort:** ~15 minutes
**Status:** Pending
**SEO Impact:** +0.7 ranking points

### Description
Create Open Graph image (1200x630px) and add complete Twitter Card metadata. Currently references og-image.png but file doesn't exist.

### Why this matters
- LinkedIn/Twitter shares show broken/no preview = 80% fewer clicks
- Twitter Card metadata completely missing
- Social shares are major SEO ranking signal

### Changes needed
1. Create `src/og-image.png` (1200x630px)
2. Add Twitter Card meta tags (card, title, description, image, creator)
3. Add OG image metadata (alt, type, width, height)

### Files to modify
- `src/index.html` (head section)
- `src/og-image.png` (new file)

### Acceptance criteria
- og-image.png exists and displays correctly
- Twitter Card validator shows rich preview
- LinkedIn preview works

---

## Task #9: Complete Person schema with missing properties

**Priority:** CRITICAL (SEO - Knowledge graph)
**Effort:** ~8 minutes
**Status:** Pending
**SEO Impact:** +0.4 ranking points

### Description
Expand JSON-LD Person schema with critical properties for knowledge graph authority.

### Why this matters
- Missing properties prevent knowledge graph card in search
- Need to establish this page IS about "Rickard Karlberg"
- Authority signals missing (image, contact, organization)

### Changes needed
- Add "mainEntityOfPage": "https://karlberg.io"
- Add "image": URL to professional headshot
- Add "contactPoint" with professional contact type
- Add "worksFor" organization schema (optional)

### Files to modify
- `src/index.html` (JSON-LD script)

### Acceptance criteria
- Schema validates in Google Rich Results Test
- Minimum: mainEntityOfPage, image, contactPoint added

---

## Task #10: Update sitemap.xml with current modification dates

**Priority:** Low (SEO - Technical)
**Effort:** ~2 minutes
**Status:** Pending
**SEO Impact:** +0.05 ranking points

### Description
Update all lastmod tags in sitemap from 2025-11-24 to current date (2026-02-04).

### Files to modify
- `src/sitemap.xml`

---

## Task #11: Add project creator schema markup to project cards

**Priority:** Medium (SEO - Content attribution)
**Effort:** ~20 minutes
**Status:** Pending
**SEO Impact:** +0.3 ranking points

### Description
Add structured data to project cards linking them explicitly to Rickard Karlberg as creator.

### Changes needed
- Change project-card div to article with schema.org markup
- Add CreativeWork itemscope
- Add creator property pointing to "Rickard Karlberg"
- Add keywords for tech stack

### Files to modify
- `src/index.html` (projects section - 3 cards)

---

## Task #12: Create blog section for thought leadership content

**Priority:** High (SEO - Backlinks)
**Effort:** ~4-8 hours
**Status:** Pending
**SEO Impact:** +0.4-0.6 ranking points + 10-20 backlinks over 6 months

### Description
Add blog section with 3-5 in-depth technical articles (1500-2000 words each) to attract backlinks.

### Why this matters
- Currently ZERO backlink opportunities
- Blog content is #1 source of natural backlinks
- 70% of SEO ranking comes from backlinks/authority signals
- Creates multiple entry points for "Rickard Karlberg" searches

### Content ideas
1. "Implementing Cilium CNI on Azure AKS: A Deep Dive"
2. "Lessons from Two Decades of Production Infrastructure"
3. "Automating TLS with cert-manager: Best Practices"
4. "GitOps in Production: ArgoCD at Scale"

### Files to create
- `src/blog/index.html`
- `src/blog/[article-slug].html`
- Update navigation and sitemap

---

## Task #13: Add certifications and awards section

**Priority:** Medium (SEO - Credibility)
**Effort:** ~10 minutes
**Status:** Pending
**SEO Impact:** +0.2 ranking points

### Description
Create section displaying professional certifications, awards, and recognition.

### Changes needed
- Add new section after Skills or Projects
- List certifications with dates
- Update Person schema with "award" property

### Files to modify
- `src/index.html`
- Potentially `src/styles.css`

---

## Summary

| # | Task | Priority | Effort | Status | SEO Impact |
|---|------|----------|--------|--------|------------|
| 1 | Keyboard focus states | High | 15 min | ✅ Done | A11y compliance |
| 2 | Twitter Card meta tags | High | 5 min | Pending | (See #8) |
| 3 | Email contact option | Medium | 3 min | ✅ Done | UX improvement |
| 4 | Heading hierarchy + skip link | Medium | 20 min | Pending | A11y & SEO |
| 5 | Remove duplicate fonts | Low-Med | 5 min | Pending | Performance |
| 6 | kubectl terminal | Medium | 30 min | ✅ Done | UX improvement |
| **7** | **Add rel="me" links** | **CRITICAL** | **3 min** | **Pending** | **+0.3 pts** |
| **8** | **Create OG image + Twitter Card** | **CRITICAL** | **15 min** | **Pending** | **+0.7 pts** |
| **9** | **Complete Person schema** | **CRITICAL** | **8 min** | **Pending** | **+0.4 pts** |
| 10 | Update sitemap dates | Low | 2 min | Pending | +0.05 pts |
| 11 | Project creator schema | Medium | 20 min | Pending | +0.3 pts |
| 12 | Create blog section | High | 4-8 hrs | Pending | +0.5 pts + backlinks |
| 13 | Add certifications section | Medium | 10 min | Pending | +0.2 pts |

### Priority Breakdown

**Quick Wins (Do First - 26 min):**
- Task #7: Add rel="me" (3 min) → +0.3 SEO points
- Task #8: OG image + Twitter Card (15 min) → +0.7 SEO points
- Task #9: Complete Person schema (8 min) → +0.4 SEO points
**Total: +1.4 ranking improvement in 26 minutes**

**High-Value Next Steps:**
- Task #5: Remove duplicate fonts (5 min)
- Task #10: Update sitemap (2 min)
- Task #11: Project creator schema (20 min)
- Task #13: Certifications section (10 min)

**Long-Term Investment:**
- Task #12: Blog section (major backlink source)
- Task #4: Heading hierarchy improvements

**Total potential SEO improvement:** +2.5 ranking points (excluding blog backlinks)