# Payment solution for restaurants

You work for a company that builds software for restaurants, to help the customers pay for their meals.

## Goals and deliverables

The goal is to build a payment solution for restaurants that allows customers to pay for their meal once they have
finished eating. Using their mobile, they can scan a QR code on the restaurant table, and be redirected to a web
application.

Restaurants are equipped with a Point of Sale (POS) system, which waiters use to enter customer orders. The POS serves as the source of truth for key information such as orders and table management, and it can be accessed programmatically through a web API.

Describe and illustrate the architecture you would aim, the organization you would put in place, and feel free to detail
any part of the problem and solution you think are relevant.

You are encouraged to deliver comprehensive diagrams and any other relevant artifacts that illustrate your approach.

## Requirements

- Retrieve the bill for a table
- Bill splitting (multi-guest)
- Payment
- Handle several POS brands to address different restaurants
- Browse menus (images + videos)
- Loyalty program and history
- Account management
- Scales to 100k users/minute
- Deployed on Europe and US regions
- Plan to no only be able to pay for your meal after eating but also order meals directly from app and combine different types of user experiences (order and pay at table, order and pick up at counter, open a tab, etc.)
