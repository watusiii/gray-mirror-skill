---
name: gray-mirror
description: Map any situation as a stock-and-flow system (Donella Meadows) and run it as a live simulation. Use when someone wants to see how their money, energy, habits, team, game economy, or any system changes over time, or asks "what happens if...".
---

# Gray Mirror

By Law Watusi. Make the unseen seen: turn a situation into stocks, flows, and loops, then watch it run.

## How to use
1. Talk with the person until you know what piles up (stocks), what fills and drains it (flows), and what feeds back (links and loops). Ask for real numbers. Pick one time unit.
2. Write the model in Gray Mirror notation (below). Nothing outside the notation.
3. Render it with `renderer.html`: replace the text inside `<textarea id="gmsrc">` with the model.
   - If you can show interactive widgets in chat, show the renderer there.
   - Otherwise, save it as an .html file or artifact the person can open.
4. Before they hit Run, ask them to predict what the line will do. Then compare. The learning is in the gap.
5. For "what if" questions, change one line and rerun.

## Notation v0
```
tick = week
stock  Money = 788
cloud  Spark
cloud  Bills
flow   Driving: Spark -> Money = 110
flow   Spending: Money -> Bills = 10% of Money
link   Money ~> Spending
loop   B  Money, Spending
```
- `tick = <unit>`: the time step (day, week, month).
- `stock Name = n`: something that accumulates and can be measured at a moment.
- `cloud Name`: where a flow comes from or goes to outside the map.
- `flow Name: A -> B = n` or `= p% of Stock`: a rate per tick. The arrow sets the direction. Rates are never negative.
- `link Stock ~> Flow`: the stock's level changes that flow's rate. Delayed: `~||>`.
- `loop R|B parts`: reinforcing (snowballs) or balancing (seeks a level).

## Rules (from Meadows, Thinking in Systems)
- Only flows change stocks.
- A stock is a noun you could count or measure. If it can't change over time, it isn't a stock.
- Only mark a link or loop when a stock's level really changes a flow. A fixed rate has no link.
- Don't invent symbols or meanings. If unsure, say so.
- Balancing loop level = inflow ÷ drain rate. Use this to check results.

## Credits
Gray Mirror (notation, renderer, and skill) by Law Watusi, 2026.
Built on system dynamics, founded by Jay Forrester (MIT, 1950s), and the stock-and-flow language as taught by Donella Meadows in *Thinking in Systems: A Primer* (2008). Related work: Joris Dormans' Machinations (game economies), Nicky Case's Loopy, Insight Maker, Stella, and Vensim.
