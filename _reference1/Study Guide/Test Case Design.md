# Test Case Design Study Guide

## Test Case Intro

### Test Case Introduction
A **test case** is a set of **preconditions**, **inputs**, **actions**, and **expected results**. It is a formal collection of resources needed to perform the actual testing you need done. The test case outlines the specific steps and criteria to verify that a particular function or feature of a system works as intended. When designing test cases it is good to keep the **testing principles** in mind

### Testing Principles
- **Testing reveals defects, not their absence**
    - The discovery of zero defects does not imply that there are no defects in the tested software. It simply means that the testing performed did not uncover any issues. There could still be undetected defects that were not exposed by the specific tests conducted
- **Exhaustive testing is impossible**
    -  It is impractical to test every possible scenario and input combination. Therefore, testing should be focused on critical features and requirements first. Prioritizing these areas ensures that the most important aspects of the software are thoroughly evaluated, reducing the risk of significant defects in key functionalities
- **Test early**
    - The sooner testing is started, the earlier defects will be caught. **Static testing**, such as code reviews and inspections, should begin as soon as possible to identify issues early in the development process. **Dynamic testing**, which involves executing the code, should be started when feasible to uncover defects that may not be evident through static testing alone. Early testing helps in detecting and addressing defects promptly, reducing the cost and effort required for later fixes
- **Defects cluster**
    - Any feature or requirement with one or more defects warrants extra testing. Defects tend to cascade, especially if the defect is at the start of any data transformation or if other features rely on the data involved in the defect. This means that a single defect can lead to multiple issues downstream, making it crucial to thoroughly test areas where defects have been identified to prevent further complications
- **Tests wear out**
    - Also called the "pesticide paradox": over time, your tests will eventually exhaust all the defects they can find. When this happens, it is worth considering additional tests to accommodate the addition of new features or requirements. However, don't remove old tests when they stop discovering defects; you can still use them for regression testing. This ensures that previously fixed defects do not reappear and that the software remains stable as new changes are introduced
- **Testing is contextual**
    - There is no overarching universal testing practice. Your test objects and objectives should determine how you approach the testing process. This means that the methods and strategies you use for testing should be tailored to the specific context of the software, including its features, requirements, and intended use. Adapting your testing approach to fit the unique aspects of each project ensures more effective and relevant testing outcomes
- **Absence of error fallacy**
    - Just because there are no defects does not mean your application was built correctly. All tests may pass, but the application may still fail to meet all client requirements. This highlights the importance of not only focusing on defect detection but also ensuring that the software aligns with the client's needs and expectations. Comprehensive testing should include validation against requirements to confirm that the application fulfills its intended purpose

## Testing Pyramid
When designing tests it is useful to keep the **Testing Pyramid** in mind. This **Test Pyramid** is a visual representation of the abundance of tests based on certain "levels" of testing. More tests exist at the lower level of the pyramid than at the top because they exist at a lower level of abstraction (unit tests), whereas fewer exist at the top and focus on a higher layer of abstraction (system tests, UI tests, UAT)
![testing pyramid](testing-pyramid.png)

### Unit Testing
**Unit testing** is the most granular level of software testing, focusing on individual components or units of a program. This type of testing is performed in isolation, meaning each component is tested independently without relying on other parts of the system. To achieve this, data mocking is often employed to simulate the necessary inputs and outputs, ensuring that the unit functions correctly on its own

### Integration Testing
**Integration testing** involves testing components that have dependencies to ensure they work together correctly. This type of testing checks that the interactions between different components are functioning as expected. Typically, logically related modules are tested as a group to verify their combined behavior and identify any issues that may arise from their use together

### System Testing
**System testing** involves evaluating the entire application as a whole to ensure it functions correctly. This comprehensive testing checks that all components and modules work together seamlessly, verifying the overall behavior and performance of the application. By conducting system testing, developers can identify and resolve any issues that appear when the various components of the system are engaged with each other: these defects can be difficult to detect at lower levels of testing on the **testing pyramid**

### Acceptance Testing
**Acceptance testing** involves evaluating a range of individual components up to the entire application to determine if they meet the required standards of "acceptability." This process often includes subjective measurements and assessments, such as evaluating how intuitive the application is to use. **Acceptance testing** can also validate that user, stakeholder, or regulatory requirements are being met by the application. While manual testing is frequently necessary for subjective evaluations, automation tools can be employed for certain aspects of **acceptance testing** to streamline the process. This ensures the application not only functions correctly but also meets the expectations and needs of its users and stakeholders

## Black Box Testing

### Black Box Testing Introduction
**Black box testing** is an approach to software testing where tests are built and executed based on the system specifications, design documentation, and a general understanding of how the application is supposed to work. It is called **black box testing** because the underlying implementation, including the source code and application environment, is unavailable to the tester and should not influence the design of the tests. This approach makes system and acceptance testing more prevalent, as it focuses on verifying the application's functionality and behavior from an external perspective without considering its internal workings

### Use Case Testing
A **use case** is a tool used in software development to define the required user interactions for creating or modifying an application. It helps developers and testers identify test scenarios that cover the entire system from start to finish. **Use Case Testing**, a part of **black box testing**, can help ensure the system meets both technical requirements and user expectations. Since it is a **black box technique**, **use cases** are often used to further develop test cases at the system and acceptance levels; use cases serve as an organizational tool for developing and grouping tests by describing real-world scenarios of how end users interact with the system and what should happen based on those interactions

### State Transition Diagram
Anytime you have a system or service where there are multiple "states" to consider, a **state transition diagram** can be used to organize your data before creating your test cases. A **state transition diagram** is simply a flow chart that shows the various states in the service and the way they connect to each other, including at minimum a starting state and one or more ending states. For instance, if you are testing a reimbursement system you may have the following states of a reimbursement request: "pending", "accepted", "rejected". Each state of the request would have different actions, expectations, and other general requirements associated with it, and if you have your states organized in a **state transition diagram** it will be easier to organize the tests you create and prevent redundant overlap

### Boundary Value Analysis
When creating test data for business requirements, there will often be "boundaries" that are specified by those requirements. For instance, if testing a registration feature, there may be limits on how many characters can be included in the username. These restrictions create your natural "boundaries", which make for great determiners for your test data. Determining what these boundaries are and organizing your test data by those boundaries is called **boundary value analysis**. Typically when performing **boundary value analysis** you would determine your boundaries and then organize your valid and invalid data by selecting values just in the boundaries of requirements and just outside the boundaries. You would then let these values represent their "class" of data in your tests (lower out of bounds, lower inner bound, upper inner bound, upper out of bounds)

### Equivalence Partitioning
Similar to boundary value analysis, **equivalence partitioning** is a technique where you divide your test data in to "classes" of data and use a single value to represent the entirety of the class. This technique is useful when you don't have requirements that create natural boundaries for your data, or when the amount of potential test data is overwhelmingly large. By implementing **equivalence partitioning** you can optimize the number of test cases you need while keeping your tests from being redundant. For instance, if you are testing a profile picture upload feature, it wouldn't make sense to try and upload every kind of non-image file: there are simply too many. Instead, one invalid file type would represent a "class" of files, which you can make as large/small as necessary. This single representative can be used instead of all possible values, which can significantly streamline your testing process

### Error Guessing
**Error guessing** is a black box testing technique where the tester leverages experience and prior knowledge of similar applications to make educated guesses about potential failure points in the software being tested. This method involves designing tests around these educated guesses to uncover defects that might not be evident through other testing techniques. Error guessing is particularly useful when requirements are minimal or ambiguous, or when trying to create new tests. By anticipating where errors are likely to occur, testers can create targeted test cases that effectively identify defects

## White Box Testing

### White Box Testing Introduction
**White box** testing is an approach to software testing where the tester uses the internal structure of the application to create tests. This includes access to the source code, internal configurations, application environment, and any other internally used resources. By leveraging this detailed internal knowledge, testers can design tests that thoroughly examine the application's internal workings. All levels of testing, from unit to acceptance testing, can be performed using white box testing, ensuring comprehensive coverage and the identification of potential issues within the application's code and architecture

### Statement Testing
**Statement testing** is the practice of writing tests to execute statements in source code. This type of testing can be used to detect defects caused by developer error. It can also be used to help identify parts of the code that are not being reached, which might indicate dead code or logic errors. Statement testing is often used in combination with other testing techniques to narrow down the location where errors are creating defects. **Statement testing** is often measured by code coverage: the number of lines of code involved in a test case. An application with 80% code coverage executes 80% of the lines of code during testing. Note that it is not always necessary to achieve 100% code coverage: you may use other testing techniques or tools to test parts of your code that are not part of your code coverage report

### Exploratory Testing
**Exploratory Testing** is a software testing technique where testers actively engage with the application to discover its functionalities and potential issues. Unlike traditional testing methods that rely on predefined test cases, exploratory testing relies on the tester’s creativity, intuition, and experience. Testers explore the software without a specific plan, learning about its behavior and identifying defects in real-time. This method is particularly useful when requirements are unclear or incomplete, as it allows testers to adapt and respond to the software’s actual performance. Exploratory testing encourages testers to think critically and investigate the application from various angles

## General Techniques

### Decision Table Testing
When a user must make a string of "decisions" using a service, such as providing multiple inputs to a form, a **decision table** can be used to organize the inputs and expected results of providing the data. For instance, if testing a login feature, you could craft a decision table where all combinations of "valid" usernames and passwords are matched with "invalid" usernames and passwords, and for each possible combo list the expected results (logged in or rejected). By organizing the data combinations in a **decision table** you can ensure coverage of all requirements with your tests and also reduce redundancy in your test suite

### Checklist Testing
**Checklist testing** involves following a pre-determined list of actions to perform your testing. This method is akin to checking items off a grocery or chore list, ensuring that each step is completed and accounted for. The checklist typically includes specific tasks or conditions that need to be met, such as verifying login functionality, checking data input fields, or ensuring that navigation links work correctly. By systematically going through the checklist, testers can ensure that all critical aspects of the software are examined. This approach helps in maintaining consistency and thoroughness in testing, as it provides a clear and structured way to track what has been tested and what still needs attention. Additionally, checklist testing can be particularly useful in regression testing, where previously tested functionalities are re-verified to ensure that new changes have not introduced any new defects

### Conditional Testing
**Conditional testing** involves grouping different combinations of conditions to determine the expected outcomes for each scenario. For example, if a user is logged in, they should be able to see user information on the homepage; if not, they should not be able to access the homepage. This method of organization is useful in "either/or" situations, or when multiple conditions must be checked to determine the expected outcome

### Data Driven Testing
**Data-driven** testing involves executing test scripts using data from external sources, such as databases, spreadsheets, or CSV files. This method allows testers to run the same set of test scripts with different sets of data inputs, similar to using a recipe with various ingredients to create different dishes. The data typically includes various input values and expected results, such as user credentials, form entries, or transaction details. By systematically applying different data sets, testers can ensure that the application behaves correctly under various conditions. This approach helps in improving efficiency and maintainability in testing, as it reduces the number of test scripts needed and makes it easier to update test data. Additionally, data-driven testing enhances test coverage by validating multiple scenarios, ensuring that the software performs reliably across a wide range of inputs