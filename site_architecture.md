# JC&C Roofing — Complete Site Architecture Blueprint

## 1. Implementation Standards (WordPress Safe)
> [!IMPORTANT]
> **Design Fidelity**: The final implementation MUST maintain 100% design parity with the current site.
> **Technology Stack**: Use only Vanilla HTML, Vanilla CSS (using the design tokens below), and Vanilla JS. This ensures compatibility with the Elementor HTML widget and "WordPress Safe" execution.
> **No Conflicts (Custom Classes)**: To avoid CSS conflicts with WordPress themes or plugins, ALL custom classes must use a unique prefix (e.g., `.jcc-hero`, `.jcc-button`, `.jcc-card`). Avoid generic names like `.header`, `.container`, or `.btn`.
> **Code Structure**: Every section must be clearly separated and labeled with descriptive HTML comments (e.g., `<!-- Section: Hero Mobile -->`).

## 2. Global Design System

### Fonts
- **Headlines/Display**: `Manrope` (800)
- **Body/Labels**: `Manrope` (400–700)
- **Icons**: `Material Symbols Outlined` (Google)

### Colors
| Token | Hex | Use |
|---|---|---|
| primary | `#006098` | Blue — brand, icons, borders |
| secondary | `#F16223` | Orange — CTAs, hover |
| secondary-container | `#fd6b2c` | Bright orange badges |
| on-background | `#0b1c30` | Main dark text |
| inverse-surface | `#213145` | Dark section bg |
| surface-container-low | `#eff4ff` | Light blue section bg |
| error | `#ba1a1a` | "URGENT" badges |

### CSS Classes (Custom)
- `.jcc-orange-power-button` — gradient `#F16223 → #D9531E`, box-shadow orange glow
- `.jcc-glass-card` — `rgba(255,255,255,0.7)`, `backdrop-blur(20px)`
- `.jcc-glass-panel` — `rgba(255,255,255,0.8)`, `backdrop-blur(12px)`

---

## 3. Header & Navigation (Fixed, `z-50`)
- **Height**: `h-20`
- **Logo**: `JCC-Roofing-Company-in-Houston-Main-New-Logo-1024x1024.webp`
- **Desktop Nav Links** (dropdown on hover via CSS `.nav-item:hover .dropdown-menu`):
  - **Roof Installation** → `roof-replacement-in-houston/`
    - Roof Replacement, Commercial Roof Replacement, Roofing Certifications, Roofing Contractor Tomball
  - **Repairs** → `roof-repair-company-in-houston/`
    - Most Trusted Roof Repair Experts, Emergency Roof Repair Houston, Roof Repair Cost Guide, Commercial Roof Repairs
  - **Roof Maintenance** → `roof-maintenance-in-houston/` (direct link, no dropdown)
  - **Storm Claims** → `roof-insurance-claims/`
    - Houston Roof Damage Repair
  - **Financing** → `roof-financing-houston/` (direct link)
  - **About Us** → `about-us/`
    - Contact us, Service Areas, Blog, Our Projects, Roofing FAQ's
- **Header CTAs**:
  - `Get Free Estimate` → orange button → `contact-us/`
  - `support_agent` icon → opens `#support-modal` (pulsing blue dot badge)
  - Hamburger `menu` icon → opens `#mobile-menu` (mobile only)

### Mobile Menu (`#mobile-menu`, slide-in right panel, `w-320px`)
- Same links as desktop with icons, organized into expandable groups
- **Bottom CTA block** (dark bg): `(713) ROOFING` orange call button + tagline "JC&C Roofing Company • Since 2013"

---

## 4. Full Section Map (In Page Order)

### S1 — Hero Mobile (`#hero-mobile`, visible `< 1024px`)
- **Badge**: "Since 2013 | Houston's Trusted Experts" (blue pill)
- **H1**: "Houston's Go-To Roof Repair Near Me..."
- **Body**: "Protecting Houston homes with precision roofing, expert storm damage restoration, and a legacy of integrity since 2013. Done right the first time, every time."
- **Feature Grid (2×2)**:
  - Emergency Service | Insurance Help
  - Preventive Maintenance | No High-Pressure Sales
- **CTAs**: `Call 24/7` (orange) | `Get Free Estimate` (blue outline)
- **Stats**: `15+` Years | `5k+` Roofs Installed | `4.8` Google Rating
- **Mascot Card (Colter)**:
  - Image: `JCC-roofing-pet-Colter-Surprised.webp` (w-20 rounded-full, green online dot)
  - Text: "Hi, I'm Colter from JC&C" / "Ready to help you calculate your roof cost instantly!"
  - Button: `Launch Free Roof Calculator` (dark bg, rocket icon) → triggers `#calculator-modal`
  - Fine print: "Honest assessments • No pressure sales • Houston-local expertise"
- **Hero Image**: `scale-hero-test.webp` (aspect-[4/5] → aspect-square on md)

### S2 — Hero Desktop (`#hero-desktop`, visible `≥ 1024px`)
- **Background image**: `scale-hero-test.webp` with `gradient-to-r from-white via-white/95 to-transparent`
- **Trust badge**: "Houston's Go-To Roofing Experts Since 2013" (with ⭐)
- **H1**: "Houston's Go-To Roof Repair Near Me **JC&C Roofing Company**"
- **Sub-features inline** (with icons): `24/7 Response` | `Emergency Service` | `Free Estimates`
- **Body**: "Houston's Go-To Roof Repair Near Me — Discover why homeowners across the Greater Houston Area trust JC&C Roofing Company..."
- **CTAs**:
  - `Call (713) ROOFING` (orange, sub-text "24/7 Emergency Response") → `tel:+17137663464`
  - `Get Free Estimate` (blue, sub-text "No Obligation • Fast Response") → `contact-us/`
- **Stats**: `15+ Years` Experience | `5,000+` Roofs Completed | `4.8 Star` Rating
- **Right side — Colter Card** (glass-panel):
  - Quote: "As your Houston roofing expert, I recommend starting with our Instant Roofing Calculator..."
  - Button: `Launch Free Roof Calculator` → `#calculator-modal`
  - Fine print: "• Honest assessments • No pressure sales • Houston-local expertise"
- **Right side — Benefits Grid (2×2)**:
  - 365 Days Emergency | Insurance Claim Assistant
  - Preventive Maintenance | No High-Pressure

### S3 — Emergency Services Grid
- **H2**: "Emergency Roof Repair & Comprehensive Roofing Services in The Greater Houston Area"
- **Subtitle**: "As Houston's trusted roofing contractor, we provide emergency roof repair near me, roof leak detection, flat roof repairs, and specialized maintenance services. Our roof repair specialists offer 24/7 emergency service..."
- **6 Service Cards** (3-col grid):
  1. **Leak Detection** [URGENT badge] → `roof-leak-detection-houston/` — "Infrared technology to pinpoint moisture..." CTA: "Secure My Home →"
  2. **Flat Roof Repairs** [COMMERCIAL badge] → `houston/roof-repairs/` — "Specialized TPO and PVC repair..." CTA: "View Details →"
  3. **Storm Damage** [INSURANCE FRIENDLY badge] → `emergency-roof-repair-houston/` — "Complete hail and wind damage assessment..." CTA: "Get Inspection →"
  4. **Roof Tune-Up** [SPECIAL: $199 badge, highlighted card] → `houston/roof-tune-up/` — "Comprehensive check, shingle replacement (up to 5)..." CTA: orange "Claim $199 Offer"
  5. **Gutter Tune-Up** [SPECIAL: $149 badge] → `gutter-tune-up/` — "Debris removal, realignment, and joint sealing..." CTA: "Book Now →"
  6. **Pine Needles Removal** [MAINTENANCE badge] → `roof-pine-needle-removal-services/` — "Prevent destructive 'needle rot'..." CTA: "Learn More →"

### S4 — Emergency Service Area (Blue Box `#cfe5ff`)
- **H2**: "Need Emergency Roof Repair Services in Houston?"
- **Label**: "SERVICE AREA"
- **Body**: "Serving all Houston neighborhoods: **Downtown, The Heights, River Oaks, Memorial, Katy, Sugar Land, The Woodlands, Spring, Cypress, Humble, Kingwood, Pearland, Friendswood, League City,** and surrounding areas."
- **White action box CTAs**:
  - `🚨 Emergency: (713) ROOFING` (orange button) → `tel:7137663464`
  - `Get Free Repair Quote` (blue outline) → `contact-us/`
  - Fine print: "Licensed & Insured Houston Experts"

### S5 — Founder's Story (Dark bg `#213145`)
- **Label**: "OUR HERITAGE" (orange)
- **H2**: "The Heart of Houston's Go-To Roofing Experts"
- **Body**: "Jennifer and Christian Hernandez founded JC&C Roofing with a single mission: to bring authentic transparency to an industry often clouded by confusion. As Houston locals, we treat every roof like it's protecting our own family."
- **Key Points**: "Verified Local Experts" (handshake icon) | "Quality Certified" (military_tech icon — "GAF Master Elite certified professionals.")
- **Checklist**: "Zero sales pressure—only expert consultation." | "Family-owned and locally operated in Houston."
- **Main Image**: `JCC-Roofing-Company-founders-Christian-Jennifer-Hernandez-scaled.webp`
- **Floating Badge**: "15+" / "Years in Houston" (glass morphism, bottom-right)

### S6 — Four Pillars (White bg)
- **H2**: "The Four Pillars of Our Integrity Promise"
- **Subtitle**: "What truly separates Houston's family-owned roofing experts from the rest? Our unwavering commitment to these core principles."
- **4 Cards (hover: lift + shadow)**:
  1. 🏡 **Family Values, Not Corporate Profits** — "As a family-owned business, we measure success by lasting relationships, not quarterly reports." Badge: "Local & Accountable 👨‍👩‍👧‍👦"
  2. 🔍 **Transparency, No Hidden Agendas** — "From initial estimate to final invoice, complete transparency. No hidden fees or surprise charges." Badge: "No High-Pressure Sales 💬"
  3. 🛡️ **Quality That Stands the Test of Time** — "Only premium materials and manufacturer-certified installation methods." Badge: "GAF Master Elite Standards 🏆"
  4. 🤝 **Partnership Beyond the Project** — "Our relationship extends for years through maintenance, inspections..." Badge: "13+ Years, Still Answering 📞"

### S7 — Integrity Difference in Action (Surface-container-low bg)
- **H2**: "The Integrity Difference in Action"
- **Subtitle**: "How our commitment to integrity translates to tangible benefits for Houston homeowners."
- **4 Bullet Points** (icon + text):
  1. **Speed with Precision** — "While we complete most roofs in 1-2 days, we never sacrifice quality..."
  2. **Roofing Excellence Only** — "We specialize exclusively in roofing—no unnecessary upsells for gutters, siding, or windows."
  3. **Direct Owner Communication** — "As owners, Jennifer & Christian are personally involved in every project."
  4. **Premium Materials Promise** — "We refuse to cut corners with cheap materials. Every shingle, nail, and component meets or exceeds manufacturer specifications..."
- **Right Image**: `mockup-satisfaction-location.webp`

### S8 — Owner CTA (Dark bg `#213145`)
- **Badge**: "EXPERIENCE THE INTEGRITY DIFFERENCE"
- **H2**: "Ready to Work with Houston's Family-Owned Roofing Experts?"
- **Body**: "Join the thousands of Houston homeowners who have discovered what true integrity in roofing looks like. Let's protect your home with the care it deserves."
- **CTAs**: `Speak with the Owners` (orange) → `tel:+17137663464` | `Free Integrity Inspection` (white outline) → `contact-us/`
- **Trust Row**: ✔ 15+ Years Local Experience | ✔ 400+ Verified Reviews | ✔ BBB A+ (0 Complaints)

### S9 — Comprehensive Roofing Services (Surface-container-low bg)
- **H2**: "Comprehensive **Roofing Services** for All Houston"
- **Subtitle**: "As **Houston's most trusted roofing company**, we offer a full range of professional roofing services to protect your home or business across the **Greater Houston Area.**"
- **4-col icon card grid (8 total, but only 4 visible in first row)**:
  1. **365 Days Emergency Service** (emergency icon, orange) → `emergency-roof-repair-houston/` — Tags: 24/7 Service, Storm Response, Quick Fixes
  2. **Storm Damage & Insurance Assistance** (thunderstorm icon) → `houston-roof-damage-repair-insurance-claims/` — Tags: Claim Help, Damage Assessment, Insurance Restoration
  3. **Preventive Maintenance** (handyman icon) → `roof-maintenance-in-houston/` — Tags: Preventive Care, Inspections, Tune-Ups
  4. **No High-Pressure Sales** (handshake icon, dashed border, "Guaranteed" badge) — Tags: Honest Quotes, No Pressure, Transparent. CTA: "Contact Us"

### S10 — Tailored Solutions / Interactive Tabs (White bg)
- **H2**: "Tailored Solutions for Your Home"
- **Subtitle**: "Select a category below to explore how we solve your specific roofing challenges."
- **Tab Buttons** (pill style, `#solutions-tabs`): Residential Repair | Roof Replacement | Storm & Insurance | Financing
- **Dynamic Content Logic**: Selecting a tab updates the Title, Body, Bullets, CTA, and Image.
- **Tab 1: Residential Repair (Default)**:
  - **Title**: "Expert Residential Roof Repair"
  - **Body**: "Don't let a small leak turn into a structural disaster. Our experts use precision thermal imaging to find the source and repair it with materials that match your original roof perfectly. We specialize in Harris County residential roofing systems."
  - **Bullets**: 
    - `task_alt` Free 21-Point Inspection (We check every valley, flashing, and vent.)
    - `task_alt` Same-Day Service Available (Rapid response for active leaks in Houston and Katy.)
  - **CTA**: `Schedule Repair Now` → `https://www.myroofimprovement.com/roof-repair-company-in-houston/`
  - **Image**: `Houstons-roof-repair-company.webp`
- **Tab 2: Roof Replacement**:
  - **Title**: "Premium Roof Replacement & Installation"
  - **Body**: "As a GAF Master Elite contractor, we provide the highest level of roof replacement services in Texas. Our full system replacements are climate-tested for Houston's heat and humidity, ensuring your home remains protected for decades."
  - **Bullets**: 
    - `task_alt` Golden Pledge Warranty (Up to 50 years of non-prorated coverage.)
    - `task_alt` Certified Installation (Only the top 2% of contractors hold this credential.)
  - **CTA**: `Get Your Estimate` → `https://www.myroofimprovement.com/roof-replacement-in-houston/`
  - **Image**: `https://www.myroofimprovement.com/wp-content/uploads/2025/04/Attic-Ventilation-JCC-Roofing-Company.webp` (Selected matching asset from S11)
- **Tab 3: Storm & Insurance**:
  - **Title**: "Houston Storm Damage & Insurance Claims"
  - **Body**: "We take the stress out of storm recovery. Our team provides comprehensive damage reports, drone inspections, and on-site adjuster representation. We've helped thousands of Houston homeowners successfully navigate the insurance claim process."
  - **Bullets**: 
    - `task_alt` 24/7 Emergency Response (Immediate tarping and mitigation services.)
    - `task_alt` Expert Adjuster Meetings (We ensure no damage is overlooked by your carrier.)
  - **CTA**: `File a Claim Help` → `https://www.myroofimprovement.com/roof-insurance-claims/`
  - **Image**: `https://www.myroofimprovement.com/wp-content/uploads/2023/07/Roof-insurance-claim-inspection.webp`
- **Tab 4: Financing**:
  - **Title**: "Affordable Roofing Financing Options"
  - **Body**: "Quality roofing shouldn't be out of reach. We offer flexible financing solutions including $0 down, low monthly payments, and 0% interest options for Houston residents. Get an instant credit decision and start your project today."
  - **Bullets**: 
    - `task_alt` Low Monthly Payments (Plans that fit your family budget.)
    - `task_alt` Instant Approval (Quick digital process with no hidden fees.)
  - **CTA**: `Apply for Financing` → `https://www.myroofimprovement.com/roof-financing-houston/`
  - **Image**: `https://www.myroofimprovement.com/wp-content/uploads/2026/05/Roof-Replacement-and-Repair-Cost-in-Tomball-TX.png`

### S11 — Home Improvement Services Grid (Surface-container-low, 3-col, 9 cards)
- **H2**: "Our Houston Home Improvement Services"
- **All cards**: white bg, hover: lift + shadow + left orange accent bar
- **9 Cards** (with SVG/WebP icons in `w-20 h-20 bg-blue-50 rounded-2xl`):
  1. **Residential Roofing** → `houston-residential-roofing/` — Tags: Roof Repair, Replacement, Home Roofing. Icon: `ROOF-MAINTENANCE-JCC-ROOFING-COMPANY.svg`
  2. **Commercial Roofing** → `houston/` — Tags: Flat Roofs, Business Roofing, Industrial. Icon: `COMMERCIAL-ROOFING-JCC-ROOFING-COMPANY.webp`
  3. **Home Improvement Financing** → `roof-financing-houston/` — Tags: Low APR, Quick Approval, Flexible Terms. Icon: `ROOF-FINANCING-JCC-ROOFING-COMPANY.webp`
  4. **Insurance Claims** → `roof-insurance-claims/` — Tags: Claim Filing, Adjuster Liaison, Documentation. Icon: `ROOF-STORM-DAMAGE-CLAIMS-JCC-ROOFING-COMPANY.webp`
  5. **Roof Repairs** → `roof-repair-company-in-houston/` — Tags: Leak Repair, Shingle Replacement, Storm Damage. Icon: `ROOF-REPAIR-JCC-ROOFING-COMPANY.webp`
  6. **Roof Maintenance** → `roof-maintenance-in-houston/` — Tags: Inspections, Tune-Ups, Preventive Care. Icon: `ROOF-MAINTENANCE-JCC-ROOFING-COMPANY.webp`
  7. **Full Replacement** → `roof-replacement-in-houston/` — Tags: New Roof, Full Replacement, Quality Materials. Icon: `Attic-Ventilation-JCC-Roofing-Company.webp`
  8. **Gutter Systems** → `houston-gutter-services/` — Tags: Gutter Repair, Cleaning, Installation. Icon: `GUTTER-CONTRACTOR-JCC-ROOFING-COMPANY.webp`
  9. **Siding Services** → `houston-home-siding-replacement-company/` — Tags: Vinyl Siding, Fiber Cement, Energy Efficient. Icon: `ROOF-REPLACEMENT-JCC-ROOFING-COMPANY.webp`

### S12 — Service Area Bento (Map, White/Background bg)
- **Label badge**: "Primary Service Region" (orange pill) + Colter mascot avatar (`JCC-roofing-pet-Colter-Surprised.webp`)
- **H2 (small, slate)**: "Serving The Greater Houston Area"
- **Display text (large, on-surface)**: "Colter Jose & the JC&C Roofing Team"
- **Right side text**: "Ensuring durable, high-quality roofing solutions across the Greater Houston area with over a decade of local authority."
- **Map Column (`lg:col-span-7`)**: White card, dot-grid bg pattern
  - **Map image**: `https://www.myroofimprovement.com/wp-content/uploads/2026/05/HoustonMapArea.webp` (`mix-blend-multiply opacity-80`)
  - **4 Interactive Pins** (absolute positioned, show label on hover):
    - **Central Houston** — Orange `bg-secondary` + `animate-pulse` — position: `top-50% left-50%`
    - **West & Southwest** — Blue `bg-primary` — position: `top-60% left-35%`
    - **North & The Woodlands** — Green `bg-emerald-500` — position: `top-30% left-55%`
    - **East & Southeast** — Indigo `bg-indigo-500` — position: `top-65% left-70%`
  - **County pills (below map)**: Harris County | Fort Bend County | Montgomery County | Brazoria County | Waller County
- **Region Cards Column (`lg:col-span-5`)**:
  - **Central Houston** (orange left border) — Neighborhoods: Downtown, The Heights, Montrose, River Oaks
  - **West & Southwest** (blue left border) — Neighborhoods: Katy, Sugar Land, Sienna, Memorial Villages, Richmond
  - **North & The Woodlands** (green left border) — Neighborhoods: Tomball & The Woodlands, Spring, Cypress, Klein, Conroe, Champions
  - **East & Southeast** (indigo left border) — Neighborhoods: Pearland, Friendswood, Humble, Atascocita, Kingwood
- **Footer Banner (dark bg `#213145`)**: "Full Houston Coverage" — "JC&C Roofing is licensed, bonded, and insured to operate across all Houston municipalities. 24/7 emergency response in every listed service area." CTA: `View Service Areas` (orange) → `service-areas/`. Fine print: "Local Authority • BBB A+ Rated"

### S13 — Expertise & 3 Badges (Surface-container-low bg)
- **H2**: "Houston's Go-To Roofing Experts | Trusted Since 2013"
- **Subtitle**: "As Houston's premier roofing contractor, we deliver excellence backed by credentials that less than 2% of roofing companies in America can claim."
- **3-Card Layout** (center card is elevated/scaled):
  - **Left — GAF Master Elite** (white card, `lg:my-8`):
    - Logo: `GAF-Master-Elite-logo.webp`
    - H3: "GAF Master Elite Contractor"
    - Body: "Houston's go-to roofing experts hold this elite distinction awarded to only 2% of roofing contractors nationwide..."
    - Badges: "Top 2% Nationwide" | "Factory Certified"
  - **Center — Fortis Integrated Roof System** (dark `#213145`, scaled up, `border-4 border-primary-container`):
    - Logo: `Fortis-Warranty.webp`
    - H3: "Fortis Integrated Roof System"
    - Body: "As Houston's go-to roofing experts, we install 21+ premium components using our proven Fortis system..."
    - Badges: "21+ Premium Components" | "Climate-Tested Design"
  - **Right — BBB A+** (white card, `lg:my-8`):
    - Logo: `BBB-.png`
    - H3: "12+ Years, 0 Customer Complaints"
    - Body: "Houston's go-to roofing experts maintain a perfect BBB A+ rating with zero complaints since 2013..."
    - CTA: "Verify Our Perfect BBB Record →"

### S14 — Home Improvement CTA (White bg, full-width split card)
- **Left side (blue `#006098` bg)**:
  - Label: "Your Home, Our Commitment"
  - **H2**: "Ready to Start Your Houston Home Improvement Project?"
  - **Body**: "Contact us today for a free, no-obligation estimate on any of our services."
  - **CTAs**: `Call (713) ROOFING Now` (orange `#F16223`) → `tel:+17137663464` | `Get Free Estimate` (white outline) → `contact-us/`
  - Trust row: ✔ FREE ESTIMATES | ✔ NO PRESSURE | ✔ LOCAL EXPERTS | ✔ LICENSED & INSURED
- **Right side**: Image `Most-trusted-company-Houston.webp` (full-cover)

### S15 — Why Houston Homeowners Choose Us (Surface-container-low bg)
- **Label**: "Why Choose Us"
- **H2**: "Why Houston Homeowners Choose Their Go-To Roofing Experts"
- **Video Link**: `youtu.be/3TkbD-GUtUc` → "Video Showcase" (play icon)
- **4 Feature Cards (2×2 grid)**:
  1. **Peace of Mind Guaranteed** (blue `#007abf` bg, white text) — `verified_user` icon
  2. **Family-Owned Excellence** (white card) — `cloud_done` icon
  3. **Local Climate Experts** (white card) — `public` icon
  4. **Honest No-Pressure Service** (primary blue bg) — `folder_shared` icon

### S16 — Stats Hero (Blue gradient `#4481eb → #04befe`)
- **H2**: "The following is the latest data related to JC&C Roofing"
- **4 Stats (2×2 → 4-col)**:
  - `15+` / Years Houston Experience
  - `100%` / Customer Satisfaction
  - `5.0★` / Go-To Expert Rating
  - `0` / BBB Complaints

### S17 — Work Process / 4 Steps (White bg)
- **Badge**: "OUR WORK PROCESS"
- **H2**: "The JC&C Roofing Process: **Simple & Stress-Free**"
- **4 Steps** (connected by horizontal line on desktop, numbered badges 01–04):
  1. **Free Inspection & Estimate** — "We conduct a thorough roof inspection, provide a detailed estimate, and answer all your questions with no pressure." Tags: Video Inspection, Transparent Pricing
  2. **Customized Plan & Materials** — "We design a solution tailored to your roof, select premium materials, and handle all paperwork, including insurance claims assistance." Tags: Insurance Help, Financing Options
  3. **Expert Installation & Repair** — "Our certified crew executes the work with precision, maintaining a clean worksite and completing most projects in 1-2 days." Tags: GAF Master Elite Crew, Clean Worksite
  4. **Final Inspection & Warranty** — "We conduct a final quality check, provide warranty documentation, and ensure you're 100% satisfied with the results." Tags: Quality Assurance, Lifetime Warranty

### S18 — Emergency 365 Days (Primary blue bg)
- **Badge**: "365 DAYS EMERGENCY ROOF REPAIR SERVICE • HOUSTON'S GO-TO EXPERTS"
- **H2**: "Emergency Roof Repair Near Me — Houston's 365 Days Crisis Response Team"
- **Body**: "When storm damage strikes or leaks threaten your home, emergency roof repair near me becomes your top priority..."
- **3 Cards (white)**:
  1. ⚡ **Storm Damage Emergency** — "Emergency roof repair for hail, wind, and hurricane damage..." Tags: Hail Damage, Wind Damage, Insurance Help
  2. 🔍 **Roof Leak Detection & Repair** — "Advanced roof leak detection and immediate leaky roof repair services..." Tags: Leak Detection, Water Damage, Mold Prevention
  3. 🏗️ **Structural Roof Emergency** — "Critical urgent roof repairs for sagging roofs, collapsed sections..." Tags: Structural Repair, Safety First, Emergency Stabilization
- **CTA**: `(713) ROOFING - Call 24/7` (orange button, call icon)

### S19 — Emergency Warning Signs (White bg)
- **Badge**: "⚠️ DON'T IGNORE THESE EMERGENCY ROOF WARNING SIGNS"
- **H2**: "When to Call for Emergency Roof Repair"
- **Subtitle**: "If you notice any of these signs, immediate emergency roof repair near me could prevent thousands in water damage..."
- **4 Warning Cards** (light colored):
  1. **Active Water Leaks** (light blue bg) — "Visible water dripping, running down walls, or pooling on ceilings..."
  2. **Sagging Roof Deck** (primary blue bg, white text) — "Visible dips or sagging indicates structural failure needing urgent roof repairs to prevent collapse."
  3. **Post-Storm Damage** (dark blue `#004a77` bg, white) — "Missing shingles, visible holes, or debris damage after storms requires immediate storm damage repair."
  4. **Interior Water Stains** (darkest `#0b1c30` bg, white) — "New or expanding ceiling stains indicate active leaks needing roof leak detection and repair."
- **Urgency Banner** (below cards): Expert photos (Todd, Colter/Jose), "Remember: Every hour of delay can increase water damage costs by hundreds of dollars. Call Houston's emergency roof repair experts immediately at:" CTA: `(713) ROOFING` (orange button)

### S20 — Residential Roof Repair Detailed (Surface-container-low bg)
- **Badge**: "🏠 RESIDENTIAL ROOF REPAIR"
- **H2**: "Residential Roof Repair Service | Houston Roof Repair Experts"
- **Body**: "Recognized as Houston's most reliable roofing company for honest roof repairs and expert roof leak detection. We're committed to education, transparency, and long-term customer relationships."
- **Left image**: `roof-insurance-claim-houston.webp` with floating "99% Satisfied" SVG circle badge
- **3 Feature Cards (stacked)**:
  1. **Insurance Claim Assistant** (highlighted, green check icon) — "Expert guidance through the claims process"
  2. **Leaky Roof Repair Specialist** (glass bg) — "Expert diagnosis and permanent fixes for leaks of all sizes."
  3. **5-Star Customer Reviews** (glass bg) — "Consistent excellence in roof repair and complete roof replacement."
- **CTAs**: `📅 Schedule Repair Consultation →` (orange) | `Emergency Call` (blue outline)

### S21 — Comprehensive Solutions Tabs Overview (White bg)
- **Badge**: "HOUSTON'S TRUSTED ROOFING EXPERTS"
- **H2**: "Comprehensive Roofing Solutions for Houston Homeowners"
- **Subtitle**: "Whether you need a minor repair, complete replacement, storm damage assistance, or flexible financing, we have the expertise..."
- **4 Tab Cards** (first active=blue, rest white):
  1. 🏠 **Residential Repair** — "Leak detection & expert fixes"
  2. 🔄 **Roof Replacement** — "Complete 1-2 day installations"
  3. 🌪️ **Storm & Insurance** — "Damage assessment & claims"
  4. 💰 **Financing Options** — "Flexible payment plans"

### S22 — Honor Our Heroes — $250 Discount (Surface-container-low bg)
- **Badge**: "🇺🇸 Honoring Our Heroes"
- **H2**: "$250 Discount for Military, First Responders, Teachers & Nurses"
- **Subtitle**: "At JC&C Roofing Company, we believe in giving back to those who dedicate their lives to serving others. Your service inspires us every day."
- **4 Hero Cards** (white, `rounded-[2rem]`, blue ribbon badge top-right):
  1. **Military Personnel** [PROUD VETERAN badge] — Image: `ToddPic.webp` — "For your bravery and sacrifice in protecting our freedom. Active duty and veterans welcome." CTA: `$250 DISCOUNT` (orange)
  2. **First Responders** [ER DOCTOR badge] — Image: `First-responders-saving-lives-scaled.webp` — "For running toward danger when others run away. Police, Fire, EMT, and all emergency personnel." CTA: `$250 DISCOUNT`
  3. **Teachers** [35 YEARS badge] — Image: `Teachers-making-a-difference-scaled.webp` — "For shaping the minds of future generations, often with little recognition..." CTA: `$250 DISCOUNT`
  4. **Nurses** [BOTH NURSES badge] — Image: `Nurses-saving-lives-everyday-scaled.webp` — "We can never forget the gratitude we owe to our nurses. True heroes during the pandemic and always." CTA: `$250 DISCOUNT`
- **"How to Claim Your Discount" box** (white `rounded-[3rem]` with decorative circle):
  - **3 Steps**:
    1. **Schedule Your Inspection** — "Call us or request an appointment online for a free roof inspection."
    2. **Verify Your Status** — "Provide proof of service (ID, badge, pay stub, etc.) when you get your estimate."
    3. **Receive Your Discount** — "The $250 will be deducted from your final invoice when you purchase your new roof."
  - Quote: "Thank you for all you do! We're honored to serve those who serve our community."
  - **CTAs**: `Call (713) ROOFING` (orange) | `Schedule Online` (blue outline)

### S23 — Testimonials (White/Surface bg)
- **Left — 2 Overlapping Review Cards** (rotate + spread on hover):
  - **Card 1**: "Excellent service" — "This company did an outstanding job and the customer service was EXCEPTIONAL..." — Rosalyn R, Verified Homeowner ⭐⭐⭐⭐⭐
  - **Card 2**: "Amazing team" — "Amazing team, I have used them twice and will again... Professional, honest, and truly Houston's best." — Jeff J, Verified Homeowner ⭐⭐⭐⭐⭐
- **Right — Dark blue box `#003459`** (dot-grid bg):
  - Label: "TESTIMONIALS" (sky-400)
  - **H2**: "Hear It From **Our Clients**"
  - **Body**: "Don't just take our word for it. Read real reviews from hundreds of satisfied Houston homeowners who have experienced the JC&C difference."
  - **3 Trust Cards** (cascading layout, last card overflows into next section):
    - Google: `4.8` rating, "Read 400+ Reviews"
    - BBB Center (tallest/elevated): `100%` BBB Complaint-Free, "12+ years with zero complaints", "✅ Perfect Record" badge
    - BBB Right: `A+` BBB Rating, "View Profile →"

### S24 — Warranties (Surface-container-low bg)
- **H2**: "Guaranteed Workmanship & Roof Protection Warranties"
- **Subtitle**: "Your peace of mind is our priority. We stand behind our work with industry-leading warranties and guarantees."
- **3 Warranty Cards**:
  1. **Guaranteed Leak Repair Warranty — 5 Years** (white) — `verified_user` icon — "If your roof leaks due to installation errors within the first 5 years, we'll fix it within 24 hours and cover any ceiling damage within 48 hours." Tags: 24-Hour Response, Damage Coverage
  2. **Customer Satisfaction Guarantee — $250** (primary blue bg, highlighted center) — `handshake` icon — "If we fail to meet expectations with our service or communication, we will compensate you $250.00 for the inconvenience." Tags: Risk-Free, Money-Back Promise
  3. **Manufacturer-Certified Roof Installations** (white) — `military_tech` icon — "Manufacturers back our warranties for long-term peace of mind. We are proud GAF Master Elite and Fortis Warranty certified." Tags: Top 2% Elite, Lifetime Protection
- **Detail Row (3-col white card)**:
  - **Workmanship Warranty**: "Covers installation errors and craftsmanship issues. Includes our industry-leading 5-year leak repair warranty for total protection."
  - **Manufacturer Warranty**: "Covers defects in roofing materials. As a GAF Master Elite contractor, we provide enhanced manufacturer warranties that others cannot."
  - **Transferable Coverage**: "Many of our warranties can be transferred to new homeowners, significantly adding to your property's resale value..."

### S25 — FAQ Accordion (White bg)
- **H2**: "Your Houston Roofing Questions, Answered"
- **Subtitle**: "Get expert answers to the most common questions we hear from homeowners in Houston, The Woodlands, Katy, and surrounding areas."
- **Filter Pills** (`#faq-filters`): All Questions | ⛈️ Storm Damage | 📋 Insurance | 💰 Cost & Pricing | 🔨 Installation
- **6 Accordion Items** (`#faq-accordion`, JS: expand/collapse with max-height, rotate icon):
  1. [storm-damage] "What are the signs I need a roof replacement after a Texas storm?" — Missing/cracked shingles, granule loss, leaks, dents, visible daylight. Expert Tip: "After any major storm, schedule a free inspection."
  2. [cost-pricing] "How much does a new roof cost in Houston?" — Pricing grid: $8k-$12k (Basic) | $12k-$20k (Premium) | $15k-$30k+ (Metal). "Offers transparent pricing with no hidden fees and flexible financing."
  3. [storm-damage, installation] "What is the best type of roof for Houston's climate and storms?" — Best: Impact-resistant architectural (Class 4). Most Durable: Metal roofing. List: Class 4 shingles, metal, ventilation, underlayment.
  4. [storm-damage, insurance] "How do I handle a roof insurance claim in Texas?" — 4-step visual: 1. Free Inspection → 2. File Claim → 3. Adjuster Meeting → 4. Approval & Repair.
  5. [installation] "How long does a roof replacement take in Houston?" — "1-2 Days Typical" highlight box. Factors: size, weather, materials, additional repairs.
  6. [storm-damage] "Do you offer free roof inspections in Houston?" — "Yes! Completely Free & No-Obligation" (green box). Includes: visual assessment, drone/ladder, photo/video, written report, repair recommendations. CTA: `Schedule Free Inspection` (orange)

### S26 — Education Slider (Surface-container-low bg)
- **H2**: "Continue Your Roofing Education"
- **Subtitle**: "Read our latest expert articles to make informed decisions about your Houston roof."
- **Slider** (`#education-slider`, horizontal scroll, snap, `no-scrollbar`):
  - **Card 1**: Image `low-slope-roof-tpo-system.webp` | Tag: Maintenance | Dec 22, 2025 | 4 min | Title: "Essential Roof Maintenance Checklist for Houston Homes" | "Prevent costly repairs with our seasonal roof maintenance checklist designed specifically for Houston's climate."
  - **Card 2**: Image `Houstons-roof-repair-company.webp` | Tag: Insurance | Nov 17, 2025 | 6 min | Title: "A To-Do List Before Hiring Roofers After Your Claim Is Approved" | "Your insurance claim is approved—now what?"
  - **Card 3**: Image `hiring_roofer_blog.png` | Tag: Guide | Nov 17, 2025 | 7 min | Title: "Make An Informed Decision: A Checklist Before Hiring A Roofer" | "Don't hire the wrong roofer!"
- **Slider Nav Buttons**: `chevron_left` / `chevron_right` (white circle, primary on hover) — scroll 400px

### S27 — KPRC2 Media Feature (Inside S26 section wrapper)
- **Label**: "As Seen On KPRC2" (orange)
- **H2**: "Is Your Insurance Company **Canceling Your Policy** Because of Your Roof?"
- **Body**: "Jennifer and Christian Hernandez, Houston's most trusted roofing experts, recently joined KPRC2's Amy Davis to discuss why insurance companies are dropping homeowners and what you can do to protect your investment."
- **Floating badge** (top-right, dark `#002a4a`): "KPRC2" / "Ask Amy" (sky-400) / animated pulse bar
- **YouTube iframe**: `https://www.youtube-nocookie.com/embed/gnV7iKzCZjE` (aspect-video, `rounded-[2.5rem]` frame)
- **Checkmarks (2×2 grid)**: Cancellation Prevention | Expert Advice | Documentation Tips | Strategic Decisions
- **Progress bar**: "Homeowner Protection Score" → `95%` (orange bar)
- **Expert avatars**: Jennifer & Christian H. (Owners & Experts)

---

## 5. Footer (`bg-[#0b1c30]`)

### Map Section
- `zeemaps.com/pub?group=6771554` iframe — `h-400px`, `border-radius: 20px`
- **Floating Logo Overlay** (centered, overlapping map bottom): `w-24 h-24 md:w-32 md:h-32` white circle — `JCC-Roofing-Company-in-Houston-Main-New-Logo-1024x1024.webp`

### Description
- P1: "Locals trust us as their **go-to certified roofers** in the Greater Houston area — including Tomball, The Woodlands, Klein, and all of North Houston. We deliver permanent roofing solutions for every homeowner with **same-day appointments**, free roof inspections, and fair-priced repairs, including emergency leak fixes. Our 1-day roof installations minimize disruption to your family."
- P2: "Choose **JC&C Roofing Company**, Houston's most trusted local roofer since 2013. With a 15-year track record, we fix roof leaks right the first time. *Our promise: if the problem returns, so will we.*"

### 4-Column Links Grid
| Our Company & Resources | Services | Office Hours | Contact |
|---|---|---|---|
| About Us | Roof Repair | Support: Mon–Sun 24/7 | **Phone**: (713) 766-3464 |
| Careers | Roof Replacement | Mon–Fri: 8AM–6PM | Direct: 281-498-7663 |
| Blog | Roof Financing | Sat–Sun: By appt. | Text: 832-590-3700 |
| Roofing FAQs | Roof Maintenance | **Main Office**: 1431 Graham Dr #266, Tomball TX 77375 | Email: hello@jccroofing.com |
| #ROOF4BRAVES | Roof Inspections | **Houston Office**: 1220 Blalock Rd #145, Houston TX 77055 (By Appt.) | 🚨 24/7 Emergency Service (green pulse dot) |
| Roof Replacement Cost Estimate | Insurance Claims | | |
| Roof Repair Cost Guide | Emergency Roof Repairs | | |

### Footer Bottom
- © 2026 JC&C Roofing Company. All Rights Reserved. Houston's Trusted Local Roofer.
- Links: Accessibility Statement | Privacy Policy | Terms of Service

---

## 6. Modals & Interactive JS Logic

### Calculator Modal (`#calculator-modal`)
- Triggered by: `#jcc-calculator-trigger` buttons (multiple on page)
- Content: iframe → `https://app.roofr.com/...` (Roofr calculator embed)
- Close: click outside or X button

### Support Modal (`#support-modal`)
- Triggered by: `#support-modal-trigger` (header agent icon)
- Options: Call (713) ROOFING | Internal Calculator | External Roofr Calculator

### FAQ Accordion JS
- `querySelectorAll('#faq-accordion > div')` → click `.faq-button` → toggle `content.style.maxHeight` + rotate icon
- Filter buttons: toggle `data-categories` visibility via `item.style.display`

### Solutions Tabs JS (`#solutions-tabs`)
- Tab data object with: `title`, `description`, `bullets`, `cta`, `ctaLink`, `image`
- Click `.tab-btn` → update `#tab-title`, `#tab-description`, `#tab-bullets`, `#tab-cta`, `#tab-image`
- Tabs: repair | replacement | storm | financing

### Mobile Menu JS
- `#mobile-menu-trigger` → adds `flex` to `#mobile-menu`, animates backdrop opacity + panel `translate-x`
- `#mobile-menu-close` / backdrop click → reverse animation → `hidden`

