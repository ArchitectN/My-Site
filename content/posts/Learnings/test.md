---
title: "Kafka use case"
summary: Devops Learning
date: 2026-05-22
weight: 1
aliases: ["/building-serverless-webapp"]
tags: ["tech", "Docs", "Learnings", "devops"]
author: ["Nick Hong"]

---

### Intro

Your example mapped out
SNS scenario:
Order placed ──► SNS ──► Email service (DOWN for 20 min)
                              │
                              └── message dropped, customer 
                                  never gets confirmation email
Kafka scenario:
Order placed ──► Kafka topic "orders" ──► Email service (DOWN for 20 min)
                      │
                      └── messages sitting at offset 4,820
                      
Email service comes back up...
                      │
                      └── "okay I was at offset 4,820, let me 