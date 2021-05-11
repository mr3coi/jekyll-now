---
published: true
layout: post
title: (NVIDIA) "NVML: Driver/library version mismatch"
---

Symptom:
- Running `nvidia-smi` prints `NVML: Driver/library version mismatch` instead

Diagnosis: 
- NVIDIA driver kernel module (mod) with wrong version has been loaded
- The module needs to be unloaded, and an appropriate module needs to be loaded instead

Solution:
1.  Reboot computer

2.  (To avoid rebooting computer) follow instructions in the below link


References:
- <https://stackoverflow.com/a/45319156>
