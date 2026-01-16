# NCMS Schema Markup Implementation Guide

**Companion to:** Digital Presence Refresh - Strategic Recommendations
**Purpose:** Ready-to-use structured data code for AI search optimization
**Platform:** Squarespace (add via Code Injection or Code Block)

---

## What is Schema Markup?

Schema markup is code that helps search engines and AI systems understand your website content. It's invisible to visitors but makes your content machine-readable, improving your chances of appearing in:
- Google AI Overviews
- ChatGPT responses
- Perplexity answers
- Bing Copilot results
- Rich search results (FAQ dropdowns, event cards, etc.)

**Format:** All examples below use JSON-LD format, which Google recommends and Squarespace supports.

---

## How to Add Schema to Squarespace

### Site-Wide Schema (Organization, LocalBusiness)
1. Go to **Settings > Advanced > Code Injection**
2. Paste the code in the **Header** section
3. Save

### Page-Specific Schema (FAQ, Event, Course)
1. Edit the specific page
2. Add a **Code Block**
3. Paste the schema code
4. Set display to "hidden" or place at bottom of page
5. Save

### Validation
After adding schema, test at: https://validator.schema.org/ or https://search.google.com/test/rich-results

---

## 1. Organization + LocalBusiness Schema (Site-Wide)

**Add to:** Settings > Advanced > Code Injection > Header

This establishes NCMS as a recognized entity with location, contact info, and organizational details.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": ["MusicSchool", "LocalBusiness", "EducationalOrganization", "NonprofitOrganization"],
  "@id": "https://www.nashuacms.org/#organization",
  "name": "Nashua Community Music School",
  "alternateName": "NCMS",
  "description": "A 501(c)3 nonprofit music school creating innovative music programming accessible to all, serving Greater Nashua, New Hampshire for over 40 years.",
  "url": "https://www.nashuacms.org",
  "logo": {
    "@type": "ImageObject",
    "url": "https://www.nashuacms.org/path-to-logo.png"
  },
  "image": "https://www.nashuacms.org/path-to-main-image.jpg",
  "telephone": "+1-603-881-7030",
  "email": "info@nashuacms.org",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "2 Lock Street",
    "addressLocality": "Nashua",
    "addressRegion": "NH",
    "postalCode": "03060",
    "addressCountry": "US"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": 42.7654,
    "longitude": -71.4676
  },
  "areaServed": [
    {
      "@type": "City",
      "name": "Nashua",
      "containedInPlace": {
        "@type": "State",
        "name": "New Hampshire"
      }
    },
    {
      "@type": "Place",
      "name": "Greater Nashua, New Hampshire"
    }
  ],
  "serviceArea": {
    "@type": "GeoCircle",
    "geoMidpoint": {
      "@type": "GeoCoordinates",
      "latitude": 42.7654,
      "longitude": -71.4676
    },
    "geoRadius": "25 mi"
  },
  "foundingDate": "1985",
  "nonprofitStatus": "Nonprofit501c3",
  "slogan": "Creating innovative music programming accessible to all",
  "knowsAbout": [
    "Music Education",
    "Music Lessons",
    "Music Therapy",
    "Early Childhood Music",
    "Private Music Instruction",
    "Group Music Classes",
    "Summer Music Camps"
  ],
  "hasOfferCatalog": {
    "@type": "OfferCatalog",
    "name": "Music Programs",
    "itemListElement": [
      {
        "@type": "Offer",
        "itemOffered": {
          "@type": "Service",
          "name": "Private Music Lessons"
        }
      },
      {
        "@type": "Offer",
        "itemOffered": {
          "@type": "Service",
          "name": "Music Therapy"
        }
      },
      {
        "@type": "Offer",
        "itemOffered": {
          "@type": "Service",
          "name": "Summer Music Camps"
        }
      },
      {
        "@type": "Offer",
        "itemOffered": {
          "@type": "Service",
          "name": "Group Music Classes"
        }
      }
    ]
  },
  "sameAs": [
    "https://www.facebook.com/nashuacms",
    "https://www.instagram.com/nashuacms"
  ],
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"],
      "opens": "09:00",
      "closes": "20:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": "Saturday",
      "opens": "09:00",
      "closes": "17:00"
    }
  ],
  "priceRange": "$$",
  "paymentAccepted": ["Cash", "Credit Card", "Check"],
  "currenciesAccepted": "USD"
}
</script>
```

**Customize:** Update logo URL, image URL, social media links, email, and verify hours/coordinates.

---

## 2. FAQ Schema (High Priority Pages)

**Add to:** Programs page, New Student page, Scholarship page, Contact page

FAQ schema allows your Q&A content to appear directly in search results and be quoted by AI assistants.

### General FAQ (New Student / Get Started Page)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "What age can children start music lessons at NCMS?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Children can begin private lessons as early as age 5 for most instruments. We also offer early childhood music classes for ages 0-5, and programs for students of all ages through adulthood. The best starting age varies by instrument—contact us for personalized guidance."
      }
    },
    {
      "@type": "Question",
      "name": "Do I need to own an instrument to take lessons?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "No, you don't need to own an instrument to get started. We can recommend reputable rental programs and help you choose the right instrument. Some instruments are available to use during lessons at our facility."
      }
    },
    {
      "@type": "Question",
      "name": "How much do music lessons cost at NCMS?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Lesson rates vary based on lesson length (30, 45, or 60 minutes). We offer scholarships through The Community Fund for families who qualify—approximately 40% of our students receive some financial assistance. Contact us for current rates and scholarship information."
      }
    },
    {
      "@type": "Question",
      "name": "Does NCMS offer scholarships for music lessons?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes, NCMS awards over $85,000 in scholarships annually through The Community Fund. Approximately 40% of our students receive financial assistance. Scholarships are available for all programs including private lessons, group classes, and summer camps. Applications are accepted year-round."
      }
    },
    {
      "@type": "Question",
      "name": "What instruments can I learn at NCMS?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "NCMS offers instruction in over 15 instruments including piano, guitar, violin, viola, cello, voice, drums, flute, clarinet, saxophone, trumpet, trombone, ukulele, bass, and more. We also offer music theory, composition, and music therapy services."
      }
    },
    {
      "@type": "Question",
      "name": "How long has NCMS been in Nashua?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Nashua Community Music School has been serving Greater Nashua since 1985—over 40 years of music education in southern New Hampshire. We are a 501(c)3 nonprofit organization dedicated to making music accessible to all."
      }
    }
  ]
}
</script>
```

### Music Therapy FAQ

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "What is music therapy?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Music therapy is an evidence-based clinical practice where board-certified music therapists use music interventions to address physical, emotional, cognitive, and social needs. At NCMS, our MT-BC credentialed therapists work with clients of all ages to achieve non-musical therapeutic goals through music."
      }
    },
    {
      "@type": "Question",
      "name": "Does NCMS offer music therapy for seniors?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes, NCMS provides music therapy services for seniors both at our facility and at senior centers and healthcare facilities throughout Greater Nashua. Our board-certified music therapists work with older adults on goals related to memory, social engagement, motor skills, and emotional wellbeing."
      }
    },
    {
      "@type": "Question",
      "name": "Is music therapy covered by insurance?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Coverage varies by insurance provider and plan. Some private insurance plans, Medicaid, and Medicare may cover music therapy services under certain conditions. NCMS can provide documentation for insurance claims. Contact us to discuss your specific situation."
      }
    },
    {
      "@type": "Question",
      "name": "Are NCMS music therapists board certified?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes, NCMS music therapists hold the MT-BC (Music Therapist - Board Certified) credential from the Certification Board for Music Therapists. This requires completing an approved degree program, 1200+ hours of clinical training, and passing a national examination."
      }
    }
  ]
}
</script>
```

### Scholarship FAQ

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "How do I apply for a music lesson scholarship at NCMS?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Scholarship applications are available year-round through our website or by contacting our office. The application process is confidential and typically takes about 2 weeks to process. Scholarships are available for all NCMS programs including private lessons, group classes, and summer camps."
      }
    },
    {
      "@type": "Question",
      "name": "Who is eligible for NCMS scholarships?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "NCMS scholarships through The Community Fund are available to families in Greater Nashua who demonstrate financial need based on household size and income. We serve residents of Nashua, Merrimack, Hollis, Hudson, Amherst, Milford, and surrounding communities. Approximately 40% of our students receive financial assistance."
      }
    },
    {
      "@type": "Question",
      "name": "How much scholarship funding does NCMS award?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "NCMS awards over $85,000 in scholarships annually through The Community Fund, supporting more than 120 students each year. Award amounts vary based on demonstrated need and can cover partial or full tuition for lessons, camps, and other programs."
      }
    }
  ]
}
</script>
```

---

## 3. Event Schema (Recitals & Concerts)

**Add to:** Recitals page, or create a code block for each event

Replace placeholder values with actual event details.

### Single Recital Event

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "MusicEvent",
  "name": "NCMS Spring 2026 Student Recital",
  "description": "Join us for our Spring 2026 student recital featuring performances by NCMS private lesson and ensemble students of all ages and skill levels. Free and open to the public.",
  "startDate": "2026-05-15T19:00:00-04:00",
  "endDate": "2026-05-15T21:00:00-04:00",
  "eventStatus": "https://schema.org/EventScheduled",
  "eventAttendanceMode": "https://schema.org/OfflineEventAttendanceMode",
  "location": {
    "@type": "Place",
    "name": "Nashua Community Music School",
    "address": {
      "@type": "PostalAddress",
      "streetAddress": "2 Lock Street",
      "addressLocality": "Nashua",
      "addressRegion": "NH",
      "postalCode": "03060",
      "addressCountry": "US"
    }
  },
  "organizer": {
    "@type": "Organization",
    "name": "Nashua Community Music School",
    "url": "https://www.nashuacms.org"
  },
  "performer": {
    "@type": "PerformingGroup",
    "name": "NCMS Students"
  },
  "offers": {
    "@type": "Offer",
    "price": "0",
    "priceCurrency": "USD",
    "availability": "https://schema.org/InStock",
    "validFrom": "2026-01-01",
    "url": "https://www.nashuacms.org/recitals"
  },
  "isAccessibleForFree": true,
  "image": "https://www.nashuacms.org/path-to-recital-image.jpg"
}
</script>
```

### Multiple Events (Recital Schedule)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "ItemList",
  "name": "NCMS 2025-2026 Recital Schedule",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "item": {
        "@type": "MusicEvent",
        "name": "Fall 2025 Student Recital",
        "startDate": "2025-11-15T19:00:00-05:00",
        "location": {
          "@type": "Place",
          "name": "Nashua Community Music School",
          "address": {
            "@type": "PostalAddress",
            "addressLocality": "Nashua",
            "addressRegion": "NH"
          }
        },
        "isAccessibleForFree": true
      }
    },
    {
      "@type": "ListItem",
      "position": 2,
      "item": {
        "@type": "MusicEvent",
        "name": "Winter 2026 Student Recital",
        "startDate": "2026-02-14T19:00:00-05:00",
        "location": {
          "@type": "Place",
          "name": "Nashua Community Music School",
          "address": {
            "@type": "PostalAddress",
            "addressLocality": "Nashua",
            "addressRegion": "NH"
          }
        },
        "isAccessibleForFree": true
      }
    },
    {
      "@type": "ListItem",
      "position": 3,
      "item": {
        "@type": "MusicEvent",
        "name": "Spring 2026 Student Recital",
        "startDate": "2026-05-15T19:00:00-04:00",
        "location": {
          "@type": "Place",
          "name": "Nashua Community Music School",
          "address": {
            "@type": "PostalAddress",
            "addressLocality": "Nashua",
            "addressRegion": "NH"
          }
        },
        "isAccessibleForFree": true
      }
    }
  ]
}
</script>
```

---

## 4. Course Schema (Programs)

**Add to:** Individual program pages (Private Lessons, Music Therapy, Summer Camps)

### Private Lessons

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Course",
  "name": "Private Music Lessons",
  "description": "One-on-one music instruction in over 15 instruments for students ages 5 through adult. Lessons available in 30, 45, or 60-minute formats with expert faculty. Scholarships available.",
  "provider": {
    "@type": "Organization",
    "name": "Nashua Community Music School",
    "url": "https://www.nashuacms.org"
  },
  "educationalLevel": "Beginner to Advanced",
  "audience": {
    "@type": "Audience",
    "audienceType": "Students ages 5 to adult"
  },
  "coursePrerequisites": "None - beginners welcome",
  "availableLanguage": "English",
  "offers": {
    "@type": "Offer",
    "category": "Music Lessons",
    "priceCurrency": "USD",
    "availability": "https://schema.org/InStock"
  },
  "hasCourseInstance": {
    "@type": "CourseInstance",
    "courseMode": "onsite",
    "courseWorkload": "Weekly lessons, 30-60 minutes"
  }
}
</script>
```

### Summer Camp

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Course",
  "name": "NCMS Summer Music Camps",
  "description": "Week-long summer music camps for children in partnership with City of Nashua Parks & Recreation. Explore instruments, make music with friends, and perform in a showcase concert.",
  "provider": {
    "@type": "Organization",
    "name": "Nashua Community Music School",
    "url": "https://www.nashuacms.org"
  },
  "educationalLevel": "Beginner",
  "audience": {
    "@type": "Audience",
    "audienceType": "Children ages 6-12"
  },
  "availableLanguage": "English",
  "hasCourseInstance": {
    "@type": "CourseInstance",
    "courseMode": "onsite",
    "courseWorkload": "Full day, Monday-Friday, one week"
  }
}
</script>
```

---

## 5. Person Schema (Faculty)

**Add to:** Our Team page

Establishes authority by highlighting credentials.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "ItemList",
  "name": "NCMS Faculty",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "item": {
        "@type": "Person",
        "name": "Faculty Member Name",
        "jobTitle": "Piano and Voice Instructor",
        "description": "12 years of teaching experience specializing in classical piano and vocal technique.",
        "worksFor": {
          "@type": "Organization",
          "name": "Nashua Community Music School"
        },
        "knowsAbout": ["Piano", "Voice", "Music Theory"],
        "hasCredential": {
          "@type": "EducationalOccupationalCredential",
          "credentialCategory": "degree",
          "name": "Bachelor of Music Education"
        }
      }
    },
    {
      "@type": "ListItem",
      "position": 2,
      "item": {
        "@type": "Person",
        "name": "Music Therapist Name",
        "jobTitle": "Board-Certified Music Therapist",
        "worksFor": {
          "@type": "Organization",
          "name": "Nashua Community Music School"
        },
        "hasCredential": {
          "@type": "EducationalOccupationalCredential",
          "credentialCategory": "certificate",
          "name": "MT-BC (Music Therapist - Board Certified)"
        }
      }
    }
  ]
}
</script>
```

---

## 6. Review Schema (Testimonials)

**Add to:** Homepage, relevant program pages

Allows testimonials to appear as social proof in search results.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Nashua Community Music School",
  "url": "https://www.nashuacms.org",
  "review": [
    {
      "@type": "Review",
      "reviewRating": {
        "@type": "Rating",
        "ratingValue": "5",
        "bestRating": "5"
      },
      "author": {
        "@type": "Person",
        "name": "Maria S."
      },
      "reviewBody": "NCMS didn't just teach my daughter to play piano—they gave her confidence, community, and a lifelong love of music. The scholarship made it possible for our family."
    },
    {
      "@type": "Review",
      "reviewRating": {
        "@type": "Rating",
        "ratingValue": "5",
        "bestRating": "5"
      },
      "author": {
        "@type": "Person",
        "name": "David R."
      },
      "reviewBody": "As an adult learner, I was nervous about starting guitar lessons. The instructors at NCMS made me feel welcome and I've made more progress than I ever expected."
    }
  ],
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.9",
    "reviewCount": "87",
    "bestRating": "5"
  }
}
</script>
```

---

## Implementation Checklist

### Phase 1: Foundation (Week 1-2)
- [ ] Add Organization + LocalBusiness schema to site header
- [ ] Verify/update Google Business Profile
- [ ] Test schema at validator.schema.org

### Phase 2: FAQ Content (Week 2-3)
- [ ] Add General FAQ schema to New Student/Get Started page
- [ ] Add Music Therapy FAQ to Music Therapy page
- [ ] Add Scholarship FAQ to Scholarship page
- [ ] Test all FAQ schemas for rich result eligibility

### Phase 3: Events (Week 3-4)
- [ ] Add Event schema for upcoming recitals
- [ ] Add recital schedule ItemList schema
- [ ] Update event schema as dates change

### Phase 4: Depth (Ongoing)
- [ ] Add Course schema to program pages
- [ ] Add Person schema for faculty
- [ ] Add Review schema with testimonials
- [ ] Build citations across local directories

---

## Testing & Validation Resources

- **Google Rich Results Test:** https://search.google.com/test/rich-results
- **Schema.org Validator:** https://validator.schema.org/
- **Google Search Console:** Monitor rich result appearances
- **Manual AI Testing:** Ask ChatGPT, Perplexity, Bing Copilot questions about music lessons in Nashua to see if NCMS appears

---

## Notes for Squarespace

- JSON-LD scripts in Code Injection (Header) apply site-wide
- For page-specific schema, use Code Blocks set to display as code
- Squarespace doesn't natively support schema, so manual implementation is required
- After any schema changes, re-test with Google's tools
- Allow 2-4 weeks for Google to process new schema

---

*Document prepared for NCMS Digital Presence Refresh*
*January 2026*
