# ⚡ TNPDCL Field Officer Utility App (தமிழ்நாடு மின் பகிர்மான கழகம்)

> **Official Field Verification & Enforcement Utility App**  
> Designed for **TNPDCL (Tamil Nadu Power Distribution Corporation Limited)** field engineers, assistant engineers (AE), and revenue inspection squads.

---

## 🎨 Official Government Theme & Styling
* **Primary Theme:** TNPDCL Navy Blue (`#1A237E`) & Electric Sky Blue (`#0288D1`)
* **Background:** Clean White / Light Slate (`#F5F7FA`) optimized for daylight outdoor meter box inspections
* **Status Colors:**
  * 🟢 **PAID:** Traffic Light Green (`#4CAF50`)
  * 🔴 **UNPAID / OVERDUE:** Alert Red (`#F44336`)
* **Typography:**
  * English: **Inter** / **Roboto**
  * Tamil: **Noto Sans Tamil** (Full bilingual one-tap toggle)

---

## 📱 Screen-by-Screen Architecture

1. **Screen 1: Officer Login (`LoginView`)**
   * Employee ID / Section Code & PIN authentication
   * Fast Biometric (Fingerprint) scan for quick field login
   * English / தமிழ் bilingual toggle

2. **Screen 2: Home Dashboard (`DashboardView`)**
   * Officer designation, section (e.g. *Ayyampalayam Section*), and EDC circle
   * Key counters: *Bills Scanned Today (45)* & *Pending Disconnections (12)*
   * **Prominent Central Pulse Button:** `📷 SCAN EB BILL QR` for instantaneous camera trigger
   * Bottom Navigation: Home | Scan | Search | Profile

3. **Screen 3: QR Code Scanner Screen (`ScannerView`)**
   * Built on `mobile_scanner` with high-speed MLKit detection
   * Darkness / night-inspection Flashlight (Torch) toggle
   * Reticle overlay with focus boundaries
   * Manual 12-digit consumer number fallback for torn/damaged bills

4. **Screen 4: Bill Details Screen (`BillDetailsView`)**
   * High-contrast top banner displaying **PAID** (Green) or **UNPAID** (Red)
   * **Card 1 (Consumer Info):** Consumer Number, Name, Address, LT Tariff 1A, Distribution Transformer code
   * **Card 2 (Billing Info):** Consumed Units (kWh), Bill Amount (₹), Due Date, Disconnection Cut-off Date
   * **Bottom Action Bar:**
     * 📱 **Send SMS Reminder:** Instantly alerts consumer with TN e-Governance payment link
     * 🖨️ **Print Receipt:** Bluetooth ESC/POS 58mm thermal print generation

---

## 📁 Directory Structure

```
project EB/
├── lib/
│   ├── main.dart                          # App initialization & GetMaterialApp routes
│   ├── constants/
│   │   └── app_colors.dart                # Official TNPDCL color palette
│   ├── localization/
│   │   └── app_translations.dart          # English and Tamil localization map
│   ├── models/
│   │   └── bill_model.dart                # Consumer & bill data model + QR string parser
│   ├── controllers/
│   │   ├── auth_controller.dart           # Session & biometric authentication
│   │   └── bill_controller.dart           # Bill states, scans, SMS & print triggers
│   ├── services/
│   │   └── bluetooth_printer_service.dart # ESC/POS 58mm thermal printer integration
│   └── views/
│       ├── login_view.dart                # Screen 1
│       ├── dashboard_view.dart            # Screen 2
│       ├── scanner_view.dart              # Screen 3
│       └── bill_details_view.dart         # Screen 4
├── server/
│   ├── server.js                          # Express.js API Gateway + Consumer DB mock
│   └── package.json
└── pubspec.yaml                           # Flutter dependencies
```

---

## 🚀 Getting Started

### 1. Flutter Mobile App
```bash
# Get dependencies
flutter pub get

# Run on connected Android / iOS device
flutter run
```

### 2. Backend Server
```bash
cd server
npm install
npm start
```
