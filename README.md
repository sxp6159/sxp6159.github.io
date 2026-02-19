# xVaccine Treatment Planner v2.0 - PWA

A comprehensive Progressive Web App (PWA) for scheduling and managing xVaccine long-acting injectable treatment appointments with flexible dosing windows.

## New Features in v2.0

### 🎯 Dual Treatment Pathways

- **Starting New Treatment**: For patients beginning long-acting injectable treatment
- **Continuation Treatment**: For patients already established on 2-month injection schedules

### 💊 Oral Lead-in Support

For new treatments, choose between:

- **With Oral Lead-in**: Complete 28 days of oral tablets (cabotegravir 30mg + rilpivirine 25mg) before starting injections
- **Direct to Injections**: Begin immediately with monthly injections

### 📅 Monthly vs 2-Month Schedules

- **New Treatment**: Monthly injections (1-month intervals)
- **Continuation Treatment**: Established patients on 2-month injection intervals

### 📊 Progressive Appointment Display

- Initially shows 3 appointments
- "Load More" button to reveal additional appointments (3 at a time)
- Support for up to 12 appointments total
- Helps manage long-term treatment planning

### 🎯 Enhanced Date Management

- **Target Treatment Date**: Consistent monthly date for all injections
- Recommended: Select day 1-28 for consistency across all months
- Warning system for dates after the 28th
- Automatic adjustment for shorter months

### 📍 Detailed Appointment Windows

Each appointment card displays:

- **Earliest Date**: 7 days before target (in red)
- **Target Date**: Optimal treatment date (in green)
- **Latest Date**: 7 days after target (in orange)
- Clear visual indicators for modified dates
- Warnings for appointments outside flexible windows

## Core Features

### 📅 Flexible Treatment Scheduling

- Customizable Target Treatment Date and time
- ±7 day Flexible Dosing Window
- Visual calendar interface with color-coded dates
- Easy date modification for individual appointments

### 🎨 Professional Medical Interface

- Medical-grade design aesthetic
- Clear visual hierarchy and indicators
- Responsive design for all devices
- Intuitive navigation and workflow

### 📄 Comprehensive Export Options

- **PDF Export**: Professional treatment plan with all appointment details
- **Calendar Export**: Individual ICS files for each appointment
  - Compatible with all major calendar applications
  - Includes 24-hour advance reminders
  - Shows target dates and flexible windows

### 📱 Progressive Web App

- Installable on mobile and desktop
- Works offline after initial load
- Native app-like experience
- No data collection - everything stays on device

## Installation

### Quick Start

1. Open `xvaccine-planner-v2.html` in any modern web browser
2. Follow the on-screen workflow

### Install as PWA

1. Open in Chrome, Edge, or Safari
2. Click the "Install" icon in the address bar
3. Add to home screen/desktop
4. Launch like any native application

## Usage Guide

### Step 1: Select Treatment Type

**Starting New Treatment:**

- Choose if beginning long-acting injectable treatment
- Proceeds to oral lead-in selection

**Continuation Treatment:**

- Select if already on established 2-month injections
- Proceeds directly to target date selection

### Step 2: Treatment Initiation (New Treatment Only)

**With Oral Lead-in:**

1. Select this option if completing oral therapy first
2. Enter the date you completed 28 days of oral lead-in:
   - 1 tablet cabotegravir (30mg) daily
   - 1 tablet rilpivirine (25mg) daily
3. System ensures at least 28 days completed before scheduling

**Direct to Injections:**

- Skip oral lead-in
- Begin immediately with monthly injections

### Step 3: Select Target Treatment Date

**Important Considerations:**

- Choose a **consistent day** between 1st-28th of month
- Select a **time** that aligns with clinic hours
- This becomes your recurring Target Treatment Date
- Avoid days 29-31 to prevent issues in shorter months

**System provides:**

- Warning if day selected is after 28th
- Recommendation to choose earlier day for consistency

### Step 4: Review and Manage Schedule

**Initial View:**

- First 3 appointments displayed
- Click "Load Next 3 Appointments" to reveal more
- Can load up to 12 total appointments

**Each Appointment Card Shows:**

- Appointment number
- Selected date and time
- Earliest acceptable date (target - 7 days)
- Target Treatment Date (optimal)
- Latest acceptable date (target + 7 days)
- "Change Date" button for modifications
- Warning if outside flexible window

**Calendar Selection:**

- Green dates = Target Treatment Date (optimal)
- Yellow dates = Flexible Window (±7 days, acceptable)
- White dates = Outside window (requires provider consultation)

## Treatment Schedules

### New Treatment Schedule

| Appointment | Interval  | Typical Timing      |
| ----------- | --------- | ------------------- |
| 1           | Start     | Target date         |
| 2           | +1 month  | Same day next month |
| 3           | +2 months | Same day, 2 months  |
| ...         | Monthly   | Continues monthly   |

### Continuation Treatment Schedule

| Appointment | Interval       | Typical Timing           |
| ----------- | -------------- | ------------------------ |
| 1           | Start          | Target date              |
| 2           | +2 months      | Same day, 2 months later |
| 3           | +4 months      | Same day, 4 months later |
| ...         | Every 2 months | Continues bi-monthly     |

### Flexible Dosing Windows

- **Purpose**: Allow scheduling flexibility while maintaining efficacy
- **Range**: ±7 days from Target Treatment Date
- **Example** (Target = 15th of month):
  - Earliest: 8th of month
  - Target: 15th of month
  - Latest: 22nd of month

### Best Practices

1. **Maintain target date**: Return to original Target Treatment Date when possible
2. **Use flexible window judiciously**: Only when necessary
3. **Communicate changes**: Inform healthcare provider of modifications
4. **Plan ahead**: Schedule appointments early to ensure availability on target dates

## Export Features

### PDF Export

**Includes:**

- Treatment type and schedule interval
- Oral lead-in status (if applicable)
- Complete appointment schedule (up to currently loaded appointments)
- For each appointment:
  - Scheduled date and time
  - Target date
  - Earliest and latest dates
  - Warnings for dates outside flexible window
- Important treatment information
- Professional formatting for healthcare providers

**Use Cases:**

- Share with healthcare team
- Keep in medical records
- Reference during appointments
- Insurance documentation

### Calendar Export (ICS Files)

**Features:**

- Individual file for each appointment
- Import into any calendar application:
  - Google Calendar
  - Apple Calendar
  - Microsoft Outlook
  - Any ICS-compatible app
- Includes:
  - Appointment date and time
  - 24-hour advance reminder
  - Target date reference
  - Flexible window information
  - Location field (customizable)

**Import Instructions:**

- **Google Calendar**: Settings → Import & Export → Select file
- **Apple Calendar**: File → Import → Select file
- **Outlook**: File → Open & Export → Import/Export → Select file

## Technical Details

### Browser Compatibility

- ✅ Chrome/Edge 90+
- ✅ Safari 14+
- ✅ Firefox 88+
- ✅ Mobile browsers (iOS Safari, Chrome Android)

### Files Structure

```
xvaccine-planner-v2/
├── xvaccine-planner-v2.html  # Main application (v2.0)
├── manifest.json             # PWA manifest
├── sw.js                     # Service worker
└── README-v2.md             # This file
```

### Customization Options

**Modify Treatment Intervals:**

```javascript
// In generateSchedule() function
const intervalMonths = treatmentType === "continuation" ? 2 : 1;
// Change numbers to adjust intervals
```

**Adjust Flexible Window:**

```javascript
// Search for: addDays(appointmentDate, -7) and addDays(appointmentDate, 7)
// Change 7 to desired number of days
```

**Change Maximum Appointments:**

```javascript
const MAX_APPOINTMENTS = 12;
// Modify this constant at the top of the script
```

**Modify Initial Display Count:**

```javascript
let visibleAppointments = 3;
// Change initial number of appointments shown
```

## Clinical Guidelines

### Oral Lead-in Requirements

- **Duration**: Minimum 28 days
- **Medications**:
  - Cabotegravir: 30mg tablet once daily
  - Rilpivirine: 25mg tablet once daily
- **Purpose**: Assess tolerability before initiating injections
- **Completion**: Must be verified before scheduling first injection

### Target Treatment Date Selection

**Recommended:**

- Day 1-28 of month for consistency
- Time aligned with clinic hours
- Consideration of patient schedule and availability

**Avoid:**

- Days 29-31 (causes issues in shorter months)
- Times outside clinic operating hours

### Flexible Window Usage

**When to Use:**

- Patient scheduling conflicts
- Clinic closure or availability issues
- Holiday periods
- Unavoidable travel

**When to Avoid:**

- Routine scheduling (maintain target date when possible)
- Convenience only (without necessity)

**Outside Window:**

- Requires healthcare provider consultation
- May impact treatment efficacy
- Document reasons for deviation

## Privacy & Security

- **Zero data collection**: All data remains on your device
- **No server communication**: Completely offline-capable
- **No tracking**: No analytics or third-party services
- **Local storage only**: Schedule data stored in browser
- **No account required**: No login or registration

## Accessibility Features

- Keyboard navigation support
- High contrast color scheme
- Large touch targets (48px minimum)
- Clear visual indicators and labels
- Semantic HTML structure
- ARIA labels where appropriate
- Responsive text sizing

## Troubleshooting

### Common Issues

**Q: Oral lead-in date won't accept my date**
A: Ensure the date is at least 28 days ago or less. The system validates that oral therapy was completed for the required duration.

**Q: Can't select dates after the 28th**
A: You can, but the system warns about potential issues in shorter months. For consistency, select day 1-28.

**Q: "Load More" button not working**
A: This appears only when there are more appointments to display. Maximum is 12 appointments.

**Q: Calendar export files not opening**
A: Ensure you have a calendar application installed. Try opening the .ics file directly - most calendar apps will automatically detect and import it.

**Q: Modified dates reverting**
A: Changes are stored in browser memory during the session. Export your schedule before closing the browser.

**Q: PDF not downloading**
A: Ensure pop-ups are allowed and JavaScript is enabled in your browser.

**Q: PWA install option not showing**
A: Use HTTPS or localhost. Try Chrome or Edge browsers. Ensure manifest.json is accessible.

## Future Enhancements

Planned features for future versions:

- Appointment reminder notifications
- Integration with healthcare provider systems
- Multi-language support
- Appointment history tracking
- Missed appointment tracking
- Provider portal for schedule review
- SMS/email reminder integration
- Data export/import functionality

## Version History

### v2.0.0 (Current)

- Added dual treatment pathways (New/Continuation)
- Oral lead-in workflow and validation
- Monthly vs 2-month schedule support
- Progressive appointment loading (3 at a time, up to 12)
- Enhanced appointment cards with earliest/latest dates
- Target date day-of-month validation and warnings
- Appointment time selection
- Improved PDF export with detailed information
- Enhanced calendar export with all appointment details

### v1.0.0

- Initial release
- Basic 4-dose vaccination schedule
- Flexible dosing windows
- PDF and ICS export
- PWA functionality

## Medical Disclaimer

This application is a scheduling tool only. It does not provide medical advice, diagnosis, or treatment recommendations. Always consult with your healthcare provider for:

- Medical advice and treatment decisions
- Determining appropriate treatment intervals
- Assessing suitability for oral lead-in
- Managing missed or delayed appointments
- Any questions about your treatment plan

Do not use this app to make medical decisions without professional guidance.

## Support

For questions about:

- **Medical treatment**: Consult your healthcare provider
- **Appointments**: Contact your clinic or treatment center
- **Technical issues**: Check troubleshooting section above

## License

Copyright © 2026 xVaccine Treatment Planner
All rights reserved.

---

**Note**: This is a treatment planning tool designed to help patients and healthcare providers manage long-acting injectable treatment schedules. Always follow your healthcare provider's specific instructions and guidance.
