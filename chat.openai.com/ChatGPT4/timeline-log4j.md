Can you write me a complete timeline of #log4j CVE-2021-44228, including when it was exploited, found, fixed, introduced and so on, please include at least one reference URL for each item listed.
I've compiled a timeline for the Log4j vulnerability CVE-2021-44228, including key dates and events. Please note that my knowledge is limited to September 2021 and I may not have the latest updates. Here's a summary of the timeline:

Introduction of the vulnerability:
The Log4j vulnerability was introduced with the release of Log4j 2.0-beta9 in March 2013.
Reference URL: https://logging.apache.org/log4j/2.x/changes-report.html#a2.0-beta9

Discovery of the vulnerability:
The vulnerability was discovered by Chen Zhaojun, a security researcher from Alibaba Cloud on November 24, 2021.
Reference URL: https://www.lunasec.io/docs/blog/log4j-zero-day/

Public disclosure and assignment of CVE:
The vulnerability was publicly disclosed on December 9, 2021, and assigned the identifier CVE-2021-44228.
Reference URL: https://nvd.nist.gov/vuln/detail/CVE-2021-44228

Release of Log4j 2.15.0 (initial fix):
The Apache Log4j team released version 2.15.0 on December 10, 2021, to address the vulnerability.
Reference URL: https://logging.apache.org/log4j/2.x/security.html

Release of Log4j 2.16.0 (additional fix):
Apache Log4j team released version 2.16.0 on December 13, 2021, which provided an additional fix for the vulnerability, disabling JNDI lookups by default.
Reference URL: https://logging.apache.org/log4j/2.x/security.html

Release of Log4j 2.17.0 (additional fix):
Apache Log4j team released version 2.17.0 on December 18, 2021, to address a newly discovered related vulnerability CVE-2021-45046.
Reference URL: https://logging.apache.org/log4j/2.x/security.html

Exploitation:
The vulnerability was actively exploited in the wild starting from December 9, 2021, after the public disclosure.
Reference URL: https://www.lunasec.io/docs/blog/log4j-zero-day/

Please ensure you're using the latest version of Log4j or have applied the appropriate mitigations to protect your systems.
