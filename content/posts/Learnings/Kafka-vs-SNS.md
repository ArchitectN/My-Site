---
title: "Kafka use case"
summary: Devops Learning
date: 2026-02-08
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
                           read 4,821 through 5,103 and send 
                           those emails"
                      
customers get their emails, nothing lost
The follow-on implication
This is also why Kafka is common in financial and e-commerce systems specifically. Dropping a payment event or order confirmation isn't just bad UX — it's a business and compliance problem. Kafka's durability gives you a guarantee that every event will be processed eventually, even if a consumer has issues.
The tradeoff is that your email service now needs to be idempotent — meaning if it processes the same message twice by accident, it doesn't send duplicate emails. That's the complexity Kafka introduces on the consumer side. But for most teams that's a worthwhile engineering problem compared to silently dropping data.