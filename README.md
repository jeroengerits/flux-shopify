# Flux Shopify Theme

A modern, accessible, and performant Shopify theme built with Liquid and Tailwind CSS.

## 🚀 Features

- **Modern Design**: Clean, responsive design with Tailwind CSS
- **Accessibility First**: WCAG compliant with proper ARIA labels and semantic HTML
- **Performance Optimized**: Lazy loading, optimized images, and efficient code structure
- **Customizable**: Extensive section settings for easy customization
- **Mobile First**: Responsive design that works on all devices
- **SEO Ready**: Proper meta tags, structured data, and semantic markup

## 🏗️ Theme Structure

```
flux-shopify/
├── config/                 # Theme configuration
├── layout/                 # Theme layout files
├── sections/               # Reusable section components
├── snippets/               # Reusable code snippets
├── templates/              # Page templates
├── locales/                # Translation files
└── assets/                 # Static assets (CSS, JS, images)
```

## 🎨 Design System

### Color Palette

- **Primary**: `#1f2937` (Dark gray)
- **Secondary**: `#6b7280` (Medium gray)
- **Accent**: `#3b82f6` (Blue)
- **Success**: `#10b981` (Green)
- **Warning**: `#f59e0b` (Orange)
- **Error**: `#ef4444` (Red)

### Typography

- **Headings**: Bold, scalable from mobile to desktop
- **Body**: Readable with proper line height and spacing
- **UI Elements**: Consistent sizing and weight system

## 🧩 Components

### Header

- Fixed navigation with backdrop blur
- Mobile-responsive menu
- Shopping cart integration
- Proper ARIA labels and navigation roles

### Hero Section

- Gradient backgrounds with subtle patterns
- Configurable content and buttons
- Responsive typography scaling
- Optional decorative elements

### Product Cards

- Optimized image loading with srcset
- Hover effects and transitions
- Accessibility features (aria-labelledby)
- Responsive grid layout
- Price comparison display

### Buttons

- Multiple variants (primary, secondary, outline, ghost)
- Consistent sizing system
- Focus-visible states for accessibility
- Support for both button and link variants

## ♿ Accessibility Features

- **Semantic HTML**: Proper use of `<section>`, `<article>`, `<nav>`, etc.
- **ARIA Labels**: Descriptive labels for screen readers
- **Focus Management**: Visible focus indicators
- **Skip Links**: Skip to main content functionality
- **Alt Text**: Descriptive alt text for images
- **Color Contrast**: WCAG AA compliant color combinations

## 📱 Responsive Design

- **Mobile First**: Design starts with mobile and scales up
- **Breakpoints**: Tailwind CSS responsive utilities
- **Touch Friendly**: Appropriate touch targets and spacing
- **Flexible Grids**: CSS Grid with responsive columns

## ⚡ Performance Optimizations

- **Lazy Loading**: Images load only when needed
- **Optimized Images**: Proper sizing and format selection
- **Minimal JavaScript**: Vanilla JS for essential functionality
- **Efficient CSS**: Tailwind CSS with custom properties
- **Resource Preloading**: Critical resources preloaded

## 🛠️ Development

### Prerequisites

- Node.js 16+
- Shopify CLI (optional)

### Setup

1. Clone the repository
2. Install dependencies: `npm install`
3. Configure your Shopify store
4. Deploy using Shopify CLI or manual upload

### Code Style

- **Liquid**: Use double quotes for consistency
- **CSS**: Follow Tailwind CSS conventions
- **HTML**: Semantic markup with proper accessibility
- **JavaScript**: Vanilla JS with modern ES6+ features

### Best Practices

#### Liquid Templates

```liquid
<!-- Good: Consistent quotes and spacing -->
{% if product.available %}
  <span class='text-success'>{{ product.title }}</span>
{% endif %}

<!-- Good: Proper variable assignment -->
{% assign show_price = section.settings.show_price | default: true %}
```

#### Accessibility

```liquid
<!-- Good: Proper ARIA labels -->
<button aria-label='Add {{ product.title }} to cart'>Add to Cart</button>

<!-- Good: Semantic HTML -->
<article class='product-card'>
  <h3 id='product-title-{{ product.id }}'>{{ product.title }}</h3>
</article>
```

#### Performance

```liquid
<!-- Good: Lazy loading and proper sizing -->
<img
  src='{{ image | image_url: width: 800, height: 400 }}'
  loading='lazy'
  alt='{{ image.alt | escape }}'
>

<!-- Good: Conditional rendering -->
{% if section.settings.show_feature %}
  <!-- Feature content -->
{% endif %}
```

## 🔧 Customization

### Section Settings

Each section includes comprehensive settings for easy customization:

- Content options (text, images, links)
- Display toggles
- Layout controls
- Color and style options

### Theme Customization

- Modify color variables in `layout/theme.liquid`
- Add new sections in the `sections/` directory
- Create reusable snippets in the `snippets/` directory
- Customize templates in the `templates/` directory

## 📚 Documentation

### Liquid Filters

- `image_url`: Optimized image URLs with sizing
- `money`: Currency formatting
- `escape`: HTML escaping for security
- `default`: Fallback values

### Shopify Objects

- `product`: Product information and variants
- `collection`: Collection details and products
- `cart`: Shopping cart contents
- `shop`: Store information

### Tailwind CSS

- Custom color variables for brand consistency
- Responsive utilities for mobile-first design
- Component classes for common patterns
- Custom focus states for accessibility

## 🚀 Deployment

### Shopify CLI

```bash
shopify theme push
shopify theme serve
```

### Manual Upload

1. Zip the theme directory
2. Upload via Shopify admin
3. Preview and publish

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes following the code style
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Support

For support and questions:

- Create an issue in the repository
- Contact: jeroen@gerits.email
- Documentation: [GitHub Repository](https://github.com/jeroengerits/flux-shopify)

## 🔄 Changelog

### v0.1.0

- Initial theme structure
- Basic sections and snippets
- Tailwind CSS integration
- Accessibility improvements
- Performance optimizations
- Responsive design implementation
