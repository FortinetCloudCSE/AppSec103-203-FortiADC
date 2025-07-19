---
title: "Adaptive Learning"
linkTitle: "Adaptive Learning"
chapter: false
weight: 50
---

### What is Adaptive Learning?

The new FortiADC WAF Adaptive Learning feature enhances security by dynamically generating tailored recommendations to refine protection policies, allowing for quick and effective WAF configuration to counter evolving threats. By continuously performing deep packet inspection and traffic analysis, the Adaptive Learning engine builds comprehensive datasets from traffic patterns, enabling it to autonomously detect and mitigate threats with precision. These insights allow the engine to provide actionable recommendations for optimizing WAF policies, ensuring that security measures are adapted to the specific traffic characteristics of each web application. This results in an improved security posture and better operational performance through real-time adjustments and fine-tuning of security settings.

The WAF Adaptive Learning feature requires either a WAF Signature license or an Application Security bundle license. For users without a valid license, FortiADC offers a 30-day trial that activates automatically when upgrading to FortiADC version 7.6.0, allowing exploration of the WAF Adaptive Learning capabilities.

Here are some practical applications of the WAF Adaptive Learning functionality:

- **Creating new WAF policies**: During the setup of a new virtual server, users can utilize the Adaptive Learning recommendation feature to automatically generate and apply basic WAF policies for a new WAF profile.

- **Enhancing existing WAF policies**: Users can adjust policy settings based on Adaptive Learning recommendations, which identify changes in traffic patterns to enhance the security of current WAF policies.

- **Identifying and reducing false positives**: The Adaptive Learning engine helps detect false positive triggers in WAF policies, allowing users to adjust settings and exclude unnecessary violations.

The Adaptive Learning engine has two key components:

- **Adaptive Learning policy** - It defines the dataset
- **Adaptive Learning statistics** - It contains the analytical results and actionable recommendations.


