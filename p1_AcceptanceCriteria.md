# Part 1. Acceptance Criteria

## Functional 
- The login process has been modified to require acceptance of a Privacy Policy in addition to username and password.
- Users are unable to login without accepting the Privacy Policy, it cannot be bypassed at all.
- The Privacy Policy documentation can be accessed, downloaded and reviewed by the user before login.
- Users are able to login successfully after accepting the Privacy Policy and entering a valid username and password.
- The Privacy Policy check does not cause any errors or issues within the login screen or any other app/acount features.

## UX/UI

- The Privacy Policy check is implemented as a checkbox and always must be initially displayed unchecked.
- Next to the checkbox there is the following text: "I have read and agreed to exampleSiteOrAppName's Privacy Policy.", and the "Privacy Policy" substring links to the Privacy Policy documentation. 
- When the user clicks or taps on the link the Privacy Policy document is displayed and it can be downloaded to the user's device. 
- While the Privacy Policy checkbox is unchecked, the login button is disabled.
- When the Privacy Policy checkbox is checked, the login button gets enabled.
- If the login button is disabled and the user hovers (web) or taps (mobile) on the button, a tooltip message is displayed: "Please accept our Privacy Policy before logging in.".
- If a savvy user bypasses the frontend protection and submits the login form without the P.P. check, an error message should be displayed under the login button: "Please accept our Privacy Policy before logging in."
- The Privacy Policy document is translated in all the different languages of the markets where the platform operates.
- The Privacy Policy elements are clearly visible on the login screen.
- The Privacy Policy elements meet the accessibility standards
- The Privacy Policy elements do not negatively impact the performance of the login process.
- The Privacy Policy elements are functional and compatible at least with:
    - Web browsers: Chrome, Firefox, MS Edge and Safari in their desktop and mobile versions. Also Samsung Internet (only mobile). Version coverage must be at 85% or better.
    - Mobile platforms: Android and iOS, both in phone and tablet.

## Backend
- The Privacy Policy feature is also implemented on the backend and is properly enforced by the system even if a savvy user bypasses the frontend.
- The acceptance of the Privacy Policy is logged in the system together with the existing user account data and can be audited when necessary.
- The Privacy Policy acceptance can be revoked.
- The backend is able to handle the increased load related to the Privacy Policy feature without causing errors or issues with other functionality on the site.

## Compliance
- The Privacy Policy functionality is compliant with any legal regulations.
- All third-party services and libraries you use are also compliant with the Privacy Policy.

## Additional considerations and improvements

### Privacy Policy impacts users in varying degrees
It could be that depending on some user aspects the Privacy Policy impacts users to varying extents. For example:
 - Users from EU are fully impacted.
 - Users from Japan have a specific version of the Privacy Policy. They can decline or accept it. If they decline it, their app/account will have some functionalities removed or limited. 
 - Users from the rest of the world (incl. USA) are not impacted at all. 
 
In a case like this we would need additional Acceptance Criteria. Some of them are listed below (this just a sample and is not intended to be an exhaustive list):
- The application must be able to detect the user's location.
- For EU users, the Privacy Policy must be enforced strictly as described in the Acceptance Criteria listed above.
- Users from Japan can accept (tick the checkbox) or decline (leave checkbox unchecked).
- Users from Japan who accept the Privacy Policy should retain all app/account functionalities.
- Users from Japan who decline the Privacy Policy should have the following features removed or modified: ...
- For users from the rest of the world the app/account must remain unchanged and no elements related to the Privacy Policy should be displayed. 
- The system must provide a mechanism for users to update their Privacy Policy acceptance status if their location changes.
- The system must be able to handle users who are using VPN, proxy, or browsers with privacy protection enabled and correctly identify their location.

### Privacy Policy elements not displayed if already accepted in the same browser/device
As an enhancement, if a user already accepted the Privacy Policy in a certain device/browser, the login page would not display the Privacy Policy elements again. This would improve the user experience by reducing the number of times the user has to accept it. The tradeoff is an increased complexity of the feature, but in this case it is probably worth it.

We could add this Acceptance Criteria to the UX/UI section:
- If a user already accepted the Privacy Policy in a certain device/browser, the login page must not display the Privacy Policy elements again.

### Privacy Policy acceptance upon account creation or login
As I made progress writing down this document I realized that it may be a better approach to ask the users to accept the Privacy Policy upon account creation instead of login.

This is because the user is actively choosing to create an account and engage with the service, and by requiring them to accept the Privacy Policy before doing so, the user is making an informed decision. This ensures that the user is aware of the company's Privacy Policy before they provide any personal information and it creates a clear record of the user's acceptance of the policy.

Requiring the user to accept the Privacy Policy at every login negatively impacts the user experience and leads to frustration, although this might be mitigated using a browser cookie as mentioned in the previous topic. Anyway, even in this case the Privacy Policy acceptance will be required for the same user if they log in from different devices/browsers.

On the other hand, accepting the Privacy Policy every time at login could have some advantages too. For example, it does re-affirm the user's understanding of the Privacy Policy and provides an extra path for users to accept an updated version of the Privacy Policy.

As a final consideration, depending on the jurisdiction, it may be legally required to accept the Privacy Policy at the time of account creation, or it may be required every time the user logs in.

### Login button before accepting Privacy Policy: enabled or disabled

It is a matter of discussion if the login button should be enabled or disabled before the user checks the Privacy Policy checkbox. The Acceptance Criteria listed above were set considering the login button should be disabled. But in case we choose to leave it enabled, if the user tries to log in without checking the checkbox it should display some sort of error message prompting the user to accept the Privacy Policy before logging in. Both options have their own pros and cons.

Leaving the login button disabled:
- Makes it clear to the user that they must accept the Privacy Policy in order to proceed.
- Can reduce confusion and the number of clicks since the user sees immediately that login is not possible.
- It might look less user friendly and make the user feel somewhat restricted.

On the other hand, choosing to enable the login button:
- Allows the user to attempt the login, giving them more sense of control over the process.
- Can serve as a reminder for the user to read the Privacy Policy.
- Increases complexity.
- Requires to display an error message, which can put off some users.

In general, it's a matter of trade-offs, and the best approach depends on the specific context and requirements of the project. It is important to consider the user experience and how the approach will affect the user's perception of the platform, as well as any regulatory compliance requirements.

### Force the user to open the Privacy Policy document before enabling the checkbox

It is also debatable if the user must be required to open the Privacy Policy and even scroll it down to the bottom before it can tick the acceptance checkbox. 

In this case I assumed it will not not be required, but forcing the user to open it could help preventing misunderstandings about the company's Privacy Policy and reduce the risk of disputes or legal action. However, this leads to a negative user experience as increases friction, specially if the Privacy Policy is several pages long. It is also worth considering the legal implications as one or the other approach might not be compliant with some jurisdictions.
