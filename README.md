# AI Speed-to-Lead System

An AI system that replies to new leads on WhatsApp within seconds, qualifies them, and books site visits automatically, so no enquiry goes cold while the team is busy.

> **Note on results:** the figures below come from a simulation on 224 modelled leads. They are projections, not results from a live client.

## The problem

Small businesses lose most of their leads in the first hours: the enquiry arrives, nobody replies for a while, and the lead books with a competitor. This system removes that delay.

## What it does

- Replies to every new lead on WhatsApp within seconds
- Asks for service needed, area, start date and budget in a natural conversation
- Uses Claude to extract the answers into structured data and score each lead **hot / warm / cold**
- Books site visits autonomously
- Sends follow-ups at 1 hour, 1 day, 3 days and 7 days if the lead goes quiet
- Alerts the owner within 15 minutes when a hot lead comes in

## Architecture

Four linked Make.com scenarios:

1. **Intake:** new lead from the form or WhatsApp is logged to Google Sheets
2. **Qualification and booking:** Claude API runs the conversation, extracts fields, scores the lead and books a visit
3. **Follow-ups:** scheduled nudges at 1h / 1d / 3d / 7d
4. **Hot-lead alert:** notifies the owner within 15 minutes

A Python/Flask version of the same logic was also built and covered by **48 automated tests**. This repository documents the design; the implementation is not published here.

## Stack

Make.com, Claude API, WhatsApp Cloud API, Google Sheets, Python, Flask

## Simulated impact (224 modelled leads)

| Metric | Before | After |
|---|---|---|
| Lead reply rate | 29% | 76% |
| Booked site visits per month | ~28 | ~57 |

## Author

Kabir Anand: [LinkedIn](https://www.linkedin.com/in/kabir-anand-391546271)
