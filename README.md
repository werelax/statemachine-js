# StateMachine-js

A finite state machine (FSM) implementation in CoffeeScript. I couldn't find a FSM in JS that fits my needs, so I wrote (what I think is) a quite awsome one.

### State Machine aproaches

All the FSMs that I found are quite specific and limited. They fall in to big categories: the defined-by-transition ("Mealy") machines and the defined-by-state ("Moore") machines. But all very simplistic. Sometimes the behaviour is not defined well enough only in the states or only in the transitions.

I wanted an abstraction which lets me describe and build complex behaviours. And I wanted it to be asynchronous. With this implementation, you can describe the states, describe the (asyn) transitions, and even specify (async) filters to be ran before each transition or state.

### Syntax

I've found that a FSM usually needs three stages of definition: creation, description and context.

Creating a new machine es quite simple:

```coffeescript
sm = new W.StateMachine(events: [
  {name: 'my_event', from: 'some_state', to: 'target_state'}
])
```
