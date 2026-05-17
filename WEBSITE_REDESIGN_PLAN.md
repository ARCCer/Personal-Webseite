# Website Redesign Plan

This plan describes how to redesign the personal academic website into a clean, research-oriented site for a PhD student / early-career researcher in operations management, AI, GenAI, and platform/service operations. It is based on the current repository structure, `CONTENT_TODO.md`, the structured YAML source files, and design lessons from the example sites.

No implementation should be done from this document alone without a separate build step.

## 1. Current Repository Diagnosis

The repository is a Quarto website project with a starter configuration:

- `_quarto.yml`: current site configuration, navbar, title, theme, and stylesheet hook.
- `index.qmd`: starter homepage with a blog listing.
- `about.qmd`: removed after merging biography and academic background content into the homepage.
- `styles.css`: currently minimal.
- `posts/`: blog content folder from the starter site.
- `website/`: draft pages for research, publications, teaching, and service.
- `source/`: structured YAML content for academic profile, education, research interests, papers, talks, teaching, industry experience, awards, service, skills, and references.
- `cv/`: modular LaTeX CV and generated CV PDFs.
- `papers/`: paper PDFs.
- `Profiles/`: profile image.
- `CONTENT_TODO.md`: content checklist for website completion.

Main diagnosis:

- The current public-facing website files are being converted from starter Quarto files into academic profile pages.
- The strongest academic content currently lives in `source/`, `cv/`, `papers/`, and `CONTENT_TODO.md`, not in the website pages.
- The current Home and About pages overlap heavily; biography and academic background should be merged into the homepage.
- The current navbar is not aligned with the academic website goal.
- Static files need cleaner canonical paths before publication.
- The website should become an academic profile site, not a blog-first site.

## 2. Proposed Website Information Architecture

Target top-level pages:

1. Home
2. Research and Publications
3. Industry Experience
4. Teaching and Service
5. CV

Navigation recommendation:

- `Home`
- `Research`
- `Industry`
- `Teaching & Service`
- `CV`

The `CV` item should link to a dedicated `cv.qmd` page. That page should provide a prominent PDF download, preferably to a canonical stable filename such as `cv/Chuan_Zhu_CV.pdf`, and a concise web summary of the CV. Contact information should remain on the homepage and in the footer, not as a standalone page.

Navbar display rule:

- Use a concise site brand in the navbar: `Chuan (River) Zhu`.
- Do not place research keywords or the full SEO title in the visible navbar brand, because it becomes visually crowded and truncates poorly on smaller screens.
- Keep the navbar focused on page navigation only: `Home`, `Research`, `Industry`, `Teaching & Service`, and `CV`.
- Do not include `Email`, `ORCID`, or `LinkedIn` in the navbar. These links should appear in the homepage contact section and compact footer links, where they are more contextually useful.

Visible page title rule:

- Suppress Quarto's default visible title metadata block on public pages.
- Keep page titles, descriptions, authorship, and keywords as metadata for SEO and sharing where useful, but do not display `Author` or `Keywords` as page content.
- Each page should instead begin with its custom designed content section, such as a homepage hero or a concise page introduction.

Design influence from examples:

- From Hongseok Namkoong: use a clear research agenda / philosophy section that explains the intellectual center of the work.
- More specifically, the merged Research page should follow the spirit of Namkoong's research overview: begin with a substantive research philosophy, organize the agenda into a few named streams, and connect each stream to representative papers or projects. Do not copy the text, examples, images, or exact layout.
- From Qiaowen Guo: use job-market-ready organization, clear working paper entries, and direct CV/research navigation.
- More specifically, use Qiaowen Guo's industry-facing structure as inspiration for a separate Industry Experience page: concise experience blocks, clear dates and locations, and short bullets that explain why each role matters for research credibility. Do not copy text, exact layout, images, or personal content.
- From Chaofan Zhai: keep the site compact, PhD-candidate friendly, and easy to scan.

## 3. Proposed Page-by-Page Structure

### Home

Purpose: combined academic identity, concise biography, and strongest research signals. This page replaces the standalone About page.

Recommended order:

1. Hero / identity block
   - Name: Chuan Zhu
   - Position: Ph.D. Candidate
   - Affiliation: School of Management, Fudan University
   - Location: Shanghai, China
   - Profile image
   - Link row: Email, CV, Google Scholar, ORCID, LinkedIn, SSRN/arXiv

2. Concise bio and academic background
   - 1-2 short paragraphs
   - Ph.D. in Business Artificial Intelligence, Fudan University, expected 2027
   - B.S. in Logistics Engineering, Northeast Forestry University, 2018
   - Avoid a long narrative bio unless the user provides one later

3. One-paragraph research summary
   - AI, GenAI, AI agents in operations management
   - Service operations and platform operations
   - Human-AI collaboration
   - Empirical operations management, field experiments, platform data, quasi-experimental methods

4. Research streams preview
   - AI-enabled service operations
   - Human-AI collaboration and human-in-the-loop systems
   - Platform operations and workforce management
   - Empirical operations management methods

5. Featured working paper
   - Job Market Paper
   - Title
   - Authors
   - Status
   - Short description
   - Links to SSRN / arXiv / paper PDF when available

6. Industry collaboration preview
   - Alibaba Group, Customer Operations Department
   - EDF Climate Corps / LONGi Green Energy

7. Teaching and service preview
   - Concise teaching assistant summary
   - Link to Teaching and Service page

8. Selected links / contact
   - CV
   - Email
   - ORCID
   - LinkedIn
   - SSRN / arXiv

### About Page Decision

No separate About page is recommended at this stage. The homepage should carry the short bio, academic background, research identity, and contact links. A separate About page can be restored later only if there is a richer narrative biography that is meaningfully different from the homepage.

### Research and Publications

Purpose: explain the research philosophy, research agenda, and research output portfolio in one scan-friendly page.

Recommended order:

1. Research philosophy
   - This should be the intellectual anchor of the page, inspired by the structure of Hongseok Namkoong's research overview.
   - Keep it concise: 2-4 short paragraphs, not a full research statement.
   - Core message: AI and GenAI are not only prediction tools; they change operational processes, human work, platform governance, and service system design.
   - Emphasize empirical grounding: field experiments, platform data, causal inference, and industry collaboration as the source of research questions and evidence.
   - Emphasize managerial relevance: how firms should design, govern, and evaluate AI-enabled service and platform operations.
   - If using the John von Neumann quote from `CONTENT_TODO.md`, use it sparingly and only if it strengthens the page. A short paraphrase may be better than a long quotation.

2. Research overview / contents
   - 1-2 concise paragraphs
   - Should summarize the agenda after the philosophy block
   - Can include a compact contents list linking to research streams and working papers
   - Avoid overly long abstract-style prose

3. Research streams
   - Stream 1: GenAI and AI agents in service operations
   - Stream 2: Human-AI collaboration and human-in-the-loop systems
   - Stream 3: Platform operations and workforce management
   - Stream 4: Empirical operations management, field experiments, platform data, and quasi-experimental methods
   - Each stream should have a short motivating paragraph and then link to related papers/projects.

4. Working Papers
   - Job Market Paper first
   - Other working papers second
   - Each paper should include title, authors, status/type, short description, methods/data tags, and public links

5. Publications
   - Only show if published/accepted items exist
   - Hide this section when empty, rather than showing TODO text

6. Work in Progress / Research Projects
   - Use this section only for projects mature enough to show publicly
   - Include project title, short description, method, data context, status, and links when available

7. Conference Presentations
   - POMS Annual Meeting, 2026
   - POMS-HK, 2026

8. Industry data and collaboration note
   - Short explanation of industry collaboration as research context
   - Keep confidentiality boundaries clear

Recommended paper entry format:

- Title
- Authors
- Status / type
- 2-3 sentence description
- Methods / data context tags
- Links: PDF, SSRN, arXiv, slides, code if available

### Industry Experience

Purpose: show field access, industry collaboration, and research-relevant operational experience without letting industry content overwhelm the academic identity.

Recommended order:

1. Brief positioning statement
   - Explain that the industry experience supports empirical research in AI-enabled service operations, platform operations, and field experimentation.
   - Keep the tone academic and factual, not resume-like or promotional.

2. Alibaba Group
   - Organization and unit: Alibaba Group, Customer Operations Department
   - Role: Research Scientist
   - Arrangement: Full-time, Onsite, Academic Collaboration
   - Dates and location: July 2022 to Present; Hangzhou, China
   - 3-4 concise bullets linking the role to human-AI customer service design, causal inference for worker supply, and data-driven customer service operations.
   - Add a confidentiality-safe note if needed.

3. Environmental Defense Fund Climate Corps and LONGi Green Energy
   - Role: Climate Corps Fellow
   - Arrangement: Full-time, Onsite, Internship
   - Dates and location: July 2021 to Oct. 2021; Xi'an, China
   - 2-3 concise bullets on supplier-side carbon-management analysis, supplier survey design, benchmarking, and green supplier empowerment roadmap.
   - Include the public project link only if the link is intended to be public.

4. Research relevance
   - Short section connecting the experience to field experiments, platform data, service operations, and operational problem discovery.
   - Avoid claiming proprietary data access or confidential details unless explicitly approved.

5. Information to complete
   - Preferred confidentiality wording
   - Whether to include public project links
   - Whether to include logos or keep text-only

### Teaching and Service

Purpose: show teaching readiness and service development without overbuilding.

Recommended order:

1. Teaching Experience
   - Teaching assistant entries
   - Course level and term

2. Teaching Interests
   - Add when available

3. Presentations
   - Optional summary or link back to Research and Publications

4. Service
   - Reviewer service
   - Conference service
   - Departmental service
   - Hide empty categories until real content exists

5. Honors, Fellowships, and Awards
   - Climate Corps Fellow
   - Outstanding Academic Scholarship

### CV

Purpose: provide a clean web-facing CV page and a prominent downloadable PDF.

Recommended order:

1. Download block
   - Link to the current CV PDF
   - Note that a stable canonical PDF filename should be chosen before final deployment
   - Include last updated date if available

2. Academic profile
   - Name, position, affiliation, location
   - Email, ORCID, LinkedIn, SSRN; Google Scholar and GitHub only when provided

3. Education
   - Ph.D. in Business Artificial Intelligence, Fudan University, expected 2027
   - B.S. in Logistics Engineering, Northeast Forestry University, 2018

4. Research interests
   - Service operations
   - Platform operations
   - Empirical operations management
   - AI-enabled service operations, human-AI collaboration, human-in-the-loop systems, GenAI and AI agents, workforce management

5. Research output
   - Publications, if any
   - Working papers
   - Conference presentations

6. Professional experience, teaching, service, honors, and skills
   - Keep this concise and link to dedicated pages where helpful

### Contact On Homepage

Purpose: make it easy to reach and verify academic identity without creating a separate Contact page.

Recommended content:

- Email
- CV page
- ORCID
- LinkedIn
- Google Scholar, when available
- GitHub, if public and relevant
- SSRN / arXiv links
- Location: Shanghai, China

This should appear as a homepage contact section and as compact footer links only. Do not create a standalone Contact page unless the site later needs a separate scheduling or advising contact workflow.

## 4. Required Content Inputs

Still needed from the user:

- Personal website URL / final site URL
- Google Scholar URL
- GitHub URL, if public
- ResearchGate URL, if any
- Canonical CV PDF filename
- Canonical profile image path or preferred crop
- 1-paragraph bio
- Longer academic bio
- Website tagline
- Teaching interests
- Guest lectures, if any
- Reviewer service, if any
- Conference service, if any
- Work-in-progress projects, if any
- Published papers, if any
- Public slide decks, if any
- Preferred wording for industry collaboration confidentiality boundaries
- Whether to show public project links for industry experience
- Whether to include company logos or keep the Industry page text-only

Content that already exists:

- Name, position, affiliation, location, email
- LinkedIn and ORCID
- Research identity and interests
- Two working papers
- Two conference presentations
- Teaching assistant experience
- Two honors / awards
- CV PDFs
- Profile image
- Paper PDFs

## 5. Visual Design Direction

Preferred style:

- Professional academic
- Clean and concise
- Research-oriented
- Modern but conservative
- Easy to maintain
- Suitable for PhD student / early-career researcher

Design principles:

- Use a white or very light background.
- Use one restrained accent color, likely a deep blue, teal, or muted academic green.
- Use strong typography hierarchy but avoid oversized marketing-style hero text.
- Use compact paper entries rather than large decorative cards.
- Use section dividers and spacing for readability.
- Keep navigation simple and predictable.
- Avoid heavy animations, decorative gradients, or stock imagery.
- Use the profile image professionally, preferably as a clean portrait crop.

Layout direction:

- Homepage can use a two-column intro on desktop: text + profile image.
- The combined Research and Publications page should be single-column or narrow content-width for readability.
- The Research and Publications page should have a lightweight table of contents or anchor-link list near the top, especially if it includes philosophy, streams, papers, and presentations.
- The research philosophy should be visually prominent but still text-first: a clean full-width section or lightly emphasized block, not a decorative card.
- Paper entries can use compact blocks with status labels and link rows.
- The Industry Experience page should use compact experience entries with clear organization, role, arrangement, dates, location, and research-relevance bullets.
- Keep the Industry page visually consistent with the Home and Research pages: text-first, conservative, and easy to scan.
- The CV page should be text-first and practical: prominent PDF button, compact section summaries, and clear links to the deeper Research, Industry, and Teaching pages.
- Mobile should stack everything cleanly.

## 6. Data / Content Management Approach

Current source-of-truth:

- `source/*.yml` should remain the canonical structured facts.
- `CONTENT_TODO.md` should remain the editorial checklist.
- `cv/` should remain the CV generation area.
- `papers/` should store public PDFs.
- `Profiles/` should store original profile images, though final website assets should preferably be copied or renamed into an `assets/` folder.

Recommended approach:

- Keep academic facts in `source/`.
- Keep website prose in `.qmd` pages.
- During drafting, use TODO placeholders where information is missing; before final deployment, remove public-facing TODOs or move them back into `CONTENT_TODO.md`.
- Hide empty sections instead of displaying incomplete content.
- Use stable static paths for public-facing files.

Recommended asset cleanup:

- Create `assets/`.
- Copy profile image to `assets/profile.jpg`.
- Choose one canonical CV file, such as `cv/Chuan_Zhu_CV.pdf`.
- Consider renaming paper PDFs to shorter web-safe filenames.

## 7. SEO and Accessibility Improvements

SEO:

- Update `_quarto.yml` visible site title to `Chuan (River) Zhu`.
- Keep the fuller research identity in metadata descriptions, Open Graph text, and page copy rather than in the navbar title.
- Update site description to mention operations management, AI, GenAI, service operations, and platform operations.
- Replace placeholder site URL.
- Add page-level descriptions where useful.
- Use descriptive page titles.
- Use meaningful link text, not "click here."
- Add research keywords naturally in homepage and Research and Publications page text, and keep keyword metadata invisible to readers.
- Hide Quarto's generated visible title metadata block so `Author` and `Keywords` do not appear as standalone page sections.

Accessibility:

- Add alt text for profile image.
- Ensure all links have descriptive labels.
- Maintain strong color contrast.
- Use semantic headings in order.
- Avoid relying on color alone for status labels.
- Ensure mobile navigation is usable.
- Ensure paper links are keyboard accessible.

## 8. Deployment and Testing Plan

Build/testing:

1. Run Quarto preview locally.
2. Check homepage, Research and Publications, Industry Experience, Teaching and Service, CV page, and homepage contact section.
3. Confirm all internal links work.
4. Confirm PDF links open.
5. Confirm profile image loads.
6. Confirm paper PDFs open.
7. Check mobile viewport.
8. Check page titles and metadata.
9. Check external links: ORCID, LinkedIn, SSRN, arXiv.
10. Before final deployment, verify no TODO text appears on public pages.

Deployment:

- Confirm hosting target, likely GitHub Pages or Quarto Publish.
- Update `site-url` in `_quarto.yml`.
- Render site with Quarto.
- Deploy.
- After deployment, test all public URLs again.

## 9. Step-by-Step Implementation Sequence

Recommended implementation order:

1. Finalize content decisions
   - Choose canonical CV filename
   - Choose profile image
   - Confirm which paper PDFs can be public
   - Add Google Scholar URL if available

2. Clean assets
   - Create `assets/`
   - Add `assets/profile.jpg`
   - Add or rename public PDFs if needed

3. Update site configuration
   - `_quarto.yml`
   - Short visible site title
   - Site description
   - Navbar with page links only
   - Footer
   - Social links in homepage contact/footer, not in the navbar

4. Redesign homepage
   - Replace blog listing with a combined academic homepage
   - Add profile image, concise bio, academic background, research summary, featured paper, industry preview, teaching preview, and contact links
   - Remove standalone `about.qmd` once homepage carries the necessary biography content

5. Build Research and Publications page
   - Begin with a concise research philosophy section inspired by Example 1
   - Add a compact contents / anchor-link list if the page becomes long
   - Use research overview and streams
   - Add working paper entries
   - Add paper links
   - Add conference presentations
   - Add project summaries only when public-ready

6. Build Industry Experience page
   - Use verified entries from `source/industry_experience.yml`
   - Lead with a short academic positioning statement
   - Use concise role blocks with role, arrangement, dates, location, and research-relevance bullets
   - Add confidentiality and public-link TODOs where information is missing

7. Build Teaching and Service page
   - Add teaching assistant experience
   - Add honors
   - Add service sections only when populated

8. Build CV page
   - Add prominent PDF download
   - Add concise web CV summary from `source/*.yml`
   - Link to Research, Industry, and Teaching pages for deeper detail
   - Add TODOs for missing Google Scholar, GitHub, publications, and canonical PDF filename

9. Keep contact on homepage and footer only
   - Add email and academic links to homepage contact section
   - Do not create a standalone Contact page

10. Style pass
    - Update `styles.css`
    - Tune typography, spacing, link styles, status labels

11. Test and deploy
    - Render locally
    - Check links, mobile, accessibility, and public-facing TODOs

## 10. Risks and Assumptions

Risks:

- Some public links are still missing, especially Google Scholar and personal website URL.
- Some static filenames are long and may be awkward in public URLs.
- The current `cv/` folder contains several generated PDFs; a canonical one should be chosen.
- Some YAML files still contain TODO placeholder sections; these should not appear publicly.
- Industry collaboration language may require confidentiality review.
- A research statement quote may feel too long or philosophical for the homepage if used without careful editing.
- The Industry Experience page may overtake the academic message if it is too detailed; keep it concise and explicitly tied to research.
- Removing the About page increases pressure on the homepage to stay concise; avoid turning the homepage into a long biography.

Assumptions:

- The site will remain a Quarto website.
- The website should prioritize academic identity over blog posts.
- Working papers are appropriate to show publicly.
- The profile image in `Profiles/` can be used or adapted.
- The website should be maintainable without a complex build pipeline.
- Research and publications should be merged into one page because the current portfolio is compact and readers should see agenda, papers, and presentations together.
- The combined page should remain concise so it does not become an overly long research statement.
- The research philosophy should be original to Chuan Zhu's work. It may be influenced by Example 1's structure and intellectual clarity, but should not imitate Namkoong's wording, examples, diagrams, or exact page order.
- Industry experience is central enough to merit a separate page because it supports field access, empirical grounding, and credibility in service/platform operations.
- The standalone About page is unnecessary until a longer biography or personal academic narrative is available.
- A standalone Contact page is unnecessary because the same information is clearer as a homepage contact section and footer links.
- A CV page is useful because it gives visitors a stable web destination while still preserving the downloadable PDF.

Core design decision:

The final website should combine the research-agenda clarity of Hongseok Namkoong's site, the job-market organization of Qiaowen Guo's site, and the compact PhD-candidate usability of Chaofan Zhai's site. The result should be a concise, polished academic website that foregrounds research identity, working papers, industry collaboration, and teaching readiness.
