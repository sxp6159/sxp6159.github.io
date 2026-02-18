# xVaccine Treatment Planner - PWA

A Progressive Web App (PWA) for scheduling and managing xVaccine treatment appointments with flexible dosing windows.

## Features

### 📅 Treatment Scheduling
- 4-dose vaccination schedule over 1 month
- Automatically calculates optimal treatment dates
- Interactive calendar interface for date selection

### 🎯 Flexible Dosing Windows
- **Target Treatment Dates**: Optimal dates highlighted in green
- **Flexible Window**: ±7 days from target date (yellow highlight)
- Visual feedback for dates outside the flexible window
- Warning system for oral bridging consideration

### 📱 Progressive Web App
- Installable on mobile and desktop devices
- Works offline after initial load
- Responsive design for all screen sizes
- Native app-like experience

### 📄 Export Options
- **PDF Export**: Professional treatment plan document
- **Calendar Export**: ICS files for each appointment
  - Compatible with Google Calendar, Apple Calendar, Outlook
  - Includes reminders 24 hours before each appointment
  - Contains target dates and flexible windows

## Installation

### Option 1: Direct Use
1. Open `xvaccine-planner.html` in any modern web browser
2. The app will work immediately

### Option 2: Install as PWA (Recommended)
1. Open the app in Chrome, Edge, or Safari
2. Look for the "Install" icon in the address bar
3. Click "Install" to add to your home screen/desktop
4. Launch the app like any native application

### Option 3: Host on Web Server
```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx http-server

# Then visit http://localhost:8000/xvaccine-planner.html
```

## Usage Guide

### Step 1: Select First Treatment Date
1. Choose your desired first vaccination date
2. Click "Generate Treatment Schedule"
3. The system calculates all 4 doses:
   - Dose 1: Day 0 (your selected date)
   - Dose 2: Day 7
   - Dose 3: Day 14
   - Dose 4: Day 28

### Step 2: Review and Modify Schedule
- View all scheduled appointments
- **Target dates** are shown in green on the calendar
- **Flexible windows** (±7 days) are shown in yellow
- Click "Change Date" on any dose to modify
- Calendar shows:
  - Green = Target Treatment Date (optimal)
  - Yellow = Flexible Dosing Window (acceptable)
  - White = Other dates (requires provider consultation)

### Step 3: Export Your Schedule

#### Download PDF
- Comprehensive treatment plan document
- Includes all dates and flexible windows
- Professional format for healthcare providers
- Contains important notes and reminders

#### Export to Calendar
- Downloads individual ICS files for each dose
- Import into your calendar app:
  - **Google Calendar**: Settings → Import & Export
  - **Apple Calendar**: File → Import
  - **Outlook**: File → Open & Export → Import
- Includes 24-hour advance reminders
- Shows flexible window information

## Treatment Schedule Details

### Standard Schedule
| Dose | Day Offset | Typical Timing |
|------|-----------|----------------|
| 1    | Day 0     | Start date     |
| 2    | Day 7     | 1 week later   |
| 3    | Day 14    | 2 weeks later  |
| 4    | Day 28    | 4 weeks later  |

### Flexible Dosing Windows
- Each dose has a ±7 day flexible window
- Example for Dose 2 (Day 7):
  - Earliest: Day 0
  - Target: Day 7
  - Latest: Day 14

### Important Guidelines
- **Target dates** provide optimal treatment efficacy
- **Flexible windows** allow scheduling flexibility
- Dates outside flexible windows require:
  - Healthcare provider consultation
  - Consideration of oral bridging therapy
  - Medical justification

## Technical Details

### Browser Compatibility
- ✅ Chrome/Edge 90+
- ✅ Safari 14+
- ✅ Firefox 88+
- ✅ Mobile browsers (iOS Safari, Chrome Android)

### Dependencies
- jsPDF 2.5.1 (for PDF generation)
- Google Fonts: DM Serif Display, Source Sans 3

### Files Structure
```
xvaccine-planner/
├── xvaccine-planner.html  # Main application
├── manifest.json          # PWA manifest
├── sw.js                  # Service worker
└── README.md             # This file
```

### Customization

You can customize the treatment schedule by modifying the `TREATMENT_CONFIG` object in the HTML file:

```javascript
const TREATMENT_CONFIG = {
    doses: [
        { number: 1, dayOffset: 0, name: "First Dose" },
        { number: 2, dayOffset: 7, name: "Second Dose" },
        { number: 3, dayOffset: 14, name: "Third Dose" },
        { number: 4, dayOffset: 28, name: "Fourth Dose" }
    ],
    flexibleWindowDays: 7  // Change this to adjust window size
};
```

## Privacy & Data

- **No data collection**: All data stays on your device
- **No server communication**: Works entirely offline
- **No tracking**: No analytics or third-party services
- **Local storage only**: Schedule data stored in browser

## Accessibility

- Keyboard navigation supported
- High contrast color scheme
- Large touch targets for mobile
- Clear visual indicators
- Semantic HTML structure

## Support & Troubleshooting

### Calendar Export Issues
**Problem**: ICS files not importing
**Solution**: Try opening the ICS file directly - most calendar apps will detect and import it automatically

### PDF Download Issues
**Problem**: PDF not generating
**Solution**: Ensure JavaScript is enabled and pop-ups are allowed

### Date Selection Issues
**Problem**: Cannot select dates
**Solution**: Ensure cookies/storage is enabled in your browser

### PWA Installation Issues
**Problem**: Install button not appearing
**Solution**: 
- Use HTTPS or localhost
- Ensure manifest.json is accessible
- Try Chrome or Edge browsers

## Future Enhancements

Potential features for future versions:
- Email reminders
- SMS notifications
- Multi-language support
- Appointment history tracking
- Integration with health records
- Provider portal for schedule review

## License

Copyright © 2026 xVaccine Treatment Planner
All rights reserved.

## Medical Disclaimer

This application is a scheduling tool only. Always consult with your healthcare provider for medical advice. Do not use this app to make medical decisions without professional guidance.

## Version History

- **v1.0.0** (Current)
  - Initial release
  - 4-dose treatment schedule
  - Flexible dosing windows (±7 days)
  - PDF export
  - ICS calendar export
  - PWA functionality
  - Offline support

---

For questions or support, consult your healthcare provider or medical facility.
