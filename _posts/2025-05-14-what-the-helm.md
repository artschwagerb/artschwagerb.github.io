---
layout: post
title: "What the Helm?"
description: "Given a Helm Repository URL, find charts and versions are available."
date: "2025-05-14"
---

Helm is good.  But what if I told you, I dont want to type in Helm CLI commands to determine helm chart and version information so I can paste it into ArgoCD.

## Introducing What The Helm?

> A tool created out of my own frustration and lack of technical understanding.  Enter your Helm Repository URL, and behold the Charts and Versions.

[https://what-the-helm.spite.cloud/](https://what-the-helm.spite.cloud/)

## Whats it do?

It simply appends /index.yaml to the URL you provide.  Then formats it as a nice little list of Charts with Versions for each.

If im being honest.  Github Copilot wrote it while I complained.