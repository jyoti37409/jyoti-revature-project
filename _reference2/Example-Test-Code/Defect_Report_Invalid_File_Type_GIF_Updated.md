
#  Defect Report: No Alert Shown for Unsupported Image Type (.gif)

**Defect ID:** PLAN-IMG-002  
**Title:** No alert shown for unsupported image file type `.gif` during planet registration  
**Reported By:** Jyoti Chiliveri  
**Module:** Planet Registration
**Build Version:** v1.0  
**Severity:** Medium  
**Priority:** High  
**Status:** New  
**Assigned To:** [Developer/Team Name]

---

##  Description

When a user attempts to register a new planet and uploads a `.gif` image (which is not among the allowed types: `.jpeg`, `.jpg`, or `.png`), the application accepts the image or silently fails without showing any alert or validation message.

This behavior was confirmed both via **automated test** and **manual testing**:
- Automated test fails with `TimeoutException` waiting for an alert.
- Manual testing shows **no alert, no message, and no response at all**.

---

##  Steps to Reproduce

1. Navigate to the **Planetarium Home Page**
2. Log in as a valid user
3. Select **Planet** from the dropdown
4. Enter a valid planet name: `"PlanetWithGIF"`
5. Upload the file: `"C:\Users\havisha\Downloads\testing.gif"`
6. Click the **Submit** button

---

##  Expected Result

> An alert should appear saying:  
> `"Invalid file type"`  
> Or a visible inline validation message near the upload input

---

##  Actual Result

> No alert is displayed. The UI does not inform the user that `.gif` is not supported.  
> Selenium test fails with:  
> `TimeoutException: waiting for alert to be present (tried for 10 seconds)`  
> Manual test shows **no error, no alert, and no UI response**.

---



##  Suggested Fix

- Add client-side validation to the `<input type="file">` element:  
  `accept="image/png, image/jpeg"`
- Implement backend file type validation based on MIME type
- Display a clear error alert like `"Invalid file type"` or an inline message
