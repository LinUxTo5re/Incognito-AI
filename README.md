# Incognito AI Pro

> Privacy-focused AI assistant with screen capture protection for Windows

**Version:** *26.1.17*  
**Platform:** *Windows 10/11 (x64)*  
**Framework:** *.NET 8.0 / WPF*  
**Developer Contact:** *dev.linuxto5re@gmail.com*  
**Download Installer:** *https://github.com/LinUxTo5re/Incognito-AI/releases*

## Overview

Incognito AI Pro is a desktop AI assistant that prioritizes user privacy. The application provides a secure interface for interacting with Google's Gemini AI while remaining invisible during screen sharing sessions on platforms like Microsoft Teams, Zoom, and Google Meet.

**Key Highlights:**
- Screen capture protection using Windows Display Affinity API
- Powered by Google Gemini AI (default model: gemini-2.5-flash)
- Cloud-synced user settings via AWS DynamoDB
- Integrated payment system via Cashfree
- Automatic version management with forced update support

---

## Screenshots

### Main Interface
<img width="1052" height="756" alt="image" src="https://github.com/user-attachments/assets/9a86250b-8f78-46fc-b1dc-90c0f80907de" />
*AI chat interface with Gemini integration*

### Main Interface with annotation
<img width="777" height="561" alt="image" src="https://github.com/user-attachments/assets/8b434d3a-13ee-4947-ba89-30957da0f205" />

### Settings Panel
<img width="575" height="685" alt="image" src="https://github.com/user-attachments/assets/4fcdeb66-1ce1-452b-b707-d6b01943e511" />
<img width="574" height="682" alt="image" src="https://github.com/user-attachments/assets/1927e7fd-bec9-4a9d-8875-5002cade698a" />
<img width="570" height="688" alt="image" src="https://github.com/user-attachments/assets/42da3a46-4d50-4f08-b32b-8c5284dffbc6" />
*User settings and API configuration*

### Plans & Pricing
<img width="775" height="753" alt="image" src="https://github.com/user-attachments/assets/0518660a-ea65-485f-9c49-b02b084a4649" />
*Subscription offers and payment options*

### Contact and Support
<img width="405" height="356" alt="image" src="https://github.com/user-attachments/assets/23e47c9e-e4c3-409e-a760-b3334244cccf" />

---

## Features

### 1. AI Chat with Gemini

Text and image-based conversations powered by Google Gemini AI.

**How it works:**
- Users provide their own Gemini API key (free tier available from Google)
- Supports multiple Gemini models including flash and pro variants
- Default model is `gemini-2.5-flash` (optimized for speed and reliability)
- API key is validated before use and stored securely

**Available Models:**

| Model | Description |
|-------|-------------|
| gemini-2.5-flash | Default - Fast responses, good for general use |
| gemini-2.5-pro | Advanced reasoning, better for complex tasks |
| gemini-2.0-flash | Previous generation, stable |
| gemini-2.0-flash-lite | Lightweight, fastest responses |

---

### 2. Screenshot Analysis

Capture any region of your screen and send it to AI for analysis.

**How it works:**
- Click the screenshot button or use keyboard shortcut
- Main window minimizes automatically
- Select screen region with configurable cursor style
- Optional: Add a text prompt with your screenshot
- AI analyzes the image and provides detailed response

**Settings:**
- Cursor type: Arrow (default), Cross, Hand, IBeam
- Screenshot preview: Disabled by default when screen protection is ON
- Background capture support

---

### 3. Screen Capture Protection

The application window is invisible during screen recordings and screen shares.

**How it works:**
- Uses Windows Display Affinity API to exclude window from captures
- Window appears black/invisible in:
  - Microsoft Teams screen share
  - Zoom screen share
  - Google Meet screen share
  - OBS Studio recordings
  - Windows Snipping Tool
  - Any screen recording software

**Requirements:**
- Windows 10 version 2004 (May 2020 Update) or later
- Windows 11 (all versions)

**Settings:**
- Default screen protection: ON (can be toggled)
- Screenshot preview is automatically disabled when protection is ON

---

### 4. Always on Top

Keep the application window above all other windows.

**How it works:**
- Uses both WPF and Win32 API for reliable behavior
- Temporarily disabled during payment flow to allow browser access
- Automatically restored after payment completion

---

### 5. App Version Management

Automatic update checking with forced update support.

**How it works:**
- App checks version information from cloud database on startup
- Compares current version with latest and minimum required versions
- Shows notification if update is available
- **Blocks app if current version is below minimum required version**

**Version Control Fields:**

| Field | Description |
|-------|-------------|
| VersionKey | Identifier (e.g., "LATEST" or platform-specific) |
| LatestVersion | Newest available version |
| MinimumVersion | **Users below this version are BLOCKED from using the app** |
| DownloadUrl | Link to download the update |
| ReleaseNotes | Changelog for the update |
| IsMandatory | If true, shows blocking notification |
| ShowUpdateNotification | Whether to show update banner |

**Force Update Scenario:**
- Set `MinimumVersion` to the version you want all users to have
- Users with older versions will see a blocking notification
- They cannot use the app until they download the new version

---

### 6. Subscription & Payment

Pro subscription with integrated Cashfree payment gateway.

**Subscription Tiers (Example):**

| Feature | FREE (Trial) | PRO |
|---------|--------------|-----|
| Trial Period | 3 days | - |
| AI Chat | Limited | Unlimited |
| Screenshot Analysis | Limited | Unlimited |
| Screen Protection | Yes | Yes |
| Cloud Sync | Yes | Yes |

**How Payment Works:**
1. User selects an offer from available plans
2. Payment link is created via Cashfree Payment Links API
3. User is redirected to Cashfree payment page
4. App polls for payment status automatically
5. On successful payment, subscription is activated immediately

---

### 7. User Settings & Cloud Sync

All user preferences are synced to AWS DynamoDB.

**Synced Settings:**
- Theme (Dark/Light)
- Window opacity (30% - 100%)
- Selected AI model
- Screen protection default state
- Cursor type for screenshots
- User profile (name, email, phone)

---

### 8. Email Notifications

Automated email notifications for payment confirmations and promotional offers.

**How it works:**
- Emails are sent only if user has provided a valid email address in Settings
- Placeholder emails (`@incognito-ai.local`) are automatically skipped
- Email credentials are stored securely in DynamoDB (not in app code)
- Non-blocking: Email failures don't affect app functionality

**Email Types:**

| Email Type | Trigger | Content |
|------------|---------|---------|
| Payment Confirmation | After successful payment | Transaction ID, amount, plan details, expiry date |
| Flash Sale Notification | When flash sale offer is available | Discount details, original/sale price, validity period |

**Requirements:**
- User must provide a valid email address in Settings
- Email configuration must be set up in DynamoDB (`EMAIL_CONFIG`)

**Privacy:**
- Emails are opt-in (only sent if user provides email)
- Flash sale emails are deduplicated per session (no spam)
- No email tracking or analytics

---

### 9. Virtual Machine Detection

Prevents app usage in virtual machines to protect against trial abuse.

**How it works:**
- Detects common virtualization platforms on startup
- Shows warning dialog if VM is detected
- App cannot be used in virtual environments

**Detected Platforms:**
- VirtualBox
- VMware
- Hyper-V
- Parallels
- QEMU/KVM
- Xen

**Detection Methods:**
- BIOS information analysis
- System manufacturer checks
- MAC address patterns
- Registry keys
- Running services

---

### 10. Customization Options

**Theme:**
- Dark mode (default)
- Light mode

**Window Opacity:**
- Range: 30% to 100%
- Default: 95%

**Cursor Types:**
- Arrow (default)
- Cross
- Hand
- IBeam

---

## Troubleshooting

### Screen Protection Not Working
- Ensure Windows 10 version 2004 or later
- Check: Settings > System > About > Version (should be 2004+)

### API Connection Issues
- Verify Gemini API key in Settings
- Test API key using the "Test" button
- Check internet connection

### Cloud Connection Failed
- Ensure internet connectivity
- Contact support if issue persists

### Payment Not Completing
- Payment verification runs automatically
- Click "Verify" button to manually check status
- Contact support with transaction details if needed

---

## Security

- **Screen Protection:** Window excluded from all screen captures
- **API Keys:** Stored securely per-user
- **Machine ID:** Hardware-based unique identifier (hashed)
- **Payment Credentials:** Stored securely in cloud, not in app code
- **Email Credentials:** SMTP credentials stored in DynamoDB, not in app code
- **VM Detection:** Prevents usage in virtual machines to protect licensing
- **Logging:** Sensitive data excluded from logs

---

## Support

**Developer Contact:** dev.linuxto5re@gmail.com

For bug reports, feature requests, or general inquiries, please contact the developer email above.

---

## License

Proprietary - All Rights Reserved

Copyright 2026 Incognito AI Pro

---

*Last Updated: January 18, 2026*
