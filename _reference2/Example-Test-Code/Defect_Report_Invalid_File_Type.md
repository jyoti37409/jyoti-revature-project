
#  Defect Report: Invalid File Type Not Triggering Alert

**Defect ID:** PLAN-IMG-001  
**Title:** No validation message shown for unsupported image file (.gif)  
**Reported By:** Jyoti Chiliveri  
**Module:** Planet Registration    
**Severity:** Medium  
**Priority:** High  
**Status:** New  
**Assigned To:** [Developer/Team Name]

---

##  Description

When a user attempts to register a new planet and uploads an unsupported image file format (e.g., `.gif`), the application accepts the input without any alert or visible error message.

The test expects a validation alert like `"Invalid file type"`, but no alert appears. This results in a `TimeoutException` in Selenium while waiting for the alert, causing automated tests to fail.

---

##  Steps to Reproduce

1. Navigate to the **Planetarium Home Page**
2. Log in as a valid user
3. Select **Planet** from the dropdown
4. Enter valid planet name: `"PlanetWithGIF"`
5. Upload an unsupported file type: `"C:\Users\havisha\Downloads\testing.gif"`
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

---


