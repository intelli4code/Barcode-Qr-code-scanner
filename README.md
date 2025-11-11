# QR & Barcode Scanner App

**Developer:** Hamza Munir  
**Version:** 1.0.0  
**Platform:** Flutter (Android & iOS)

---

## 📱 Overview

A comprehensive, all-in-one mobile application for scanning, creating, and managing QR codes and barcodes. This app is designed to be the single go-to solution for all your QR and barcode needs, combining powerful scanning capabilities with intuitive code generation and beautiful style templates.

---

## ✨ Key Features

### 🔍 **1. Scanner (Tab 1)**
- **Live Camera Scanning**: Real-time QR code and barcode detection
- **Auto-Detection**: Automatic recognition of various code types
- **Image Upload**: Scan codes from gallery images
- **Camera Controls**:
  - Flashlight toggle
  - Front/Back camera switch
- **Smart Feedback**:
  - Vibration on successful scan
  - Audio beep notification
  - Custom viewfinder overlay with brackets
- **Auto-Save**: All scans automatically saved to history
- **Supported Formats**:
  - QR Codes
  - EAN-13, EAN-8
  - UPC-A, UPC-E
  - Code 128, Code 39
  - ITF (Interleaved 2 of 5)
  - And many more!

### 🎨 **2. Create (Tab 2)**
Generate professional QR codes and barcodes with multiple style options.

#### QR Code Types:
- **Plain Text**: Any text content
- **URL/Website**: Direct web links
- **Wi-Fi Network**: SSID, password, and encryption type
- **Contact Card**: vCard format (name, phone, email, organization)
- **Phone Number**: Direct call links
- **Email**: Pre-filled email with subject and body

#### Barcode Types:
- **EAN-13**: 13-digit product barcodes
- **Code 128**: General-purpose barcodes
- **ITF**: Interleaved 2 of 5 format

#### **8 Beautiful Style Templates:**
1. **Standard** - Classic black and white
2. **Minimal** - Clean, borderless design
3. **Blue Ocean** - Vibrant blue background
4. **Green Nature** - Professional green style
5. **Black Frame** - Elegant black border
6. **Golden Frame** - Premium gold border
7. **Purple Round** - Modern rounded purple
8. **Orange Round** - Vibrant rounded orange

#### Features:
- **Style Customization**: Change colors, borders, and padding
- **Save to Gallery**: High-quality PNG export
- **Share**: Direct sharing to any app
- **Preview**: Real-time code preview

### 📚 **3. History (Tab 3)**
- **Complete Scan History**: All past scans organized by date
- **Smart Search**: Filter scans by content
- **Date Formatting**: "Today", "Yesterday", or full date
- **Quick Actions**:
  - Tap to view details
  - Swipe to delete
  - Bulk delete all history
- **Type Icons**: Visual identification by content type
- **Empty State**: Helpful guidance when no history exists

### ⚙️ **4. Settings (Tab 4)**

#### General Settings:
- ✅ Vibrate on Scan
- ✅ Beep on Scan

#### Scanning Settings:
- ✅ Auto-copy to Clipboard
- ✅ Auto-open Links (with safety warning)

#### History Management:
- 🗑️ Clear All Scan History

#### Support & Contact:
- 🐛 **Report an Error** - Direct WhatsApp link
- 💬 **Contact the Developer** - Get support via WhatsApp (+92 305 7468644)
- ⭐ Rate this App
- 📄 Privacy Policy
- ℹ️ App Version

---

## 🎯 Smart Result Panel

Intelligent action buttons based on scanned content type:

| Content Type | Available Actions |
|-------------|-------------------|
| **URL** | Copy • Open in Browser |
| **Wi-Fi** | Copy • View Connection Info |
| **Phone** | Copy • Call • Send SMS |
| **Email** | Copy • Send Email |
| **Product Barcode** | Copy • Search on Google |
| **Plain Text** | Copy to Clipboard |

---

## 🛠️ Technical Stack

### Framework & Language:
- **Flutter** 3.9.2+
- **Dart** Language

### Key Dependencies:
- `mobile_scanner` ^5.2.3 - QR/Barcode scanning
- `qr_flutter` ^4.1.0 - QR code generation
- `barcode_widget` ^2.0.4 - Barcode generation
- `hive` ^2.2.3 - Local database
- `image_picker` ^1.1.2 - Gallery access
- `url_launcher` ^6.3.1 - Open URLs and apps
- `share_plus` ^10.0.2 - Share functionality
- `permission_handler` ^11.3.1 - Runtime permissions
- `vibration` ^2.0.0 - Haptic feedback
- `intl` ^0.19.0 - Date formatting

### Architecture:
```
lib/
├── main.dart                 # App entry point & splash screen
├── models/                   # Data models
│   ├── scan_history.dart    # Hive model for scan history
│   ├── code_type.dart       # Code type definitions
│   └── barcode_template.dart # Style templates
├── screens/                  # UI screens
│   ├── scan_screen.dart     # Camera scanner
│   ├── create_screen.dart   # Code type selection
│   ├── code_generator_screen.dart # Forms & generation
│   ├── history_screen.dart  # Scan history
│   └── settings_screen.dart # App settings
├── services/                 # Business logic
│   └── database_service.dart # Hive operations
├── utils/                    # Helper functions
│   └── action_helper.dart   # Action utilities
└── widgets/                  # Reusable widgets
    └── result_panel.dart    # Bottom sheet panel
```

---

## 📦 Database Schema

### Hive Box: `scan_history`
```dart
class ScanHistory {
  String id;              // Unique identifier
  String content;         // Scanned/generated data
  String type;           // url, text, wifi, phone, email, product, contact
  DateTime timestamp;    // When it was scanned
  bool isFavorite;      // Future feature
}
```

### Hive Box: `settings`
```dart
{
  'vibrate_on_scan': bool,
  'beep_on_scan': bool,
  'auto_copy': bool,
  'auto_open_links': bool,
}
```

---

## 🚀 Getting Started

### Prerequisites:
- Flutter SDK 3.9.2 or higher
- Android Studio / VS Code
- Android SDK (for Android development)
- Xcode (for iOS development on macOS)

### Installation:

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd barcodereader_by_hamza
   ```

2. **Install dependencies**
   ```bash
   flutter pub get
   ```

3. **Generate Hive adapters**
   ```bash
   flutter pub run build_runner build --delete-conflicting-outputs
   ```

4. **Run the app**
   ```bash
   flutter run
   ```

### Building for Release:

**Android APK:**
```bash
flutter build apk --release
```

**Android App Bundle:**
```bash
flutter build appbundle --release
```

**iOS:**
```bash
flutter build ios --release
```

---

## 📱 Permissions

### Android:
- **CAMERA** - For scanning QR codes and barcodes
- **VIBRATE** - For haptic feedback
- **INTERNET** - For opening URLs
- **READ_EXTERNAL_STORAGE** - For picking images from gallery
- **WRITE_EXTERNAL_STORAGE** - For saving generated codes (API < 29)

### iOS:
- **Camera Usage** - NSCameraUsageDescription
- **Photo Library** - NSPhotoLibraryUsageDescription

---

## 🎨 Design Philosophy

This app follows Material Design 3 principles with:
- **Clean UI/UX**: Intuitive navigation with bottom tabs
- **Consistent Colors**: Blue primary theme (#2196F3)
- **Responsive Layouts**: Adapts to different screen sizes
- **Smooth Animations**: Polished transitions and feedback
- **Accessibility**: High contrast, readable fonts

---

## 🔒 Privacy & Data

- ✅ **100% Local Storage**: All data stored on device using Hive
- ✅ **No Cloud Sync**: Your data never leaves your device
- ✅ **No Tracking**: Zero analytics or user tracking
- ✅ **No Ads**: Clean, ad-free experience
- ✅ **Open Permissions**: Only essential permissions requested

---

## 🐛 Known Issues & Limitations

1. **Wi-Fi Auto-Connect**: Manual connection required (OS limitation)
2. **iOS File System**: Limited access to save directory
3. **Large QR Codes**: Very long text may affect scanning accuracy

---

## 🔄 Future Roadmap

- [ ] Batch scanning mode
- [ ] Export history to CSV/PDF
- [ ] Custom QR code logos/images
- [ ] Favorite scans
- [ ] Scan analytics
- [ ] Multi-language support
- [ ] Widget support
- [ ] Cloud backup (optional)

---

## 📞 Support & Contact

**Developer:** Hamza Munir  
**WhatsApp:** +92 305 7468644  
**Link:** [wa.me/+923057468644](https://wa.me/+923057468644)

### Reporting Issues:
Use the "Report an Error" option in Settings (Tab 4) to contact the developer directly via WhatsApp.

---

## 📄 License

This project is proprietary software developed by Hamza Munir. All rights reserved.

---

## 🙏 Acknowledgments

- **Flutter Team** - For the amazing framework
- **Open Source Community** - For the excellent packages
- **Beta Testers** - For valuable feedback

---

## 📊 Version History

### v1.0.0 (Current)
- ✅ Initial release
- ✅ Full scanner functionality
- ✅ Code generator with 8 style templates
- ✅ History management
- ✅ Settings & preferences
- ✅ Share & save features
- ✅ WhatsApp support integration

---

## 🎓 Usage Tips

1. **For Best Scanning**:
   - Hold phone steady 6-12 inches from code
   - Ensure good lighting
   - Use flashlight in low light
   - Clean your camera lens

2. **Creating Professional Codes**:
   - Choose templates based on use case
   - Use "Golden Frame" for business cards
   - Use "Minimal" for print materials
   - Test scans after generation

3. **Managing History**:
   - Use search to find old scans quickly
   - Swipe left to delete unwanted scans
   - Regular cleanup keeps app fast

---

**Made with ❤️ by Hamza Munir**

*Scan, Create & Share - Everything in One App!*
# Barcode-Qr-code-scanner
# testing-delete
# testing-delete
