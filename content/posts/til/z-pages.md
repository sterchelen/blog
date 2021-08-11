---
title: "TIL: google's z-pages"
date: 2021-08-02T21:35:55+02:00
categories: ["til"]
tags: ["history"]
summary: "Why health check endpoints in k8s are ending with a 'z'"
---

# Why z pages?
For a long time, I've asked myself why the kubernetes API health endpoints are ending with a "z".
Like `healhtz` or `readyz` and even `livez`.[^1]  
I've finally found the answer, here [^2].  

## TL;DR
The reason is simple, google introduced these pages to reduce
path collision within their applications.  
This way, you can have `statusz` page giving the status of the whole api and a `status` page for anything else.
{{< mermaid >}}
graph LR;
    A[REQUESTS] --> B{API}
    B --> C[status]
		B --> D[statusz]
{{< /mermaid >}}

## Kelsey Hightower's explanation
<iframe src="https://player.vimeo.com/video/173610242?h=cfbee80585&portrait=0&texttrack=en#t=26m50s" width="640" height="360" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe>





[^1]: https://kubernetes.io/docs/reference/using-api/health-checks/
[^2]: https://stackoverflow.com/questions/43380939/where-does-the-convention-of-using-healthz-for-application-health-checks-come-f/43381061#43381061
