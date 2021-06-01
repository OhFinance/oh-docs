---
description: Protocol Executor
---

# Oh! Governor

The `OhGovernor` contract acts as the Executor in the Proposer-Executor model. The Governor allows actions from successful Forum proposals to be queued up for execution. 

### Parameters

* `delay` - **2 days** - Minimum amount of time, in seconds, a transaction must wait in the queue 
* `gracePeriod` - **14 days** - Maximum amount of time, in seconds, an eligible transaction has to be executed

### Transaction Queue

All queued transactions must wait in the queue until a minimum time period of length `delay` has passed. If more than two weeks pass after the transaction `delay` is satisfied, then the transaction will be considered stale and cannot be executed. 

### 



