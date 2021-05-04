[title]: # (Gatekeeper)
[tags]: # (macOS)
[priority]: # (28)

# macOS Gatekeeper Best Practices

The macOS Gatekeeper technology prevents certain scripts from running on a system. Only items downloaded from the app store or items identified as trusted software are allowed to run.

Privilege Manager cannot get around these OS specific security protections; however deploying a script that developers use or need to run frequently is possible via the MDM process (and JAMF rollout).

Refer to details as documented by Apple regarding bypassing Gatekeeper via MDM: [Gatekeeper and runtime protection in macOS](https://support.apple.com/guide/security/gatekeeper-and-runtime-protection-sec5599b66df/web)