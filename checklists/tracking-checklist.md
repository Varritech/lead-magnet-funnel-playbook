# Tracking Checklist for a Meta Lead Funnel

Run this before you spend on ads. A funnel with broken tracking teaches the ad algorithm nothing.

## 1. The Lead event

- [ ] The Lead event fires **on form submit**, not on page load
- [ ] It fires once per submit, not twice
- [ ] It does not fire when the form fails validation
- [ ] The thank-you page does not fire Lead again on refresh

## 2. Verify in the real browser

Test tools can say "installed" while the real page is broken.

- [ ] Open the live page in a normal browser window with your ad blocker off
- [ ] Open your pixel helper extension or Meta Events Manager test events
- [ ] Submit the form with a test email
- [ ] See a Lead event arrive in Events Manager within a minute
- [ ] Repeat on a phone
- [ ] Check the form still works if the user has a tracking blocker on (the lead is saved even if the event is blocked)

## 3. The server-side event

Browser events get blocked. Send the same event from your server too.

- [ ] Your form handler sends a Lead event to the Conversions API
- [ ] The browser and server events share the **same event ID**, so Meta de-duplicates them
- [ ] You send hashed email (and phone if collected)
- [ ] Events Manager shows both sources and no duplicate count
- [ ] Event match quality is shown as good or better

## 4. The Purchase event

- [ ] The low-ticket offer fires Purchase with value and currency
- [ ] The purchase is linked to the lead by email so you can count purchases from leads
- [ ] Test one purchase end to end

## 5. Campaign setup

- [ ] The ad set optimization event is **Lead**
- [ ] Every ad points to the right page
- [ ] UTM parameters are on the ad link so you can tell ads apart
- [ ] Switch to Purchase optimization only after you have a steady flow of purchases

## 6. Weekly check

- [ ] Lead count in your database matches Lead events in Events Manager (close, not exact)
- [ ] Count purchases from leads per ad
- [ ] Pause ads that bring leads who never buy
