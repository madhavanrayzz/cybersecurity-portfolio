# A Practical Approach to Web and API Security Testing

*An overview of methodology—not a claim that every listed test has been performed on every engagement.*

## 1. Understand scope and roles

Before testing, confirm the authorized hosts, applications, API versions, test accounts, permitted techniques, time windows, and prohibited actions. Identify the user roles and the actions each role should be able to perform.

## 2. Map the application

Review the application’s primary workflows, API routes, parameters, authentication mechanisms, and trust boundaries. Proxy traffic through an intercepting tool and build a structured endpoint inventory. Keep notes tied to the agreed scope.

## 3. Test authorization explicitly

For each sensitive action or object, ask:

- Is authentication required?
- Is the user authorized for this action?
- Is access checked server-side on every request?
- Can one user access another user’s object by changing an identifier?
- Are role and tenant boundaries consistently enforced?

Use only approved test accounts and data. Avoid accessing real users’ information.

## 4. Review business logic

Look for security assumptions in workflows such as registration, account recovery, email changes, invitations, payments, and administrative actions. Test meaningful edge cases within the engagement rules. A technically valid request can still violate an intended business rule.

## 5. Assess resilience and configuration

Where authorized, evaluate rate limiting, input validation, session handling, CSRF protections, error handling, security headers, and exposed documentation or debug interfaces. Do not treat the absence of a single header or a scanner alert as proof of a high-impact vulnerability.

## 6. Validate findings

A finding should have reproducible steps, a clear affected component, evidence that avoids unnecessary sensitive data, realistic impact, and a remediation recommendation. Distinguish confirmed vulnerabilities from observations and hardening suggestions.

## 7. Report for remediation

A useful report includes a concise summary, affected endpoint or component, prerequisites, reproduction steps, impact, evidence, severity rationale, and a practical fix. Retest after remediation where agreed.

## Closing principle

The goal is not to generate the largest number of alerts. It is to identify meaningful risk accurately and help the owner reduce it.

*Use this methodology only on systems you own or are explicitly authorized to assess.*
