[title]: # (Gatekeeper)
[tags]: # (macOS)
[priority]: # (28)

# macOS Gatekeeper Best Practices

The macOS Gatekeeper technology can prevent newly downloaded applications and scripts from running, unless downloaded from the App Store or identified as coming from a trusted developer

Privilege Manager cannot get around these OS specific security protections; however deploying a script that developers use or need to run frequently is possible via the MDM process (and JAMF rollout).

Refer to details as documented by Apple regarding bypassing Gatekeeper via MDM: [Gatekeeper and runtime protection in macOS](https://support.apple.com/guide/security/gatekeeper-and-runtime-protection-sec5599b66df/web)