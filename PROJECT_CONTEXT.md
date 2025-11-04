Tebelo NPC (Brand & Build Guide)

0) Purpose

This file is the single source of truth for Tebelo's brand style and build rules inside Cursor.

Use it for:

Rebuilding tebelo.org (structure, voice, components).

Generating HTML emailers (mobile-first, widely compatible).

Keeping tone, visuals, and UX consistent for corporate sponsors, private donors, and local communities.

Source of truth: Review content and imagery on https://tebelo.org/

 before generating or editing pages or emailers.

1) Brand essence

Who we are: Tebelo Community Development NPC—helping communities thrive through Health, Nutrition, and Education, plus on-the-ground projects like the Matter Innovation Hub and Tebelo Lighthouse.

Audience: Corporate CSI/CSR teams, private donors, community partners, volunteers, and local residents."

Voice: Clear, human, hopeful, grounded in real impact. Avoid jargon and hype. Prefer active voice, short sentences, and concrete outcomes.

Tone examples

Do: "Your support helps 30 learners start coding this term."

Don't: "We leverage disruptive innovation to unlock synergies."

2) Visual system

2.1 Logo

Pull the current logo from tebelo.org and keep aspect ratio.

Minimum size on web: 24px height (header), 40px+ in footers/hero areas.

Clear space: at least the height of the "T" around the mark.

2.2 Color

Rule: First, auto-derive palette from tebelo.org to stay aligned.

If you are coding generation steps, have the AI:

Inspect the live site and its images,

Propose a primary, secondary, accent, neutral, and success/notice palette with hex values,

Keep contrast AA/AAA compliant.

Fallback palette (use only if extraction isn't possible right now):

--brand-primary: a confident deep blue or teal suitable for trust and health

--brand-secondary: a warm highlight color that pairs with the primary (e.g., soft orange/coral)

--brand-accent: a bright, optimistic accent (limited use for CTAs/tags)

--neutral-900..100: grayscale ramp for text/background/dividers

--success: green tone for confirmations/badges

Maintain WCAG AA contrast for body (≥4.5:1) and large type (≥3:1).

When you finalize exact hex codes from the site, write them into /styles/tokens.css and update components.

2.3 Typography

Web: Use a clean, legible sans-serif stack (e.g., system-ui, -apple-system, Segoe UI, Roboto, Inter, Arial, sans-serif).

Email: Use web-safe fonts (e.g., Arial, Helvetica, sans-serif).

Hierarchy:

H1 36–44, bold, tight leading

H2 28–34, semibold

H3 22–26, semibold

Body 16–18, regular

Caption/Meta 12–14

2.4 Icons & imagery

Icons: Simple, outline or duotone that matches brand stroke weight.

Photos: Real people, real places (Lighthouse, classrooms, hubs, gardens). Avoid stocky clichés. Show dignity and agency.

3) Content & voice rules

Lead with impact, then how, then call to action.

Always include a specific outcome where possible: learners trained, meals served, teachers certified, etc.

Avoid internal acronyms unless explained.

Keep paragraphs short (2–4 sentences).

Buttons use verbs: "Donate", "Sponsor a Hub", "Get Involved".

Microcopy examples

Donate page sub-text: "Every Rand helps a learner start."

Volunteer CTA: "Offer your time or skills."

4) Accessibility & UX

Color contrast AA minimum; link focus visible.

Alt text for all images; meaningful link text ("Read the Lighthouse story"), never "Click here".

Form labels and error states must be explicit.

Tap targets ≥44px.

Reduce motion preference respected.

5) Website structure (vibecoding guide)

Top-level nav (suggested)

Our Work (Health, Nutrition, Education, Matter Innovation Hub, Lighthouse, Training Centre)

Get Involved (Donate, Partner with Us, Volunteer)

Tebelo News

About (Our Team, Partners)

Contact

Home page sections (suggested order)

Hero: Short mission + single primary CTA (e.g., "Donate" or "Partner with us").

Three pillars: Health / Nutrition / Education (each with 1-line impact + deep link).

Featured projects: Lighthouse, Matter Innovation Hub, Food Systems, Training Centre (cards with image, 2-line blurb, CTA).

Impact stats/testimonials: Real numbers, short quotes.

Get involved: Donate, Partner, Volunteer (3 cards).

Latest news: 3–4 items.

Footer: Contacts, address, social links, NPO details, quick links.

Components

Header (sticky, simple)

Hero (image/video + clear headline + single CTA)

Section heading + kicker

Card list (3- or 4-up, responsive)

Testimonial block

Stat badges (count-up optional)

CTA band (full-width, high contrast)

Footer with sitemap + donation CTA

Tech notes

Mobile-first CSS, 12-column fluid grid, container widths at 640/768/1024/1280+.

Prefer semantic HTML, minimal libraries, fast LCP.

Images next-gen (webp/avif), lazy-load below the fold.

6) HTML emailers (production rules)

Max width 600px; centered; background #ffffff or very light neutral.

Tables-first layout for broad client support.

Inline CSS (no external CSS).

Use hosted images with absolute URLs.

Bulletproof buttons (table-based with display:block links).

Alt text on all images.

Fallbacks for Outlook (no background images in critical areas).

Primary CTA appears above the fold; repeat at end.

Keep copy short: headline (≤9 words), 1–2 short paragraphs, single CTA.

Footer: physical address, contact email/phone, social links, legal/registration info if required.

Email component snippets

Button (bulletproof)

<table role="presentation" cellpadding="0" cellspacing="0" border="0" align="center">

  <tr>

    <td bgcolor="#000000" style="border-radius:4px;">

      <a href="https://tebelo.org/donate" 

         style="display:block;padding:12px 20px;font-family:Arial,Helvetica,sans-serif;font-size:16px;line-height:1.2;text-decoration:none;color:#ffffff;">

        Donate

      </a>

    </td>

  </tr>

</table>

Basic email shell

<!doctype html>

<html>

  <head>

    <meta name="x-apple-disable-message-reformatting">

    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>

    <title>Tebelo</title>

  </head>

  <body style="margin:0;padding:0;background:#f6f7f8;">

    <table role="presentation" width="100%" cellpadding="0" cellspacing="0" border="0">

      <tr>

        <td align="center" style="padding:24px 12px;">

          <table role="presentation" width="600" cellpadding="0" cellspacing="0" border="0" style="background:#ffffff;border-radius:6px;overflow:hidden;">

            <tr>

              <td style="padding:20px 24px;">

                <!-- Logo -->

                <img src="https://tebelo.org/path-to-logo.png" alt="Tebelo" width="120" style="display:block;border:0;outline:0;">

              </td>

            </tr>

            <tr>

              <td style="padding:0 24px 12px 24px;font-family:Arial,Helvetica,sans-serif;color:#111;">

                <h1 style="margin:0 0 8px 0;font-size:22px;line-height:1.3;font-weight:bold;">Together we build healthy communities</h1>

                <p style="margin:0 0 16px 0;font-size:16px;line-height:1.6;">

                  Your support helps learners access coding, robotics and real-world skills at the Matter Innovation Hub in Plettenberg Bay.

                </p>

                <!-- CTA -->

                <!-- Insert bulletproof button snippet here -->

              </td>

            </tr>

            <tr>

              <td style="padding:12px 24px 24px 24px;font-family:Arial,Helvetica,sans-serif;font-size:12px;color:#555;">

                Tebelo Community Development NPC • Portion 10 of Farm 434, Holt Hill N2 Harkerville, Plettenberg Bay, 6600 • 083 625 3755

              </td>

            </tr>

          </table>

        </td>

      </tr>

    </table>

  </body>

</html>

7) Copy patterns (ready-to-use)

CTA verbs: Donate · Partner with Us · Sponsor a Hub · Volunteer · Learn More · Get Involved

Section openers

Health: "Prevention first. Data-driven care for real lives."

Education: "From classroom to career—skills that stick."

Nutrition: "A daily meal that fuels learning."

Impact lines

"The first Matter Innovation Hub in SA helps local learners code, create, and solve real problems."

"Our Lighthouse site brings training together for entrepreneurs, teachers, farmers and caregivers."

8) Code conventions

Folders:

/styles/tokens.css (CSS variables for color, spacing, radii)

/styles/base.css (resets + typography + utilities)

/components/ (web) and /emails/ (HTML email partials)

/content/ (MD/JSON content blocks)

Naming: BEM-ish (.card, .card--feature, .btn, .btn--primary).

Performance: compress images, preconnect fonts if used, minimize render-blocking.

9) SEO & sharing

Per page: unique title (≤60 chars), meta description (≤155 chars).

OpenGraph: title, description, image (1200×630).

Add structured data where relevant (Organization, Article for news posts).

Descriptive slugs, avoid dates in URLs for evergreen pages.

10) AI generation guardrails (Cursor)

When generating code or copy:

Check tebelo.org for current headings, imagery, and project names; mirror voice and content structure.

Keep CTAs action-oriented and few (1 primary per screen).

Enforce accessibility (contrast, alt text, focus, labels).

For email HTML, prefer table-based layout + inline CSS only.

Never invent partner names, stats, or certifications—use known projects (e.g., Lighthouse, Matter Innovation Hub) and update via content files.

If colors are missing, first extract them from the live site; if still unknown, use the fallback scheme and mark TODO: confirm exact hex.

11) Quick tasks for project kickoff

 Extract brand colors from tebelo.org and set /styles/tokens.css.

 Import current logo and set header/footer components.

 Build base layout, header, footer, and card components.

 Create emails/ with a master template + CTA partial.

 Draft Home, Our Work, Get Involved, About, Contact.

 Add Donate and Partner CTAs site-wide.

 Check Lighthouse, Matter Hub, and Nutrition pages for updated copy/images.

Notes

This guide is intentionally simple and human. Default to clarity over decoration.

Keep everything donor- and community-friendly.
