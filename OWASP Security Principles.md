-  **Minimize the attack surface area**
  Reduce the number of entry points or ways an attacker can gain unauthorized access.
  **Example:**
	  1. Suppose your web application has 20 different APIs, but only 5 are needed by users. Exposing all 20 increases your risk. By **disabling or removing unused APIs**, you reduce the possible paths an attacker can exploit.
	2. **On a server**:  you disable unused services like FTP or Telnet to limit exposure.

-  **Principle of least privilege**
  Each user or process should only have the minimum access or permissions necessary to perform its function.
  **Example:**
	  1. A user who only needs to view reports should **not be granted admin or write access** to the database.
	  2. Your web app's file upload component shouldn't be allowed to execute files—just store them.

-  Defense in Depth
  Use multiple layers of security controls so that if one fails, others still protect the system.
  **Example**:
	  1. You enforce **multi-factor authentication (MFA)**.
	  2. You encrypt passwords using a strong hashing algorithm (e.g., bcrypt).
	  3. You monitor login attempts for anomalies.

-  Separation of duties
  Split responsibilities so no one individual has complete control over a critical process, reducing the risk of misuse or error.
  **Example**:
- In a DevOps team:
	  1. The developer **writes the code**.
	  2. The security team **reviews the code**.
	  3. The operations team **deploys the code**.

- Keep security simple
  Complex security mechanisms are harder to understand, maintain, and can lead to mistakes or misconfiguration.
  **Example**:
		1. Instead of building your own encryption logic (which may have bugs), **use a proven library** like OpenSSL or libsodium.

- Fix security issues correctly
  When fixing a security vulnerability, ensure the root cause is addressed—not just the symptoms.
  **Example:**
		1. Don’t just block a malicious IP—**understand how it got in**, and fix the underlying flaw in authentication or input validation.