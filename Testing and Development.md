## Comprehensive Notes on Testing and Development

---

### **1. Code Review**
**Definition**: Reviewing source code to catch bugs, improve quality, and ensure it follows coding standards.

**Key Points:**
- Detects security issues and logic errors early.
- Encourages knowledge sharing and collaboration among developers.
- Improves code readability and maintainability.

**Examples:**
1. A developer finds a missing null check during a code review.
2. Reviewing code uncovers repeated code that can be refactored into a reusable function.
3. A peer review identifies inconsistent variable naming.

**Flashcard:**
**Q**: What are the benefits of code review?  
**A**: Improves quality, detects issues early, and fosters team collaboration.

**Practice Question:**
**Scenario**: A peer review shows hardcoded credentials in the code. What’s the issue?  
**Answer**: Hardcoded credentials are a security risk and should be stored securely, like in environment variables.

---

### **2. Static Application Security Testing (SAST)**
**Definition**: Scanning source code for vulnerabilities without executing it.

**Key Points:**
- Detects security flaws like SQL injection risks and unused variables.
- Produces false positives, requiring manual validation.
- Must be configured for the tech stack being used.

**Examples:**
1. A SAST tool flags a potential buffer overflow in the code.
2. Detecting hardcoded API keys through automated scans.
3. A scan identifies a function with missing input validation.

**Flashcard:**
**Q**: What is a limitation of SAST tools?  
**A**: They can produce false positives and miss business logic flaws.

**Practice Question:**
**Scenario**: A SAST scan flags a security flaw, but the team finds no actual issue. What should you do?  
**Answer**: Treat it as a false positive and review the tool’s configuration.

---

### **3. Software Composition Analysis (SCA)**
**Definition**: Analyzing open-source and proprietary software components for security and license compliance.

**Key Points:**
- Creates a Software Bill of Materials (SBoM).
- Scans for vulnerabilities in dependencies during CI/CD.
- Proactively prevents use of insecure libraries.

**Examples:**
1. An SCA tool highlights a vulnerable version of a library.
2. Blocking unapproved packages during coding via IDE integration.
3. Scheduling regular scans to ensure no vulnerabilities are introduced.

**Flashcard:**
**Q**: What does an SBoM provide?  
**A**: A detailed inventory of all software components used in a project.

**Practice Question:**
**Scenario**: An SCA scan flags a dependency with known vulnerabilities. What is your next step?  
**Answer**: Update the dependency or apply a security patch.

---

### **4. Unit Tests**
**Definition**: Testing individual functions or components to ensure they work as expected.

**Key Points:**
- Positive tests check expected behavior.
- Negative tests ensure errors are handled gracefully.
- Essential for regression testing.

**Examples:**
1. Testing a function that calculates discounts with valid inputs.
2. A negative test for a login feature handles invalid passwords properly.
3. Ensuring an API returns correct error messages for invalid inputs.

**Flashcard:**
**Q**: Why are unit tests important?  
**A**: They catch bugs early and ensure that code changes don’t break functionality.

**Practice Question:**
**Scenario**: A unit test fails after a new feature is added. What does this indicate?  
**Answer**: The new feature might have introduced a bug or broken existing functionality.

---

### **5. Infrastructure as Code (IaC)**
**Definition**: Writing code to manage infrastructure configurations, ensuring consistency and version control.

**Key Points:**
- Tracks infrastructure changes like application code.
- Simplifies rollbacks and testing.
- Ensures consistent environments across development and production.

**Examples:**
1. Automating server setup with Terraform.
2. Using version control to track infrastructure changes.
3. Deploying identical environments using Ansible scripts.

**Flashcard:**
**Q**: What’s a benefit of IaC?  
**A**: Ensures consistency and reduces manual errors in infrastructure management.

**Practice Question:**
**Scenario**: A deployment fails due to misconfiguration. How can IaC help?  
**Answer**: IaC allows you to quickly roll back to a known stable configuration.

---

### **6. Dynamic Application Security Testing (DAST)**
**Definition**: Testing an application during runtime to find vulnerabilities.

**Key Points:**
- Identifies flaws like weak session handling and XSS.
- Requires permissions and backups before testing.
- Tests APIs and user-facing interfaces for dynamic risks.

**Examples:**
1. Testing a web app for cross-site scripting vulnerabilities.
2. Identifying insecure cookies during runtime analysis.
3. Simulating invalid API requests to uncover improper handling.

**Flashcard:**
**Q**: What does DAST test?  
**A**: An application’s runtime behavior to find security flaws.

**Practice Question:**
**Scenario**: A DAST scan flags a weak session token. What action should you take?  
**Answer**: Improve token generation and expiration policies.

---

### **7. Fuzzing**
**Definition**: Testing applications by providing unexpected or invalid inputs to find vulnerabilities.

**Key Points:**
- Uncovers crashes, memory leaks, and unhandled exceptions.
- Useful for testing APIs, file uploads, and input fields.
- Automated fuzzing covers a wide range of scenarios efficiently.

**Examples:**
1. Sending random characters to test API stability.
2. Uploading corrupted files to assess file handling robustness.
3. Injecting malformed JSON into an API to find unhandled errors.

**Flashcard:**
**Q**: What is the purpose of fuzzing?  
**A**: To discover vulnerabilities by testing unexpected inputs.

**Practice Question:**
**Scenario**: Fuzz testing causes an application to crash. What does this imply?  
**Answer**: The crash indicates a potential vulnerability or unhandled exception.

---

### **8. Security as Code (SaC)**
**Definition**: Embedding security checks and tests into DevOps workflows to ensure secure development processes.

**Key Points:**
- Scans IaC for vulnerabilities before deployment.
- Maps out secure code and infrastructure changes.
- Reduces delays by integrating security into workflows.

**Examples:**
1. Adding automated scans to CI/CD pipelines to catch security issues early.
2. Ensuring proper authentication rules are included in IaC templates.
3. Verifying secure encryption settings in cloud configurations.

**Flashcard:**
**Q**: What is the purpose of SaC?  
**A**: To integrate security directly into DevOps tools and workflows.

**Practice Question:**
**Scenario**: Security checks delay deployment. How can SaC help?  
**Answer**: By automating checks and embedding them in workflows, SaC reduces delays.

---

### **9. Regression Testing**
**Definition**: Re-running tests to ensure existing functionality remains unaffected by code changes.

**Key Points:**
- Identifies unintended side effects of updates.
- Automates test execution for quick feedback.
- Ensures stability of new and old features.

**Examples:**
1. Running all login-related tests after updating password encryption.
2. Testing shopping cart functionality after adding a new payment method.
3. Verifying API endpoints after backend refactoring.

**Flashcard:**
**Q**: Why is regression testing important?  
**A**: It ensures new changes don’t break existing functionality.

**Practice Question:**
**Scenario**: A feature works during initial testing but breaks after updates. What’s the issue?  
**Answer**: Regression issues; re-running tests can identify where it broke.

---

### **10. Stress Testing**
**Definition**: Determining how much load or traffic a system can handle before breaking.

**Key Points:**
- Measures system limits under heavy loads.
- Identifies bottlenecks and capacity issues.
- Ensures reliability under expected and peak usage.

**Examples:**
1. Simulating 10,000 concurrent users on a website.
2. Testing database performance with large data imports.
3. Overloading an API to observe response times and errors.

**Flashcard:**
**Q**: What is the goal of stress testing?  
**A**: To ensure a system can handle heavy usage without failing.

**Practice Question:**
**Scenario**: A site crashes during a sale due to high traffic. What could prevent this?  
**Answer**: Stress testing beforehand to optimize performance.

---

### **11. Manual Testing**
**Definition**: Testing applications manually to find bugs and usability issues without automation.

**Key Points:**
- Useful for finding design and logic flaws.
- Can test from an end-user perspective.
- Often uses tools like web proxies to inspect API calls.

**Examples:**
1. Checking how a login page handles incorrect credentials.
2. Testing different user roles for proper permissions.
3. Manipulating HTTP requests with a web proxy to find vulnerabilities.

**Flashcard:**
**Q**: What is a key benefit of manual testing?  
**A**: It uncovers design and logic flaws that automated tests might miss.

**Practice Question:**
**Scenario**: A tester manually alters URL parameters to access restricted content. What does this test for?  
**Answer**: Unauthorized access vulnerabilities.

---

### **12. Integration Testing**
**Definition**: Testing how different components of a system work together.

**Key Points:**
- Detects issues in component interactions.
- Ensures seamless integration of new features.
- Common in CI/CD pipelines for automated testing.

**Examples:**
1. Verifying a new payment gateway integrates with the existing checkout system.
2. Testing API responses after connecting with third-party services.
3. Checking a backend change doesn’t disrupt the frontend.

**Flashcard:**
**Q**: What does integration testing focus on?  
**A**: Ensuring smooth interactions between system components.

**Practice Question:**
**Scenario**: A new module causes errors in the main system. What test could prevent this?  
**Answer**: Integration testing to identify compatibility issues early.

---

### **13. Interactive Application Security Testing (IAST)**
**Definition**: Combines static and dynamic analysis to identify vulnerabilities in running applications.

**Key Points:**
- Monitors applications during normal usage.
- Requires manual and automated tests for full coverage.
- Provides real-time feedback on vulnerabilities.

**Examples:**
1. Detecting insecure session handling during active user tests.
2. Finding unencrypted sensitive data in a running app.
3. Monitoring API behavior for unusual patterns during usage.

**Flashcard:**
**Q**: How does IAST differ from DAST?  
**A**: IAST combines static and dynamic testing for better vulnerability detection.

**Practice Question:**
**Scenario**: IAST detects a security issue while users browse an app. What should you do?  
**Answer**: Investigate and fix the issue promptly to maintain security.

---

### **14. Testing Your APIs and Web Services**
**Definition**: Examining APIs for functionality, security, and reliability.

**Key Points:**
- Uses web proxies for inspection.
- Requires crafting requests to test all endpoints.
- Tests for injection attacks, bad input handling, and rate limits.

**Examples:**
1. Sending invalid JSON data to an API and observing responses.
2. Testing rate limits by sending multiple rapid requests.
3. Validating responses for different HTTP methods.

**Flashcard:**
**Q**: What tools are commonly used for API testing?  
**A**: Web proxies and API testing tools like Postman.

**Practice Question:**
**Scenario**: An API accepts malformed input without validation. What’s the risk?  
**Answer**: It could lead to security vulnerabilities like injection attacks.

---
