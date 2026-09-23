SELECT
    p.PRODNB AS [Producer Code],
    p.PRODNAME AS [Producer Name],
    p.PRODLINE1 AS [Address Line 1],
    p.PRODLINE2 AS [Address Line 2],
    c.AgentID,
    c.CommissionRate
FROM TBLProducer p
LEFT JOIN tblCommissionRate c
    ON p.PRODNB = c.AgentID
WHERE p.PRODNAME LIKE '%Assured%';
Policy copy not printed for SS 9085412-02 due to multiple LAD229 endorsements

Description:
What: Policy copy was not getting printed for SS 9085412-02.
When: 2026-09-16
Who: Single User
How: The policy contained multiple LAD229 endorsements, which were causing the policy printing issue.
Why: Duplicate LAD229 endorsements were present in the policy.

Closure Notes:
The issue was analyzed and identified to be caused by multiple LAD229 endorsements. The duplicate endorsements were removed using DML, retaining only one LAD229 endorsement. The midterm endorsement will be added back after the required validation.
UW-Aero eLAD: User unable to complete MFA verification and access eLAD.

Description:

WHAT: User reported being unable to complete the 2-step verification process while accessing UW-Aero eLAD.

WHEN: [Update the issue start time]

WHO: eLAD User

HOW - Steps of Approach:
1. Reviewed the reported login and MFA verification issue.
2. Coordinated with the Okta team to investigate the MFA issue.
3. MFA was reset for the affected user.
4. User retried the login process after the MFA reset.
5. Confirmed that the user was able to successfully log in to eLAD.

WHY: The user was unable to complete the MFA verification required to access eLAD.

IDENTIFIERS:
Application: UW-Aero eLAD
Issue: MFA / 2-Step Verification

Closure Notes:

Reported Issue:

User was unable to complete the 2-step verification process while accessing UW-Aero eLAD.

Issue Description:

The user was unable to complete MFA verification and could not access eLAD.

Analysis:

Reviewed the reported access issue and coordinated with the Okta team. The MFA configuration for the affected user was reset to resolve the verification issue.

Solution/Workaround:

The MFA was reset with the assistance of the Okta team. The user was then able to successfully complete the verification process and log in to eLAD.

Module/Functionality:

UW-Aero eLAD / Okta MFA

No defect or recurring issue found; problem ticket not applicable. — I’ll keep it in the **same concise ServiceNow format** we were using, with the **WHEN section left for you to fill in**.

### Short Description

**Incorrect AOPA number for policy LA316069-02 in ILS**

### Description

**WHAT:**
Business user reported an error while trying to view A/C information under the A/C tab for policy **LA316069-02**.

**WHEN:**
[To be updated]

**WHO:**
Business User

**WHY:**
The issue occurred due to an **incorrect AOPA number maintained in ILS**.

**HOW:**
The policy details were analyzed and the AOPA number was verified in the ILS database. The incorrect AOPA number was identified and corrected using a DML script.

### Closure Notes

Hi,

Thank you for contacting AerospaceWindows support.

**Reported Issue:** Business user reported an error while trying to view A/C information under the A/C tab for policy **LA316069-02**.

**Issue Description:** The AOPA number maintained in ILS was incorrect.

**Analysis:** Upon analyzing the policy details, the AOPA number was found to be incorrect in the ILS database.

**Solution/Workaround:** The AOPA number was corrected in ILS using a DML script. The updated information was verified successfully and the issue has been resolved.
