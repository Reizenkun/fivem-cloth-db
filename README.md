# Fivem Clothing Database & Viewer

A catalog with pre-rendered clothing from GTA V (prior to 2025_02 update).
Fully rendered: head, berd, hair, uppr, lowr, hand, feet, teef, accs, task, decl, jbib, p_head, p_eyes, p_ears, p_lwrist, p_rwrist.

Some items (for example, the night vision goggles in the p_head) have texture issues. If anyone knows how to fix this, I'd appreciate the advice.

## Web-preview

You can see preview of items on https://reizenkun.github.io/fivem-cloth-db/

## Accessing Assets via CDN

### Cloudflare R2 (Recommended)

IMPORTANT! Use pub-b5680e433ce7438d9f7fede88058efc3.r2.dev only for developing, in future I will provide static link without rate-limits and disable this link. Or you can clone this repo and host clothes for yourself.
```
https://pub-b5680e433ce7438d9f7fede88058efc3.r2.dev/{gender}/{part}/{drawableId}_{texId}.webp
```

Example:
```
https://pub-b5680e433ce7438d9f7fede88058efc3.r2.dev/male/accs/0_0.webp
```

## Integration Examples

### JavaScript/FiveM Resource
```javascript
// Base URL for Cloudflare R2 bucket
const baseUrl = "https://pub-b5680e433ce7438d9f7fede88058efc3.r2.dev";

// Generate clothing picture URL
const getIconUrl = (gender, category, drawable, texture = 0) => 
  `${baseUrl}/${gender}/${category}/${drawable}_${texture}.webp`;

// Usage example: getting a male torso (jbib) image (drawable 15, texture 0)
const shirtUrl = getIconUrl("male", "jbib", 15, 0);
// Returns: https://pub-b5680e433ce7438d9f7fede88058efc3.r2.dev/male/jbib/15_0.webp
```
