# PITCH.md

Six lines and a lever. Your words. The last two are scored.

Built: - next available day: It answers "when is the first day I can fly?" by finding the earliest date that still has a free seat on the customer's route.
- Fare rules: pricing, looks up written rules to the customer queries in their own words fare-rules.md files.
- reopen stats: Give people information on what happend to them in the past, is the problem going to come back and how it was resolved in the past.
Does: It finds the booking, checks the flight, tells the customer the first day they can fly, offers only flights with seats for the whole party, explains what Larkspur owes from the policy, and hands groups and refunds to a human.
Number: $0.0654 to $0.0299 model cost per conversation (-54%) after adding prompt caching, 5 ticket types, 3 runs each, cold cache; evals unchanged at 9/11.
Safety check: It offers to hold a seat but never books it; only the customer's own Confirm click does. We saw it in the K7PQ2M trace and in evals irrv-0101 and team-0101, where confirm_rebooking was never called.
Next: Make next_available_day check the whole party, not one seat, and stop the agent telling a customer with an unclear connection (T9WN4C) that they have not missed it when it cannot see the inbound flight.
Still broken: An angry customer threatening legal action (R8KD3F) gets a normal entitlements answer and is never handed to a human; eval tone-0101 fails on both rules and judge, every run.
Lever: cost

## Priya asked

Costs:
Wrong:
Runs it:
Left out:
