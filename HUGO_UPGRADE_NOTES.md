# Hugo Version Upgrade Notes

## Current Status
- **Minimum Hugo Version:** 0.154.2
- **Last Updated:** January 3, 2026

## Upgrade from v0.153.3 to v0.154.2

### Summary
The Huey theme has been updated to require Hugo v0.154.2 as the minimum version. This upgrade includes five minor releases (v0.153.4 through v0.154.2) with no breaking changes that affect the theme.

### Breaking Changes
**None** - This upgrade path contains no breaking changes that affect Huey's functionality.

### Notable Features Available in v0.154.x

#### 1. Partial Decorators (v0.154.0)
Hugo v0.154.0 introduces partial decorators, which allow partials to act as wrappers using the new `inner` keyword. This enables more flexible template composition:

```go
{{ with partial "wrapper.html" "content" }}Hello {{ . }}{{ end }}

{{ define "_partials/wrapper.html" }}<div class="wrapper">{{ inner . }}</div>{{ end }}
```

**Recommendation:** While Huey doesn't currently use this feature, it could be beneficial for future component-based enhancements while maintaining the minimal philosophy.

#### 2. Enhanced reflect Package (v0.154.0)
New utility functions for type checking:
- `reflect.IsResource` - Check if a value is a resource
- `reflect.IsImageResource` - Check if a value is an image resource
- `reflect.IsPage` - Check if a value is a page
- `reflect.IsSite` - Check if a value is a site

**Current Usage:** Not used in Huey, but could improve type safety in future template logic.

#### 3. WebP Improvements (v0.153.5 & v0.154.2)
- Improved WebP configuration with proper compression options
- Fixed quality/hint parameters that were being ignored
- Increased memory limits for WebP processing (384 MiB)
- Fixed alpha/fuzzy border issues with transparent backgrounds (v0.154.2)

**Impact on Huey:** Positive - Images with transparent backgrounds will render better, and WebP processing is more reliable.

### Files Updated
1. `/Users/whitlock/Developer/huey/theme.toml` - Updated `min_version` from "0.153.3" to "0.154.2"
2. `/Users/whitlock/Developer/huey/CLAUDE.md` - Updated compatibility requirement to ">= 0.154.2"
3. `/Users/whitlock/Developer/huey/config.toml` - Updated `module.hugoVersion.min` from "0.80.0" to "0.154.2"

### Compatibility Assessment

#### Template Syntax
- All template patterns in Huey use stable Hugo features
- No deprecated `.Page.Site` patterns found
- No deprecated `.Hugo.Version` references found
- Standard pagination, resources, and content functions remain unchanged

#### Asset Processing
- Sass/SCSS processing (used for Bulma) - No changes required
- Image processing - Improved with WebP fixes
- CSS minification and fingerprinting - No changes required

#### Configuration
- TOML configuration format - No changes required
- Module system - No changes required
- Menu configuration - No changes required
- Pagination settings - No changes required

### Testing Recommendations

When upgrading your Hugo installation to v0.154.2, test the following:

1. **Build Process**
   ```bash
   hugo
   ```
   Verify no errors or deprecation warnings appear.

2. **Development Server**
   ```bash
   hugo server -D
   ```
   Ensure the server starts correctly and all pages render properly.

3. **Asset Pipeline**
   - Verify Bulma CSS compiles correctly
   - Check custom CSS in `assets/css/extra/` loads properly
   - Confirm Font Awesome icons display (if configured)

4. **Content Rendering**
   - Test blog post pages with header images
   - Verify pagination works on home and archive pages
   - Check responsive design on multiple screen sizes
   - Test shortcodes (center-image, center)

5. **Image Processing**
   - Verify header images render correctly
   - Test images with transparent backgrounds (WebP fixes)
   - Confirm base64 encoding works for page bundle images

### Installation Notes

#### Via Package Manager
Hugo v0.154.2 may not be immediately available in all package managers:
- **Flox:** Currently provides v0.153.3 (as of January 3, 2026)
- **Homebrew:** Check with `brew info hugo`
- **Other managers:** Verify version before upgrading

#### Direct Installation
Download the latest Hugo extended edition from:
https://github.com/gohugoio/hugo/releases/latest

The extended edition is required for Sass/SCSS processing used by Bulma.

### Rollback Instructions

If you encounter issues with v0.154.2, you can temporarily use v0.153.3 by:

1. Reverting these files to use "0.153.3":
   - `theme.toml`
   - `CLAUDE.md`
   - `config.toml`

2. Installing Hugo v0.153.3 from:
   https://github.com/gohugoio/hugo/releases/tag/v0.153.3

Note: No template or configuration changes are required for rollback as the theme remains backward compatible.

### Future Upgrade Path

The Huey theme will continue to track Hugo's stable releases. Future upgrades will:
- Maintain backward compatibility where possible
- Adopt new features that align with the minimal philosophy
- Document any breaking changes clearly
- Test thoroughly before updating minimum version requirements

### Questions?

If you encounter issues with this Hugo version upgrade, please:
1. Check the Hugo release notes: https://github.com/gohugoio/hugo/releases
2. File an issue on the Huey GitHub repository
3. Verify you're using the Hugo extended edition

### References
- Hugo v0.154.2 Release: https://github.com/gohugoio/hugo/releases/tag/v0.154.2
- Hugo v0.154.0 Release: https://github.com/gohugoio/hugo/releases/tag/v0.154.0
- Hugo Documentation: https://gohugo.io/documentation/
