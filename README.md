# iOS 15.5 WebDriverAgent build test

Target: iPhone 6s Plus on iOS 15.5; Windows 10 with Python 3.12 and tidevice.

## Purpose

This repository provides a **diagnostic build**, not a guaranteed installable or working iPhone automation app. WDA is an XCTest runner and usually needs appropriate Apple signing and a compatible test launch mechanism.

## Run

1. Open **Actions** in this repository.
2. Select **Build WDA for iOS 15.5 (experimental)**, then **Run workflow**.
3. Review job logs. Download `WDA-iOS15-unsigned-test-build` only after a green build.
4. Inspect minimum iOS version and signing requirements before attempting to install anything on the phone.

The output includes a deliberately **unsigned** candidate IPA and build-for-testing products. An IPA alone does not prove that WDA can launch as an XCTest service when installed through Windows sideloading.

## Safety and limitations

- Do not enter Apple ID credentials into build workflows or GitHub secrets for this experiment.
- Keep the iPhone connected to Windows with USB.
- No automated bypass of video-platform anti-bot or access controls is implemented.
- Source comes from `appium/WebDriverAgent` (master); the exact commit can be read from the GitHub Actions checkout log. Pin it after confirming compatibility.
- A Mac/Xcode signing or compatible pre-signed XCTest runner might be required even if compilation succeeds.
