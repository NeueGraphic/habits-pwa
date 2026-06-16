# Habits App — App Store Listing Copy
## Ready to paste into App Store Connect

---

## APP NAME
Habits — Daily Routine Tracker

## SUBTITLE (30 chars max)
Build streaks. Stay consistent.

---

## DESCRIPTION (4,000 chars max)

Habits is the simplest, most satisfying way to track your daily routines. No subscriptions. No accounts. No data collection. Just your habits, your streaks, and your progress.

**BUILD BETTER ROUTINES**
Create habits for anything — morning workouts, reading, hydration, meditation, journaling, or any daily goal you want to stick with. Add an emoji icon and colour to make each habit feel personal.

**STREAK TRACKING THAT MOTIVATES**
Nothing builds momentum like a streak. Habits tracks consecutive days completed and shows you your current and longest streaks so you always know what you're working toward.

**SEE YOUR WEEK AT A GLANCE**
The weekly dot view shows the last 7 days for every habit, so you can instantly see patterns in your consistency. The daily summary ring shows today's completion rate across all your habits.

**DETAILED HISTORY**
Tap into any habit to see a 10-week heatmap of your completion history, your all-time stats, and your 28-day completion rate.

**COMPLETELY PRIVATE**
Habits stores everything on your device. Nothing is sent to any server. No account required. No tracking. Your data is yours.

**DESIGNED FOR iOS**
Built with Apple's Human Interface Guidelines from the ground up. Respects your system appearance (light or dark mode), feels native on any iPhone, and works completely offline.

---

How to use Habits:
1. Tap + to create your first habit
2. Check it off each day to build your streak
3. Tap a habit to expand it and see your weekly progress
4. Long press to open the full detail view with your history heatmap

---

## KEYWORDS (100 chars, comma-separated — no spaces after commas)
habit tracker,daily routine,streak counter,productivity,goal tracker,self improvement,wellness

## PROMOTIONAL TEXT (170 chars — shown above description, can change anytime)
The simplest habit tracker for iPhone. No subscription, no account, no ads. Just build your streaks and stay consistent every day.

---

## WHAT'S NEW (Version 1.0)
Welcome to Habits! Track your daily routines, build streaks, and see your progress with a beautiful 10-week history heatmap. Everything is stored privately on your device — no account needed.

---

## SUPPORT URL
https://yourdomain.com/support

## MARKETING URL (optional)
https://yourdomain.com/habits

## PRIVACY POLICY URL (REQUIRED)
https://yourdomain.com/habits/privacy-policy

---

## APP STORE CATEGORIES
Primary:   Productivity
Secondary: Health & Fitness

## AGE RATING
4+ (no objectionable content)

## PRICING
$2.99 (Tier 3) — or $1.99 (Tier 2)
(One-time purchase, no subscription)

---

## SCREENSHOT CAPTIONS
(These appear on your screenshots in the App Store)

Screenshot 1 — Home screen with habits list
Caption: "Track every habit. Hit every day."

Screenshot 2 — Check-off animation
Caption: "One tap to log. Instant satisfaction."

Screenshot 3 — Weekly dot view expanded
Caption: "See your week. Spot your patterns."

Screenshot 4 — Detail / heatmap screen
Caption: "10 weeks of history. All on your device."

Screenshot 5 — Onboarding / add habit sheet
Caption: "Set up in seconds. No account needed."

---

## REVIEW NOTES FOR APPLE
(Paste into the "Notes" field in App Store Connect)

This app is a habit tracking utility. All data is stored locally using the device's localStorage / WKWebView local storage — no network requests are made and no account or login is required.

Demo habits may be added on first launch to demonstrate functionality; these can be deleted by the user.

The app works completely offline and requires no special permissions (no camera, location, notifications, or contacts access).

Test account: N/A — no account system exists.

---

## CHECKLIST BEFORE SUBMISSION

[ ] App icon uploaded (1024×1024px, no alpha channel, no rounded corners — Apple adds those)
[ ] Screenshots uploaded for iPhone 6.9" (iPhone 16 Pro Max) — REQUIRED
[ ] Screenshots uploaded for iPhone 6.5" (iPhone 15 Plus) — required if supporting older devices
[ ] iPad screenshots if you selected iPad support
[ ] Privacy Policy URL live and accessible
[ ] Support URL live and accessible  
[ ] Age rating questionnaire completed
[ ] Pricing set
[ ] App Review notes filled in
[ ] Build uploaded via Xcode (Archive → Distribute → App Store Connect)
[ ] No placeholder content in the app (demo habits can remain)
[ ] App tested on real device (not just Simulator)
[ ] Dark mode tested
[ ] App does not crash on launch on clean install
[ ] Privacy manifest (PrivacyInfo.xcprivacy) added to Xcode project

---

## XCODE PROJECT NOTES

When creating your WKWebView wrapper in Xcode:

1. File → New Project → App (iOS)
2. Set Bundle Identifier: com.yourname.habits (must be unique)
3. Deployment Target: iOS 16.0 (covers ~98% of devices)
4. Add WKWebView to your main ViewController
5. Load index.html from the app bundle (not from a URL)
6. In Info.plist, set:
   - NSAppTransportSecurity → NSAllowsLocalNetworking → YES
   - UIStatusBarStyle → UIStatusBarStyleDefault
   - UISupportedInterfaceOrientations → Portrait only (recommended for v1)
7. Add PrivacyInfo.xcprivacy with empty accessed API types (since you use no APIs)
8. Set CFBundleDisplayName to "Habits"

WKWebView Swift snippet:
```swift
import WebKit

class ViewController: UIViewController {
    var webView: WKWebView!

    override func loadView() {
        let config = WKWebViewConfiguration()
        config.preferences.setValue(true, forKey: "allowFileAccessFromFileURLs")
        webView = WKWebView(frame: .zero, configuration: config)
        view = webView
    }

    override func viewDidLoad() {
        super.viewDidLoad()
        if let url = Bundle.main.url(forResource: "index", withExtension: "html") {
            webView.loadFileURL(url, allowingReadAccessTo: url.deletingLastPathComponent())
        }
    }
}
```
