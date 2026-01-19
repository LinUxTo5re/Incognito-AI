# Incognito AI Pro

> Privacy-focused AI assistant with screen capture protection for Windows

**Version:** *26.1.17*  
**Platform:** *Windows 10/11 (x64)*  
**Framework:** *.NET 8.0 / WPF*  
**Developer Contact:** *dev.linuxto5re@gmail.com*  
**Download Installer:** *https://github.com/LinUxTo5re/Incognito-AI/releases*

## Overview

Incognito AI Pro is a desktop AI assistant that prioritizes user privacy. The application provides a secure interface for interacting with Google's Gemini AI while remaining *invisible during screen sharing* sessions on platforms like Microsoft Teams, Zoom, and Google Meet.

**Key Highlights:**
- Screen capture protection using Windows Display Affinity API
- Powered by Google Gemini AI (default model: gemini-2.5-flash)
- Cloud-synced user settings via AWS DynamoDB
- Integrated payment system via Cashfree
- Automatic version management with forced update support
- **Once installed on your system:** *No registration or login required — lifetime activation included in this build. We will detect your system automatically.*
  
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
- Users provide their own Gemini API key (free tier available from Google with limitations)
- Supports multiple Gemini models including flash and pro variants
- Default model is `gemini-2.5-flash` (optimized for speed and reliability)
- API key is validated before use and stored securely

**Available Models:**

| Model | Description |
|-------|-------------|
| gemini-2.5-flash | Default - Fast responses, good for general use |
| gemini-2.5-pro | Advanced reasoning, better for complex tasks |
| gemini-2.0-flash | Previous generation, stable |

...many more

---

### 2. Screenshot Analysis

Capture any region of your screen and send it to AI for analysis.

**How it works:**
- Click the screenshot button
- Main window minimizes automatically
- Select screen region with configurable cursor style
- Optional: Add a text prompt with your screenshot

**Settings:**
- Cursor type: Arrow (default), Cross, Hand, IBeam
- Screenshot preview: Disabled by default when screen protection is ON

---

### 3. Screen Capture Protection

The application window is invisible during screen recordings and screen shares.

**How it works:**
- Window appears invisible in:
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

---

### 4. Always on Top

Keep the application window above all other windows.

**How it works:**
- Temporarily disabled during payment flow to allow browser access
- Automatically restored after payment completion

---

### 5. App Version Management
- **Blocks app if current version is below minimum required version**

---

### 6. Subscription & Payment

Pro subscription with integrated payment gateway.

**Subscription Tiers (Example):**

| Feature | FREE (Trial) | PRO |
|---------|--------------|-----|
| Trial Period | 3 days | - |
| AI Chat | Unlimited | Unlimited |
| Screenshot Analysis | Unlimited | Unlimited |
| Screen Protection | Yes | Yes |
| Cloud Sync | Yes | Yes |

**How Payment Works:**
1. User selects an offer from available plans
2. Payment link is created via Cashfree Payment Links API
3. User is redirected to Cashfree payment page
4. App polls for payment status automatically
5. On successful payment, subscription is activated immediately

---

### 7. Email Notifications

Automated email notifications for payment confirmations and promotional offers.

**Requirements:**
- User must provide a valid email address in Settings
  
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

## Support

**Developer Contact:** dev.linuxto5re@gmail.com

For bug reports, feature requests, or general inquiries, please contact the developer email above.

---

## License

Proprietary - All Rights Reserved

Copyright 2026 Incognito AI Pro

---

*Last Updated: January 18, 2026*
