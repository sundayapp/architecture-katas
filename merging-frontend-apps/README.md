# Merging Frontend Apps for Restaurant Software

You work for a company that builds software for restaurants, to help the customers order and pay for their meals.

## Current State
Two separate front end apps:
- Pay At Table: a React app targeted to mobile users, that is open by scanning a QR on your restaurant table and let you pay the given bill
- Order & Pay: a Next app that let you order something from a restaurant, pay for your order and select a pick-up method (at counter, at table... etc)

Shared components with specific features:
- review form,
- credit card payment
- design system

These apps were built by different teams, each with separate backend APIs

## Goals and deliverables
The goal is to merge into a single app that lets the merchant associate different experiences with different entry points (pay at table on restaurants table, order and pick up on its website)

Describe and illustrate the strategy you would take, the organization you would put in place, the architecture you would aim, and feel free to detail any part of the problem and solution you think are relevant.

You are encouraged to deliver comprehensive diagrams and any other relevant artifacts that illustrate your approach.

## Functional Requirements
- Browse menus (images + videos)
- Order: basket management and payment or pre-authorization
- Bill splitting (multi-guest)
- Loyalty program and history
- Account management

## Non-Functional Requirements
- Responsive under poor network conditions
- Scales to 100k users/minute
