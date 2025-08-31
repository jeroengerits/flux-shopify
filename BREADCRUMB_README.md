# Breadcrumb System Documentation

This theme includes a comprehensive breadcrumb system that automatically generates navigation breadcrumbs based on the current page context.

## Files Created

- `sections/breadcrumb.liquid` - Main breadcrumb section
- `sections/breadcrumb-group.json` - Section group configuration
- `snippets/breadcrumb.liquid` - Reusable breadcrumb snippet
- Updated templates to include breadcrumbs

## How It Works

The breadcrumb system automatically detects the current template and generates appropriate breadcrumbs:

### Supported Templates

- **Pages**: Home > Page Title
- **Products**: Home > Collection > Product Title
- **Collections**: Home > Collection Title
- **Blog**: Home > Blog Title
- **Articles**: Home > Blog > Article Title
- **Search**: Home > Search Results
- **404**: Home > Page Not Found
- **Cart**: Home > Cart

### Automatic Detection

The system uses Liquid's `template` variable to determine the current page type and automatically generates the appropriate breadcrumb structure.

## Usage

### 1. Using the Section (Recommended)

Add breadcrumbs to any template using:

```liquid
{% section 'breadcrumb' %}
```

### 2. Using the Snippet

For custom breadcrumb implementations, use the snippet:

```liquid
{% render 'breadcrumb', show_home: true, custom_items: custom_breadcrumb_array, current_title: 'Custom Title' %}
```

#### Snippet Parameters

- `show_home` (boolean): Whether to show the home link (default: true)
- `custom_items` (array): Custom breadcrumb items with 'title' and 'url' properties
- `current_title` (string): The current page title
- `current_url` (string): The current page URL

#### Example with Custom Items

```liquid
{% assign custom_breadcrumbs = array %}
{% assign custom_breadcrumbs = custom_breadcrumbs | push: 'title': 'Category', 'url': '/collections/category' %}

{% render 'breadcrumb', custom_items: custom_breadcrumbs, current_title: 'Product Name' %}
```

## Styling

The breadcrumbs use Tailwind CSS classes and follow the theme's design system:

- **Background**: `bg-brand-neutral-50`
- **Border**: `border-b border-brand-neutral-200`
- **Text colors**:
  - Links: `text-brand-neutral-600 hover:text-brand-neutral-900`
  - Current page: `text-brand-neutral-900 font-medium`
- **Separators**: `text-brand-neutral-400`

## Section Settings

The breadcrumb section includes configurable settings:

- **Show breadcrumbs**: Toggle breadcrumb visibility
- **Breadcrumb style**: Choose between minimal and detailed styles

## Accessibility

- Proper `aria-label="Breadcrumb"` for screen readers
- `aria-current="page"` for the current page
- Semantic navigation structure

## Customization

### Adding New Template Support

To add breadcrumb support for a new template type, edit `sections/breadcrumb.liquid` and add a new case:

```liquid
when 'custom_template' assign current_title = custom_object.title assign current_url = custom_object.url assign
breadcrumb_items = 'custom_template'
```

### Styling Modifications

Modify the CSS classes in `sections/breadcrumb.liquid` to match your design requirements.

## Performance

- Uses Liquid's `{%- -%}` tags to minimize whitespace
- Efficient template detection
- Minimal DOM manipulation

## Browser Support

- Modern browsers with CSS Grid and Flexbox support
- Responsive design for mobile and desktop
- RTL language support with `rtl:rotate-180` classes
