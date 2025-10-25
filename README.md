# Shelly Device Icons

A centralized repository of device images/icons for all Shelly smart home devices. Perfect for use in web applications, dashboards, and Home Assistant integrations.

## 🎯 Purpose

This repository provides:
- High-quality product images for all Shelly devices
- Organized by generation (Gen1, Gen2, Gen3)
- Easy CDN access via GitHub raw URLs
- Machine-readable manifest for programmatic access
- Thumbnails for faster loading

## 📦 Structure

```
devices/
├── gen1/          # First generation Shelly devices
├── gen2/          # Plus and Pro series
└── gen3/          # Latest generation
categories/        # Category icons (relay, dimmer, sensor, etc.)
```

## 🚀 Usage

### Direct Image URL

```
https://raw.githubusercontent.com/[username]/shelly-device-icons/main/devices/gen1/shelly-1pm.png
```

### In HTML

```html
<img src="https://raw.githubusercontent.com/[username]/shelly-device-icons/main/devices/gen1/shelly-1pm.png" 
     alt="Shelly 1PM" 
     width="100">
```

### Using the Manifest (Recommended)

```javascript
// Fetch the manifest
const response = await fetch('https://raw.githubusercontent.com/[username]/shelly-device-icons/main/manifest.json');
const manifest = await response.json();

// Get image URL for a device type
const deviceType = 'SHSW-PM'; // From Shelly API
const imageUrl = manifest.base_url + '/' + manifest.devices[deviceType].image;
```

### Python Example

```python
import requests

# Load manifest
manifest = requests.get('https://raw.githubusercontent.com/[username]/shelly-device-icons/main/manifest.json').json()

# Get device image
device_type = 'SHSW-25'
if device_type in manifest['devices']:
    image_url = f"{manifest['base_url']}/{manifest['devices'][device_type]['image']}"
    print(f"Image URL: {image_url}")
```

## 📸 Image Specifications

- **Format:** PNG with transparency
- **Full Size:** 512x512px or original product photo resolution
- **Thumbnails:** 128x128px (in `thumbs/` subdirectory)
- **Background:** Transparent or white
- **Quality:** High-resolution product photos

## 🤝 Contributing

Want to add a device or improve an image?

1. Fork this repository
2. Add your image to the appropriate directory
3. Update `manifest.json` with the device information
4. Create a thumbnail (128x128px) in the `thumbs/` folder
5. Submit a pull request

### Naming Convention

- Use lowercase with hyphens: `shelly-plus-1pm.png`
- Match the official Shelly product name
- Keep file sizes reasonable (< 500KB for full size, < 50KB for thumbs)

## 📋 Supported Devices

See `manifest.json` for the complete list of supported devices.

Current count: **[X] devices** across **[Y] categories**

## 🙏 Credits

Images sourced from:
- Official Shelly product pages
- Community contributions
- [maxlyth/shelly-admin](https://github.com/maxlyth/shelly-admin) (original inspiration)

## 📄 License

MIT License - Free to use in any project, commercial or personal.

## 🔗 Related Projects

- [ha-addon-shelly-scanner](https://github.com/filmgarage/ha-addon-shelly-scanner) - Home Assistant add-on for scanning Shelly devices
- [Shelly API Documentation](https://shelly-api-docs.shelly.cloud/)

## 💡 Use Cases

- Home Assistant dashboards
- Custom Shelly management interfaces
- Mobile apps
- Documentation and tutorials
- Inventory management systems
