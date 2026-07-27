# Bundle Banner Section

## Overview

This project adds a reusable Shopify Product Page (PDP) section that displays a promotional bundle banner. The section is fully customizable through the Shopify Theme Editor and follows the approved **After – V1** Figma design.

The implementation is built as a standalone Shopify section and can be added to any Product Detail Page without affecting the existing layout.

Loom Viedo: https://www.loom.com/share/9ef68e6b860640a3af0d9dcbd6a6b1d4

Preview link: https://pm-digital-iqxsuzad.myshopify.com/?_ab=0&_bt=eyJfcmFpbHMiOnsibWVzc2FnZSI6IkJBaEpJaVp3YlMxa2FXZHBkR0ZzTFdseGVITjFlbUZrTG0xNWMyaHZjR2xtZVM1amIyMEdPZ1pGVkE9PSIsImV4cCI6IjIwMjYtMDctMjdUMDQ6NDM6NTcuNzEyWiIsInB1ciI6InBlcm1hbmVudF9wYXNzd29yZF9ieXBhc3MifX0%3D--b725be3cd598a8e9051f566daaf8d33c844c5a04&_fd=0&_sc=1&key=96c1a8a2164dd70aff11028689810b54b8656d1e0a5b9bd73614d913a1258be5&preview_theme_id=192453542154

Variant A: https://pm-digital-iqxsuzad.myshopify.com/?ig-preview=e67e8357-1a69-4936-9b5c-6890ba7e3914&igTg=ae26c37a-fa54-429b-8cc9-89cad7cc91c5&preview_theme_id=192453542154&pb=0

Variant B: https://pm-digital-iqxsuzad.myshopify.com/?ig-preview=e67e8357-1a69-4936-9b5c-6890ba7e3914&igTg=dd47e48f-9bd2-4ab6-aaba-cb03e6bca357&preview_theme_id=192453542154&pb=0

Password: gayglo
Product Page: https://pm-digital-iqxsuzad.myshopify.com/products/physical-product-the-band-t-shirt



---

## File Structure

```
sections/
└── bundle-banner.liquid
```

---

## Requirements

### Section Development

- Build as a standalone Shopify section.
- File location:
  ```
  sections/bundle-banner.liquid
  ```
- Compatible with Shopify Online Store 2.0.

### Design Implementation

- Match the **After – V1** Figma design.
- Responsive implementation for:
  - Desktop: **1440px**
  - Mobile: **390px**

### Theme Editor Settings

The section should expose the following customizable settings:
```
{% schema %}
{
  "name": "Bundle Banner",
  "tag": "section",
  "class": "section-bundle-banner",
  "settings": [
    {
      "type": "header",
      "content": "Rating Settings"
    },
    {
      "type": "checkbox",
      "id": "show_rating",
      "label": "Show rating header",
      "default": true
    },
    {
      "type": "text",
      "id": "review_rating",
      "label": "Rating score",
      "default": "4.7"
    },
    {
      "type": "text",
      "id": "review_count_text",
      "label": "Rating count text",
      "default": "1,700+ VERIFIED REVIEWS"
    },
    {
      "type": "header",
      "content": "Content Settings"
    },
    {
      "type": "inline_richtext",
      "id": "heading",
      "label": "Heading",
      "default": "Your Brain Isn't Broken. <em>It's Just Been Running on the Wrong Fuel</em>"
    },
    {
      "type": "textarea",
      "id": "subheading",
      "label": "Subheading / Body text",
      "default": "Brain fog, procrastination, the 3pm wall, these aren't signs that something's wrong with you. They're signs that what you're drinking to fix them is making them worse. Here's what's actually happening, and what 32,000+ people do about it every morning."
    },
    {
      "type": "header",
      "content": "Call to Action"
    },
    {
      "type": "text",
      "id": "cta_label",
      "label": "CTA button label",
      "default": "TRY IT RISK-FREE — 50% OFF YOUR FIRST ORDER →"
    },
    {
      "type": "url",
      "id": "cta_url",
      "label": "CTA button link"
    },
    {
      "type": "text",
      "id": "guarantee_text",
      "label": "Guarantee subtext",
      "default": "100-Day Money-Back Guarantee • Free Shipping • Cancel anytime in 3 clicks"
    },
    {
      "type": "header",
      "content": "Images"
    },
    {
      "type": "image_picker",
      "id": "background_image",
      "label": "Custom Background Image"
    },
    {
      "type": "image_picker",
      "id": "product_image",
      "label": "Product Image (3 Bottles)"
    },
    {
      "type": "checkbox",
      "id": "show_badge",
      "label": "Show rotating trust badge",
      "default": true
    },
    {
      "type": "image_picker",
      "id": "badge_image",
      "label": "Trust Badge Image"
    },
    {
      "type": "header",
      "content": "Color Customization"
    },
    {
      "type": "color",
      "id": "card_bg_color",
      "label": "Card background color",
      "default": "#FFFFFF"
    },
    {
      "type": "color",
      "id": "text_color",
      "label": "Heading text color",
      "default": "#1A1A1A"
    },
    {
      "type": "color",
      "id": "button_bg_color",
      "label": "Button background color",
      "default": "#000000"
    },
    {
      "type": "color",
      "id": "button_text_color",
      "label": "Button text color",
      "default": "#FFFFFF"
    },
    {
      "type": "color",
      "id": "accent_color",
      "label": "Checkmark icon background color",
      "default": "#00A884"
    },
    {
      "type": "color",
      "id": "star_color",
      "label": "Rating star color",
      "default": "#FF758F"
    },
    {
      "type": "header",
      "content": "Section Layout & Padding"
    },
    {
      "type": "range",
      "id": "padding_top",
      "min": 0,
      "max": 100,
      "step": 4,
      "unit": "px",
      "label": "Top padding",
      "default": 40
    },
    {
      "type": "range",
      "id": "padding_bottom",
      "min": 0,
      "max": 100,
      "step": 4,
      "unit": "px",
      "label": "Bottom padding",
      "default": 40
    }
  ],
  "blocks": [
    {
      "type": "benefit",
      "name": "Benefit Item",
      "settings": [
        {
          "type": "text",
          "id": "text",
          "label": "Benefit text",
          "default": "Calm, focused energy for 7+ hours, without the crash†"
        }
      ]
    },
    {
      "type": "ticker_item",
      "name": "Ticker Item",
      "settings": [
        {
          "type": "text",
          "id": "text",
          "label": "Ticker text",
          "default": "10 years of research"
        }
      ]
    }
  ],
  "presets": [
    {
      "name": "Bundle Banner (After V1)",
      "blocks": [
        {
          "type": "benefit",
          "settings": {
            "text": "Calm, focused energy for 7+ hours, without the crash†"
          }
        },
        {
          "type": "benefit",
          "settings": {
            "text": "Procrastination and brain fog that lift, not just mask*"
          }
        },
        {
          "type": "benefit",
          "settings": {
            "text": "Stress that actually decreases over time†"
          }
        },
        {
          "type": "ticker_item",
          "settings": {
            "text": "10 years of research"
          }
        },
        {
          "type": "ticker_item",
          "settings": {
            "text": "Third-party tested"
          }
        },
        {
          "type": "ticker_item",
          "settings": {
            "text": "Patented formula"
          }
        },
        {
          "type": "ticker_item",
          "settings": {
            "text": "Clinically-backed ingredients"
          }
        }
      ]
    }
  ]
}
{% endschema %}
```


### CTA Button

- CTA label should be editable.
- CTA destination should support:
  - Shopify Collection
  - Custom URL
- Open using the configured schema link.

### Styling

- Mobile-first approach.
- Vanilla CSS only.
- No CSS frameworks.
- Responsive across desktop, tablet, and mobile devices.

### Accessibility

- Use semantic HTML elements.
- Include descriptive `alt` attributes for all images.
- Ensure buttons and links are keyboard accessible.

### Compatibility

- Should render correctly on any Shopify Product Detail Page.
- Must not interfere with existing PDP sections or functionality.
- Keep styles scoped to the section to avoid CSS conflicts.

---

## Acceptance Criteria

- ✅ Standalone Shopify section.
- ✅ Matches Figma "After – V1" design.
- ✅ Responsive for 1440px and 390px layouts.
- ✅ All content configurable through Theme Editor.
- ✅ CTA supports Collection or Custom URL.
- ✅ Mobile-first implementation.
- ✅ Vanilla CSS only.
- ✅ Vanilla JavaScript only (if required).
- ✅ Semantic, accessible HTML.
- ✅ Images include proper alt attributes.
- ✅ No impact on existing PDP layout.
- ✅ Compatible with Shopify Online Store 2.0.

---

## Technical Notes

- Follow Shopify Liquid best practices.
- Keep CSS namespaced within the section.
- Optimize images using Shopify image filters.
- Minimize DOM complexity for better performance.
- Ensure the section is reusable across multiple products.

---

## Deliverables

- `sections/bundle-banner.liquid`
- Fully responsive implementation
- Theme Editor configurable settings
- Production-ready Shopify section
```
