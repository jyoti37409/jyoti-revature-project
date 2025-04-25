
#  Defect Report: Planet with PNG Image Not Saved or Displayed

**Defect ID:** PLAN-IMG-003  
**Title:** Planet with supported `.png` image fails to save or display on the Planetarium homepage  
**Reported By:** Jyoti Chiliveri  
**Module:** Planet Registration  
**Environment:** Windows 11, Chrome v135, Java 23.0.2, Selenium 4.31, Cucumber 7.22.0  
**Build Version:** v1.0  
**Severity:** Medium  
**Priority:** High  
**Status:** New  
**Assigned To:** [Developer/Team Name]

---

##  Description

When attempting to register a new planet with a supported `.png` image file (`sun123.png`), the application does not display the planet on the homepage table after submission.

The automated test fails on an assertion that checks if the planet name is displayed. The image upload does not throw any errors, but the planet is not shown or saved, which indicates that `.png` files might not be properly handled or saved by the backend or UI.

---

##  Steps to Reproduce

1. Navigate to the **Planetarium Home Page**
2. Log in as a valid user
3. Select **Planet** from the dropdown
4. Enter planet name: `"Earth_2025"`
5. Upload image: `"C:\Users\havisha\Downloads\sun123.png"`
6. Click the **Submit** button

---

##  Expected Result

> The planet `"Earth_2025"` should be saved and displayed in the Planetarium table with the uploaded `.png` image.

---

##  Actual Result

> No error shown, but the planet is not visible in the UI.  
> Automated test fails with:  
> `Planet 'Earth_2025' not found in table.`  
> AssertionError from:  
> `Assert.assertTrue(addPlanetPage.isPlanetDisplayed(planetName));`

---


##  Suggested Fix

- Ensure backend logic correctly handles `.png` file extensions and MIME types
- Check if the image is saved and linked to the planet object in DB
- Ensure the UI reloads or refreshes the planet list after submission
- Validate `.png` support in both frontend file validation and backend storage logic
