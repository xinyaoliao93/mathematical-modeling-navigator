# Approved Authoritative Sources

These are the default web domains for verified model selection and analysis. Prefer exact entries, chapters, or course lessons over search-result snippets.

## 1. SpringerLink

- Domain: `link.springer.com`
- Statistical reference: *International Encyclopedia of Statistical Science*.
- Optimization reference: *Encyclopedia of Optimization*.
- Best for: unfamiliar terminology, statistical/optimization families, definitions, historical context, extensions, and bibliographies.
- Limitation: some full text requires institutional access.

## 2. Wiley Online Library / Wiley StatsRef

- Domain: `onlinelibrary.wiley.com`
- Reference: *Encyclopedia of Statistical Sciences*.
- Best for: statistical methods, assumptions, applications, cross-references, and deeper bibliographies.
- Limitation: some full text requires institutional access.

## 3. Penn State STAT Online

- Domain: `online.stat.psu.edu`
- Core routes: STAT 501 regression; STAT 502 ANOVA, random effects, mixed models and repeated measures; STAT 504 categorical/GLM; STAT 505 multivariate methods; STAT 508 statistical learning; STAT 510 time series.
- Best for: applied selection logic, assumptions, worked examples, diagnostics, and course-level explanations.

## 4. NIST/SEMATECH e-Handbook of Statistical Methods

- Domain: `itl.nist.gov`
- Entry: `https://www.itl.nist.gov/div898/handbook/`
- Best for: engineering statistics, exploratory analysis, process modeling, experimental design, distributions, diagnostics, uncertainty, and case studies.
- Limitation: not a complete source for modern ML, causal, spatial, or hierarchical models.

## 5. MIT OpenCourseWare

- Domain: `ocw.mit.edu`
- Core routes: Optimization Methods; Introduction to Mathematical Programming; relevant differential equations, probability, control, and algorithms courses.
- Best for: derivations, optimization structure, algorithms, problem sets, and mathematical foundations.
- Limitation: course coverage is distributed rather than encyclopedic.

## Verification protocol

1. Search the exact model name and accepted aliases within the most relevant approved domains.
2. Confirm the model's response/data structure, assumptions, and target quantity from an exact page.
3. For a material recommendation, corroborate with a second relevant approved source when possible.
4. Prefer a reference entry for definition and a course or evidence page for application and diagnostics.
5. Cite direct pages close to each claim; do not cite search-result pages.
6. If sources disagree, report the difference in parameterization, scope, or convention instead of silently merging them.
7. If access is limited to an abstract or table of contents, say so. Do not claim the inaccessible text was checked.
8. If the five sources lack the model, name the coverage gap and request permission to use the original paper or another authoritative society, university, government, publisher, or official software source.

## Query patterns

- `site:online.stat.psu.edu <model> assumptions diagnostics`
- `site:itl.nist.gov/div898/handbook <method or data problem>`
- `site:link.springer.com/referencework <model or optimization method>`
- `site:onlinelibrary.wiley.com <model> encyclopedia statistical sciences`
- `site:ocw.mit.edu <model family> lecture notes`

## Evidence labels

- **Verified:** directly supported by an inspected approved source.
- **Modeling judgment:** a recommendation inferred from the user's goal and data structure.
- **Conditional assumption:** missing information temporarily assumed and stated explicitly.
