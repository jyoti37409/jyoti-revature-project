
#  Revised Acceptance Testing Report  
**Project Name:** Planetarium Web Application  
**Sprint:** Sprint 1
**Tester:** Jyoti Chiliveri  
**Date Completed:** 2025-04-24  

---

##  Testing Objective
To verify the application fulfills user expectations and product requirements through real-user scenarios and edge case analysis.

---

## 📋 Acceptance Criteria with Test Results

| **User Story** | **Acceptance Criteria** | **Test Result** | **Notes / Defects** |
|----------------|--------------------------|-------------|---------------------|
| **US01**: Register New User | Unique username required |  **Failed** | Error message says "Username not valid" even when it already exists; confusing message. No clear alert for duplicates |
| **US02**: Image Upload | Accept only `.jpg`, `.jpeg`, `.png`; reject others with alert |  **Failed** | PNG file not accepted. No alert, no error message, no server response |
| **US03**: Add Planet / Moon | Reject blank or whitespace-only names |  **Failed** | Names with only spaces (e.g., `"  "`) or repeated space entries are still accepted |
| **US04**: Add Moon | Moon should be added to valid Planet ID |  Passed | Works as expected |
| **US05**: Delete Planet | Should cascade delete associated moons |  Passed | Works correctly |


---

 Key Defects Identified

 Defect 1: Poor Error Feedback on Username
- **Expected:** "Username already exists" error message or alert  
- **Actual:** Shows unrelated message "Username not valid" — user thinks it's a formatting issue

Defect 2: PNG Uploads Not Working
- **Expected:** PNG accepted with preview or confirmation  
- **Actual:** PNG not accepted; no alert, no browser error, no console/network response
Defect 3: Planet/Moon Names Accept Spaces
- **Expected:** Validation must prevent names that are only spaces  
- **Actual:** Submitting `"  "` or `"   Mars"` with multiple spaces allows entry and saves blank/invalid names

---

Summary of Execution

| Metric | Value    |
|--------|----------|
| Scenarios Executed | 67       |
| Scenarios Passed | 62       |
| Scenarios Failed | 6        |
| Critical Failures | 3        |
| Ready for Release |  Not Yet |

---

 Recommendations for Next Sprint

-  Improve **username validation logic and messaging**
-  Implement **file type validation client-side** with proper alerts
-  Add **input sanitation** to strip excess whitespace before submission
-  Ensure every form input failure results in **visible user feedback**

## What went Well
Core Functionalities Worked as Expected:
Major workflows like adding moons to valid planet IDs, deleting planets along with their moons (cascade delete),
successful navigation redirects, and updating the home page table functioned correctly without issues

Data Display and UI Updates are Stable:
After adding or deleting items, the planet and moon tables refresh accurately on the UI, reflecting changes immediately.
→ This confirms that frontend-backend synchronization is working well.
For successful scenarios, users are redirected properly, and expected pages/loaders work without bugs.
→ This provides a good user experience where operations feel smooth when inputs are correct
