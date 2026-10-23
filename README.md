# Awesome-Mobile-Devops-Deployment

# Awesome-Mobile-Devops-Deployment

## Top Mobile DevOps & Deployment Tools Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Self-Hosted Beta Distribution, Managed Code Signing & CI/CD Automation*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Mobile DevOps & Deployment**. These tools handle the critical path from compiled binary to tester's device — building on clean machines, managing iOS certificates and provisioning profiles, distributing beta builds, and automating store submissions — so releases aren't a manual ritual performed by the one developer who understands signing.

**Examples** include Fastlane, Bitrise, Codemagic, Zealot, Firebase App Distribution, and TestFlight (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, transparent code signing, and CI-agnostic automation — especially relevant now that **Microsoft App Center was retired on March 31, 2025** and **Ionic Appflow enters end-of-life on December 31, 2027**.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **Firebase App Distribution** — **The no-cost beta distribution service within Firebase.** Distribute pre-release iOS and Android builds to tester groups via the Firebase console, CLI, or public API [citation:12]. Testers receive email notifications with a streamlined sign-up flow, and in-app updates keep them on the latest build [citation:5]. **Free to use** — Firebase explicitly states App Distribution is a no-cost tool [citation:5][citation:12]. **Best for teams already in the Firebase ecosystem** wanting zero-friction beta distribution without a separate vendor.

- **Bitrise** — **The mobile-first CI/CD platform with 400+ pre-built steps.** Hobby tier is free (300 credits/month), Starter at **$89/month**, Pro at **$200/month** [citation:4]. M1/M2 Mac machines without managing GitHub Actions macOS runners, and a visual workflow editor for complex multi-step pipelines [citation:4]. **Best for teams wanting dedicated mobile CI** with mobile-specific build insights and test reports.

- **Codemagic** — **Flutter and cross-platform CI/CD specialist.** Free tier: **500 minutes/month on Apple Silicon**, Pro at **$49/month** [citation:4]. Supports Flutter, iOS, Android, and React Native, with a hosted CodePush OTA service that claims roughly 1/4 the price of Expo for 100k MAU [citation:7]. **Best for Flutter teams** wanting native Apple Silicon builds without managing infrastructure.

- **GitHub Actions** — **The general-purpose CI/CD runner with macOS support.** Free for public repositories; **2,000 minutes/month for private repos** [citation:4]. Requires DIY configuration for mobile-specific tasks, but integrates natively with GitHub's repository and security features. **Best for teams already on GitHub** wanting CI without a separate vendor.

- **Visual Studio App Center** — **Retired on March 31, 2025.** Build and distribute functionality is gone; CodePush is community-maintained only. **Do not start new projects on App Center.**

- **TestFlight (Apple)** — **Apple's native beta testing platform, bundled with the Apple Developer Program ($99/year).** Beta builds available for 90 days per upload, with up to 30 devices per tester. **Best for iOS-exclusive teams** already paying for Apple Developer membership.

## Open-Source GitHub Projects

- **[Fastlane](https://github.com/fastlane/fastlane)** — **The de facto standard for mobile build automation.** MIT licensed. **Handles the tedious parts of iOS and Android releases**: code signing via **match** (stores certificates and profiles in an encrypted Git repository), screenshots via **snapshot**, beta distribution via **pilot**, and App Store metadata via **deliver**. **Runs locally and on any CI** (GitHub Actions, CircleCI, Bitrise) — no third-party CI dependency [citation:4]. **The foundation most mobile pipelines are built on**, even when the CI itself is commercial. **Best for teams wanting complete ownership** of their build and signing process.

- **[Zealot](https://github.com/ai-aide/zealot)** — **The self-hosted beta distribution platform for iOS, Android, macOS, Linux, and Windows.** Open-source alternative to Pgyer/TestFlight [citation:3]. **Features**: multi-platform app hosting (APK/AAB, IPA, macOS, Windows, Linux), **automatic iOS test device sync and one-click registration** to the Apple Developer portal, **REST API and iOS/Android SDKs**, **fastlane plugin** for automated uploads, **app metadata parsing** (extract info from iOS/Android binaries and provisioning profiles), **custom Income WebHooks** for notifications, **multi-channel classification**, and **third-party login** (Feishu, GitLab, GitHub, Google, LDAP, OIDC) [citation:3]. **Best for teams wanting a full-featured self-hosted TestFlight replacement** with device management and CI integration.

- **[Oore CI](https://github.com/oore-ci/oore.build)** — **The self-hosted, Flutter-first mobile CI and internal app distribution platform.** Alpha status — APIs and CLI flags may change before stable [citation:2]. **Runs on macOS (arm64 or x86_64)** with a daemon (`oored`), operator CLI (`oore`), web UI, and OIDC authentication [citation:2]. **Five device roles** for distributed setups: Complete, Control plane, Runner, Web node, and CLI only — allowing builds to run across multiple Macs [citation:2]. **Best for Flutter teams** wanting self-hosted CI with distribution capabilities, accepting alpha-stage stability.

### Additional Strong Open-Source Options

- **Appium** — The free, code-first mobile automation foundation underneath most test clouds. **You own device procurement, USB hubs, battery health, and flaky host machines** — hardware upkeep is a real headcount cost. Best for teams with platform engineers wanting full control and zero license cost.
- **Zebrunner MCloud** — Self-hosted device farm for automated Appium tests and manual remote access to physical Android/iOS devices.
- **OpenSTF** — The original open-source device farm for Android. Basis for MCloud and similar tools.

**Frameworks for building custom systems**: Combine **Fastlane** for build automation and code signing across any CI, **Zealot** for self-hosted beta distribution with device management and fastlane integration, **Oore CI** for Flutter-first self-hosted CI with distribution, and **Bitrise** or **GitHub Actions** for the CI runner itself — to build a mobile deployment pipeline tailored to your platform (iOS vs Android vs cross-platform), signing complexity, and tolerance for vendor dependency.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- **Microsoft App Center was retired on March 31, 2025** — build and distribute functionality is gone, and CodePush is community-maintained open source only. **Ionic Appflow stops new sales immediately and existing customers lose access on December 31, 2027**. Do not start new projects on either.
- **iOS code signing is the most common reason mobile CI pipelines break** — certificates expire, provisioning profiles need renewal, and credentials must match across local machines and CI. **Fastlane match** stores signing assets in an encrypted Git repo so everyone uses identical credentials. **Bitrise** stores them in its dashboard.
- **Self-hosted distribution shifts responsibility to you** — storage durability, access control, and app binary retention become your operations, not a vendor's.
- Self-hosted open-source solutions require proper Docker deployment, TLS configuration for installation pages, and awareness that iOS ad-hoc distribution requires registered device UDIDs.

---

**Made for mobile engineers and release managers who want deployment pipelines they can debug and control.**
Let's make mobile DevOps more open, signing-transparent, and self-hostable.
