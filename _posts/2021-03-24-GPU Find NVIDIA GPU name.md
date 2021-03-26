---
published: true
layout: post
title: (GPU) Find name of installed NVIDIA GPU
---

1.  Run `nvidia-smi`, then look under `Name` section

2.  If the name is chopped off in `nvidia-smi`, directly query for the full name:
    `nvidia-smi --query-gpu=name --format=csv,noheader`
    - The `format` option seems to be required


References:
- <https://askubuntu.com/questions/524242/how-to-find-out-which-nvidia-gpu-i-have>
