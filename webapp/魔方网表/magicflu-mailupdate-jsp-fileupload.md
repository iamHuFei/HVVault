**CVE Request**

**Title:**
magicflu-mailupdate-jsp-fileupload

**Description:**
An attacker can exploit this vulnerability by sending a crafted HTTP request to the '/magicflu/html/mail/mailupdate.jsp' endpoint, manipulating the 'messageid' parameter to traverse directories and upload a malicious file (e.g., a web shell) with a randomized filename. Subsequently, the attacker can validate the successful upload by sending a request to the '/magicflu/{{name}}.txt' endpoint, where {{name}} is the randomly generated filename.

**Vendor Contact:**
https://www.magicflu.com/

**Affected Versions:**
Unknown

**Mitigations:**
Wait for the vendor to fix it

**References:**
Code audits

**Proof of Concept (PoC):**
[magicflu-mailupdate-jsp-fileupload.yaml](magicflu-mailupdate-jsp-fileupload.yaml)

**Verification process:**

1. Home:
![img.png](img.png)
2. Upload File:
![img_1.png](img_1.png)
3. Validation:
![img_2.png](img_2.png)