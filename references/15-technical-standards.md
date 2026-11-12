# RENDER BEAST — Technical Standards
# Production Specifications for All Four Engines

---

## IMAGE TECHNICAL STANDARDS

### Resolution Standards

| Use Case | Minimum Resolution | Recommended | DPI |
|---|---|---|---|
| Web hero image | 1920 × 1080 | 2560 × 1440 | 72 |
| Social square | 1080 × 1080 | 1500 × 1500 | 72 |
| Social portrait | 1080 × 1350 | 1440 × 1800 | 72 |
| Stories / Reels | 1080 × 1920 | 1440 × 2560 | 72 |
| YouTube thumbnail | 1280 × 720 | 1920 × 1080 | 72 |
| Blog/article image | 1200 × 630 | 2000 × 1050 | 72 |
| App icon | 1024 × 1024 | 1024 × 1024 | 72 |
| Print A4 | 2480 × 3508 | 3508 × 4961 | 300 |
| Print A3 | 3508 × 4961 | 4961 × 7016 | 300 |
| Print A2 | 4961 × 7016 | 7016 × 9933 | 300 |
| Billboard small | 3000 × 1500 | 4000 × 2000 | 150 |
| Billboard large | 10000 × 4000 | 15000 × 6000 | 150 |

### Color Space Standards

**sRGB (IEC 61966-2-1)**
- Standard for web and digital delivery
- Maximum compatibility across displays
- Use for: web, social media, email, screen-only use

**Display P3 (DCI-P3 with D65 white point)**
- Wider gamut — covers approximately 25% more colors than sRGB
- Use for: Apple device optimization, iOS apps, Safari-delivered content, modern iPhone photography
- Fallback: Always provide sRGB version as well

**Adobe RGB (1998)**
- Professional photography standard
- Wider gamut than sRGB, narrower than P3
- Use for: professional photography workflow, print pre-press

**CMYK (various profiles)**
- Required for offset printing
- Never deliver sRGB for professional print without converting
- Coated stock: Coated Fogra 39 / SWOP v2
- Uncoated stock: Uncoated Fogra 29
- Always convert from RGB profile; do not leave as uncalibrated CMYK

### File Format Guide

| Format | Use When | Avoid When | Key Properties |
|---|---|---|---|
| **PNG** | Transparency needed; lossless required; graphics with text | Photos (file too large) | Lossless, transparency support, large files |
| **JPG/JPEG** | Photographs for web/digital; smaller file size needed | Transparency needed; text-heavy graphics | Lossy compression, no transparency, quality 85-95 for web |
| **WebP** | Modern web delivery; best quality-to-size ratio | Older browsers needed; printing | Lossless or lossy, transparency, excellent compression |
| **AVIF** | Next-gen web delivery | Wide browser support needed | Better than WebP, excellent compression, broad color |
| **TIFF** | Print masters; professional photography archive | Web delivery | Lossless, large, professional standard |
| **PSD** | Layered Photoshop files; design handoff | Web delivery; non-Adobe users | Layered, requires Photoshop or compatible |
| **SVG** | Logos; icons; scalable graphics | Complex photographs | Vector, infinitely scalable, small size |
| **EPS/AI** | Print graphics; vector logos | Web display | Vector, print-ready, requires compatible software |

### Compression Standards

**JPEG quality levels**:
- 100: Lossless equivalent (no visible compression) — archive use only
- 90-95: High quality — print proofing
- 80-90: Web high quality — large display images
- 70-80: Web standard — typical use
- 60-70: Compressed — thumbnails, low-priority images

**WebP quality levels**:
- 90-100: Lossless mode
- 80-90: High quality web
- 70-80: Standard web

**PNG optimization**:
- Use `pngquant` for PNG-8 conversion (lossy compression, 60-80% size reduction)
- Use `oxipng` for lossless PNG optimization
- Use `sharp` or `Squoosh` for batch processing

---

## VIDEO TECHNICAL STANDARDS

### Resolution Standards

| Format | Resolution | Aspect Ratio | Use Case |
|---|---|---|---|
| HD 720p | 1280 × 720 | 16:9 | Social clips, preview, low bandwidth |
| Full HD 1080p | 1920 × 1080 | 16:9 | Standard delivery, YouTube, Instagram |
| 2K DCI | 2048 × 1080 | 17:9 | Cinema, high-quality production |
| 4K UHD | 3840 × 2160 | 16:9 | Premium, future-proofing, platform maximum |
| 4K DCI | 4096 × 2160 | 17:9 | Cinema production |
| 8K UHD | 7680 × 4320 | 16:9 | Archival, specialized use |
| Stories vertical | 1080 × 1920 | 9:16 | Instagram Stories, TikTok, Reels |
| Square | 1080 × 1080 | 1:1 | Instagram feed, some social |

### Frame Rate Guide

| FPS | Use Case | Feel |
|---|---|---|
| 23.976 (24p) | Cinematic standard, film, narrative | Cinematic, dramatic |
| 25p | European broadcast (PAL), streaming | Smooth broadcast |
| 29.97 (30p) | North American broadcast, YouTube, general | Standard digital |
| 48p | High frame rate cinema (HFR) | Hyperrealistic, smooth |
| 50p | European high-frame broadcast | Smooth, sports |
| 59.94 (60p) | Action, sports, gaming, YouTube | Very smooth, gaming |
| 120p | Slow motion (4× when played at 30p) | Dramatic slow motion |
| 240p | Extreme slow motion (8× at 30p) | Ultra slow, specialized |

**Slow motion calculation**: Shoot at high FPS, play at target FPS.
- 120fps played at 30fps = 4× slow motion
- 240fps played at 30fps = 8× slow motion

### Color Grading Standards

**Rec.709 (BT.709)**
- Standard for HD broadcast and streaming
- SDR (Standard Dynamic Range)
- Use for: YouTube, Instagram, Vimeo, most delivery

**Rec.2020 (BT.2020)**
- UHD broadcast, HDR
- Wider color gamut than Rec.709
- Use for: HDR delivery, Netflix, Apple TV+, Amazon

**DCI-P3**
- Digital cinema standard
- Use for: theatrical release, high-end streaming

**S-Log / Log formats** (Sony, RED, ARRI, etc.)
- Flat, desaturated recording that preserves maximum dynamic range
- Must be color graded — raw log footage is not a deliverable
- Provides headroom for creative grading

### Codec Guide

| Codec | Container | Use When |
|---|---|---|
| H.264 / AVC | MP4, MOV | Standard web delivery; maximum compatibility |
| H.265 / HEVC | MP4, MOV | Smaller files at same quality as H.264; modern platforms |
| ProRes 422 | MOV | Production master; editing proxy |
| ProRes 4444 | MOV | Master with alpha channel |
| AV1 | MP4, WebM | Next-gen web; YouTube, Netflix; best quality-to-size |
| VP9 | WebM | Google/YouTube optimization |
| DNxHD/HR | MXF, MOV | Avid-based workflows |

### Bitrate Requirements

| Resolution | H.264 (web) | H.265 | ProRes 422 |
|---|---|---|---|
| 720p 30fps | 5–8 Mbps | 3–5 Mbps | ~220 Mbps |
| 1080p 30fps | 8–15 Mbps | 5–10 Mbps | ~422 Mbps |
| 1080p 60fps | 15–25 Mbps | 10–15 Mbps | ~630 Mbps |
| 4K 30fps | 35–60 Mbps | 20–40 Mbps | ~1700 Mbps |
| 4K 60fps | 60–100 Mbps | 40–70 Mbps | ~2500 Mbps |

### Audio Specifications

| Setting | Standard | Broadcast |
|---|---|---|
| Sample Rate | 48,000 Hz | 48,000 Hz |
| Bit Depth | 24-bit | 24-bit |
| Channels | Stereo (2.0) | 5.1 or 7.1 |
| Codec | AAC (web), WAV/AIFF (master) | Dolby Digital / DTS |
| Loudness | -14 LUFS (streaming), -23 LUFS (broadcast) | -24 LUFS EBU R128 |
| Peak | -1 dBTP True Peak | -1 dBTP True Peak |

### Export Specifications by Platform

| Platform | Resolution | FPS | Format | Max File Size | Audio |
|---|---|---|---|---|---|
| YouTube | Up to 4K | Up to 60fps | MP4 H.264 or H.265 | 256GB | AAC 384kbps |
| Instagram Feed | 1080p | 30fps | MP4 H.264 | 650MB | AAC 128kbps |
| Instagram Reels | 1080×1920 | 30fps | MP4 H.264 | 650MB | AAC 128kbps |
| TikTok | 1080×1920 | 30fps | MP4 H.264 | 500MB | AAC |
| LinkedIn | 1080p | 30fps | MP4 H.264 | 5GB | AAC |
| Twitter/X | 1080p | 60fps | MP4 H.264 | 512MB | AAC |

---

## 3D TECHNICAL STANDARDS

### File Format Guide

| Format | Description | Best For |
|---|---|---|
| **GLTF/GLB** | GL Transmission Format (binary=GLB) | Web, AR, universal, modern standard |
| **FBX** | Autodesk Film Box | Animation, game engines, interop |
| **OBJ** | Wavefront Object | Simple geometry interchange, legacy |
| **USDZ** | Universal Scene Description (Zipped) | Apple AR, iOS Quick Look |
| **USD/USDA/USDC** | Universal Scene Description | Film/VFX pipeline, Omniverse |
| **ABC (Alembic)** | Point cache format | Complex animation bake |
| **STL** | Stereolithography | 3D printing only |
| **3MF** | 3D Manufacturing Format | Modern 3D printing |
| **DAE (Collada)** | COLLADA | Legacy interop |

### Polygon Budget by Use Case

| Context | Recommended Budget | Maximum | Notes |
|---|---|---|---|
| Mobile game hero | 2,000–5,000 tris | 10,000 | Includes LODs |
| Mobile game environment object | 500–2,000 tris | 5,000 | Needs LOD chain |
| Desktop game hero | 10,000–30,000 tris | 60,000 | With LODs |
| Desktop game vehicle | 20,000–50,000 tris | 80,000 | |
| VR/AR asset | 5,000–15,000 tris | 30,000 | Performance critical |
| Arch-viz (real-time) | No hard limit | Performance tested | EEVEE/Unreal |
| Film VFX hero | 1–10M tris | Unlimited | With subdivision |
| Three.js web simple | 1,000–5,000 tris | 20,000 | 60fps on average GPU |
| Three.js web complex scene | 5,000–50,000 total | 100,000 total | Manage per-object |

### Texture Resolution Standards

| Asset Type | Standard | High Quality | Notes |
|---|---|---|---|
| Mobile game | 512–1024 | 2048 | Compressed in engine |
| Desktop game | 2048 | 4096 | Depends on asset size |
| Film/visualization | 4096 | 8192+ | Unlimited for hero |
| Web (Three.js) | 512–1024 | 2048 | Affects load time significantly |
| AR (USDZ) | 1024–2048 | 4096 | Apple guidelines |

**Always use power-of-2 dimensions**: 256, 512, 1024, 2048, 4096, 8192

### PBR Workflow Specifications

**Metalness/Roughness Workflow (GLTF, Three.js, Unreal, Unity URP)**
- Base Color (RGB): Diffuse color for non-metals; for metals, reflected color
- Metalness (Grayscale): 0 = non-metal, 1 = full metal
- Roughness (Grayscale): 0 = mirror smooth, 1 = fully diffuse
- Normal (RGB): Tangent-space normals
- Occlusion (R channel): Ambient occlusion
- Emissive (RGB): Self-emission

**Specular/Glossiness Workflow (Blender legacy, some engines)**
- Diffuse (RGB): Base color
- Specular (RGB): Specular color
- Glossiness (Grayscale): 0 = rough, 1 = mirror
- Normal (RGB): Tangent-space normals

### UV Layout Requirements

- UV islands must be within 0–1 UV space for primary texture set
- No overlapping UVs (causes texture seams)
- Island padding: minimum 2px at target texture resolution
- Straighten edges where appropriate (reduce texture waste)
- Maximize UV space utilization (minimize wasted UV area)
- Direction-consistent: UV grid should align with surface flow

### LOD Specifications

LOD0 (highest): Full geometry — used at close distance
LOD1: 50% of LOD0 triangles
LOD2: 25% of LOD0 triangles
LOD3: 10% of LOD0 triangles
LOD4 (optional): Impostor billboard — used at extreme distance

---

## WEB TECHNICAL STANDARDS

### Responsive Breakpoints

```css
/* Mobile first — base styles apply to mobile */
/* xs */ @media (min-width: 320px) { }  /* Small phones */
/* sm */ @media (min-width: 375px) { }  /* Standard phones */
/* md */ @media (min-width: 768px) { }  /* Tablets */
/* lg */ @media (min-width: 1024px) { } /* Large tablets / small desktops */
/* xl */ @media (min-width: 1280px) { } /* Standard desktops */
/* 2xl*/ @media (min-width: 1536px) { } /* Large desktops */
```

### Performance Budgets (Core Web Vitals)

| Metric | Good | Needs Improvement | Poor | Measurement |
|---|---|---|---|---|
| LCP (Largest Contentful Paint) | ≤ 2.5s | 2.5–4.0s | > 4.0s | Mobile 4G |
| FID (First Input Delay) | ≤ 100ms | 100–300ms | > 300ms | Real user data |
| INP (Interaction to Next Paint) | ≤ 200ms | 200–500ms | > 500ms | Replaces FID |
| CLS (Cumulative Layout Shift) | ≤ 0.1 | 0.1–0.25 | > 0.25 | Per page |
| TTFB (Time to First Byte) | ≤ 800ms | 800ms–1.8s | > 1.8s | Server metric |
| FCP (First Contentful Paint) | ≤ 1.8s | 1.8–3.0s | > 3.0s | Perceived load |

**JavaScript bundle budget**:
- Initial load: ≤ 150KB (gzipped)
- Total (all JS): ≤ 500KB (gzipped)
- Each route chunk: ≤ 100KB

**Image budget**:
- Hero image: ≤ 100KB (WebP)
- Content image: ≤ 50KB
- Thumbnail: ≤ 20KB
- Use `srcset` and `sizes` for responsive images

### Security Headers

```nginx
# Nginx example
add_header Content-Security-Policy "default-src 'self'; script-src 'self' 'unsafe-inline' (approved CDNs); style-src 'self' 'unsafe-inline' (approved CDNs); img-src 'self' data: https:; font-src 'self' https://fonts.gstatic.com; connect-src 'self';";
add_header X-Frame-Options "SAMEORIGIN";
add_header X-Content-Type-Options "nosniff";
add_header Referrer-Policy "strict-origin-when-cross-origin";
add_header Permissions-Policy "camera=(), microphone=(), geolocation=()";
add_header Strict-Transport-Security "max-age=31536000; includeSubDomains; preload";
```

### Browser Compatibility Requirements

**Minimum support (without polyfill)**:
- Chrome 90+ (desktop and Android)
- Firefox 88+
- Safari 14+ (macOS and iOS)
- Edge 90+
- Samsung Internet 14+

**Progressive enhancement**: Core functionality must work without JavaScript. Progressive enhancement layers JS for enhanced experience.

### SEO Technical Requirements

```html
<!-- Essential meta tags -->
<title>[Page Title | Brand Name]</title> <!-- 50-60 characters -->
<meta name="description" content="[150-160 character description]">
<link rel="canonical" href="[page URL]">

<!-- Open Graph (Facebook, LinkedIn) -->
<meta property="og:title" content="[Title]">
<meta property="og:description" content="[Description]">
<meta property="og:image" content="[1200x630 image URL]">
<meta property="og:url" content="[Page URL]">
<meta property="og:type" content="website">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="[Title]">
<meta name="twitter:description" content="[Description]">
<meta name="twitter:image" content="[Image URL]">

<!-- Structured Data (JSON-LD) -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "[Brand Name]",
  "url": "[Website URL]"
}
</script>
```

**Robots.txt** must exist and correctly declare crawlable paths.

**Sitemap.xml** must exist for sites with more than 5 pages.

**Core technical requirements**:
- HTTPS required (HTTP pages penalized in rankings)
- Mobile-friendly (required for mobile-first indexing)
- Page speed (Core Web Vitals affect ranking)
- No broken internal links
- No duplicate content
- Correct heading hierarchy (one H1 per page)
