# Social Media Automation – Production Ready (n8n)

## Overview

This repository contains a **production-ready n8n workflow** designed for **safe, scalable, and automated social media account warm-up and posting**. The workflow simulates realistic human behaviour while applying strict safety and risk-management rules to support long-term account stability and reduce the likelihood of bans.

It is built for advanced automation use cases where reliability, control, and observability are more important than basic posting automation.

---

## Key Features

- Automated account warm-up with human-like browsing behaviour  
- Webhook-based content posting for Instagram and TikTok  
- Residential proxy rotation with geo-targeting  
- Mobile device fingerprint and browser profile isolation  
- Risk-aware safety filters with dynamic ban-risk scoring  
- Progressive daily limits based on account age  
- Automatic cooldowns between actions and sessions  
- Centralised account state management using Google Sheets  
- Daily health checks, counter resets, and status transitions  

---

## Workflow Architecture

The automation is divided into three core pipelines:

### 1. Warm-Up Automation
Accounts marked as *Warming* are activated on a fixed schedule. Each session:
- Assigns a unique proxy and mobile device fingerprint  
- Starts an isolated browser profile  
- Executes a weighted random sequence of actions such as scrolling, pausing, watching content, and light engagement  
- Analyses results for errors, rate limits, or ban signals  
- Updates warm-up counters and ban-risk scores  

### 2. Automated Posting
Posting is triggered via webhook and follows a strict validation and safety process:
- Content and platform are validated before execution  
- Only *Ready* and low-risk accounts are selected  
- Posting is batched and rate-limited  
- Each post runs in its own isolated browser session  
- Results are analysed and logged to adjust risk scores  

### 3. Daily Health & Risk Management
A scheduled maintenance routine:
- Resets daily warm and post counters  
- Gradually decays ban-risk scores for healthy accounts  
- Promotes warmed accounts to *Ready* status  
- Flags inactive or risky accounts automatically  

---

## Safety & Risk Controls

The workflow includes multiple protection layers:
- Minimum time gaps between warm-ups and posts  
- Progressive daily limits based on account maturity  
- Dynamic ban-risk scoring with automatic escalation  
- Behaviour randomisation to reduce automation patterns  
- Residential proxy usage with location alignment  
- Cooldown periods after each session  
- Automatic detection of platform warning signals  

These controls are designed to prioritise account longevity over speed.

---

## Integrations & Technologies

- **n8n** – workflow orchestration  
- **Google Sheets** – account state, metrics, and control panel  
- **GoLogin** – browser profile isolation and fingerprinting  
- **IPRoyal** – residential proxy management  
- **Puppeteer** – browser automation  
- **Node.js** – dynamic script execution  
- **Webhooks** – controlled posting interface  

---

## Intended Use

This project is intended for **advanced automation scenarios**, such as:
- Social media account warm-up systems  
- Managed multi-account posting workflows  
- Automation research and experimentation  
- Portfolio demonstration of production-grade n8n automation  

It is not designed for simple or unsupervised mass posting.

---

## Disclaimer

This project is provided for **educational and research purposes only**.  
Users are responsible for ensuring compliance with all applicable platform terms of service and local regulations.

---

## License

MIT License
