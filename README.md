# 🎯 QR Code Generator

A simple yet powerful Python utility to generate QR codes from text, URLs, or any string data.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

---

## ✨ Features

- ✅ **Generate QR Codes** - Convert text/URLs to QR codes
- ✅ **Customizable** - Adjust size, color, and error correction level
- ✅ **Multiple Formats** - Save as PNG, JPG, SVG
- ✅ **Easy to Use** - Simple Python API
- ✅ **No Dependencies** - Lightweight implementation

---

## 📋 Prerequisites

- Python 3.8+
- pip

---

## 🚀 Installation

```bash
# Clone the repository
git clone https://github.com/Anuj230977/qr-code-generator.git
cd qr-code-generator

# Install dependencies
pip install -r requirements.txt
```

### Dependencies
```
qrcode[pil]>=7.3.1
Pillow>=9.0.0
```

---

## 💻 Usage

### Basic Usage

```python
import qrcode

# Generate QR code from text
qr = qrcode.QRCode(
    version=1,
    error_correction=qrcode.constants.ERROR_CORRECT_L,
    box_size=10,
    border=4,
)
qr.add_data('https://github.com')
qr.make(fit=True)

# Create image
img = qr.make_image(fill_color="black", back_color="white")
img.save("github_qr.png")
```

### Advanced Usage

```python
# Custom size QR code
qr = qrcode.QRCode(
    version=1,
    error_correction=qrcode.constants.ERROR_CORRECT_H,
    box_size=20,
    border=4,
)

# Add data
qr.add_data('Your text here')
qr.make(fit=True)

# Generate with custom colors
img = qr.make_image(fill_color="blue", back_color="white")
img.save("custom_qr.png")
```

### Error Correction Levels

| Level | Constant | Recovery |
|-------|----------|----------|
| L | ERROR_CORRECT_L | ~7% |
| M | ERROR_CORRECT_M | ~15% |
| Q | ERROR_CORRECT_Q | ~25% |
| H | ERROR_CORRECT_H | ~30% |

---

## 📁 Project Structure

```
qr-code-generator/
├── qr_generator.py    # Main script
├── requirements.txt   # Dependencies
├── examples/
│   ├── github_qr.png
│   ├── url_qr.png
│   └── text_qr.png
└── README.md
```

---

## 🎨 Examples

### Text to QR Code
```python
import qrcode

text = "Hello, World!"
qr = qrcode.QRCode()
qr.add_data(text)
qr.make()
img = qr.make_image()
img.save("text_qr.png")
```

### URL to QR Code
```python
import qrcode

url = "https://github.com/Anuj230977"
qr = qrcode.QRCode()
qr.add_data(url)
qr.make()
img = qr.make_image()
img.save("url_qr.png")
```

### Wi-Fi QR Code
```python
import qrcode

wifi_string = "WIFI:T:WPA;S:NetworkName;P:Password;;"
qr = qrcode.QRCode()
qr.add_data(wifi_string)
qr.make()
img = qr.make_image()
img.save("wifi_qr.png")
```

---

## 🧪 Testing

```bash
# Run tests
python -m pytest tests/

# Generate sample QR codes
python examples/generate_samples.py
```

---

## 🔧 Customization

### Size
```python
qr.box_size = 15  # Larger QR code squares
qr.border = 2     # Border thickness
```

### Colors
```python
img = qr.make_image(
    fill_color="navy",      # Foreground
    back_color="lightblue"  # Background
)
```

### Error Correction
```python
error_correction=qrcode.constants.ERROR_CORRECT_H  # Maximum recovery
```

---

## 📊 Use Cases

- 📱 Mobile app links
- 🔗 URL shortening
- 📧 Contact information
- 📝 Event tickets
- 🏷️ Product labeling
- 🎁 Gift card codes
- 🔐 Authentication codes

---

## ⚙️ Configuration

### Version
- Version 1 = 21×21 pixels
- Version ranges from 1 to 40
- Auto-increment with `fit=True`

### Box Size
- Larger box_size = Larger output image
- Default = 10 pixels

### Border
- Border size in boxes (not pixels)
- Default = 4

---

## 🐛 Troubleshooting

**Issue:** "No module named 'qrcode'"
```bash
pip install qrcode[pil]
```

**Issue:** "PIL/Pillow not found"
```bash
pip install Pillow
```

**Issue:** QR code too complex
```python
# Use higher version
qr = qrcode.QRCode(version=10)
```

---

## 📚 Resources

- [QRCode Docs](https://github.com/lincolnloop/python-qrcode)
- [Pillow Docs](https://pillow.readthedocs.io/)

---

## 📝 License

MIT License

---

## 📞 Support

- 📧 Email: [Your Email]
- 💬 Issues: [GitHub Issues](https://github.com/Anuj230977/qr-code-generator/issues)

---

**⭐ Star if helpful!**
