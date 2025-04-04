# Changelog

## [25.0.0] - 2025-03-17

It has been possible to recover a running engine. The execution was overwritten and all references to timers etc was lost. This stops with this version. Either stop the the execution or wait for it to end if the engine should be re-used. It is highly recommended to initiate a new Engine when recovering from state.

### Breaking

- Disallow a running engine to be recovered and resumed. Recommended is to recover and resume a new Engine instance with state or stop the instance before recovering.

### Fixes

- minor update of moddle-context-serializer brings some performance improvement

## [24.0.1] - 2025-03-14

- fix recover engine with options not keeping scripts and logger from when initiated

> NB! Next major versions will not accept recovering a running engine.

## [24.0.0] - 2025-02-08

- major update [`bpmn-elements@17`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md), something about mitigating weird formatting behaviour

## [23.0.2] - 2024-10-22

- move `smqp` to peerDependencies since it's included in `bpmn-elements`
- patch [`bpmn-elements@16.2.1`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)
- use optional chaining and remove futile object creations

## [23.0.1] - 2024-09-08

- patch [`bpmn-elements@16.1.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)
- fix AppVeyor build badge

## [23.0.0] - 2024-08-08

### Breaking

- changed `ConditionalEventDefinition` behaviour in [`bpmn-elements@16`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

## [22.0.2] - 2024-07-10

- patch [`bpmn-elements@15.0.3`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

## [22.0.1] - 2024-06-19

- for a number of years the `extendFn` option has been accepted, but never passed to moddle-context-serializer. Now it is
- fix type declaration for options `extendFn` and `TypeResolver`
- type declare that a generic listener instance with an emit function works just as well as a full blown new EventEmitter

## [22.0.0] - 2024-06-14

Performance tweaks.

- major bump [`bpmn-elements@15`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)
- major bump of [`smqp@9`](https://github.com/paed01/smqp/blob/default/CHANGELOG.md)

### Breaking

- drop support for node 14 and 16
- JavaScripts.Script property scripts is now a Map

## [21.1.0] - 2024-05-17

- minor bump [`bpmn-elements@14.1.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md), addresses issue #180

## [21.0.0] - 2024-05-04

Stop execution if invalid time duration, cycle, or date is encountered.

### Breaking

- invalid `TimerEventDefinition` timer type value stops execution according to [`bpmn-elements@14`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md). Old behaviour can be achieved by using bpmn-elements@13

## 20.0.2

- patch away package prettier from smqp

## 20.0.1

- hoist current definition environment output to engine environment output if run fails
- Major bump `bpmn-moddle@9`
- Minor bump [`moddle-context-serializer@4.2`](https://github.com/paed01/moddle-context-serializer/blob/master/CHANGELOG.md)
- Minor bump [`bpmn-elements@13.2.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

## 20.0.0

- turn into esm with exports for node
- build with node >= 18, should still work with earlier versions but proceed with caution and make tests
- remove eslint formatting rules in favor of prettier, touched basically all files but now it is "pretty"
- prototype `ProcessOutputDataObject` and make properties id and type readonly

## 19.0.1

- Patch [`bpmn-elements`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

## 19.0.0

Upgrade is recommended since nasty evergroving state size is fixed.

- Major bump [`bpmn-elements@13`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)
- remove enumerable flag on prototype properties

## 18.0.0

Only breaking if multi-instance sub-process executions are inspected after sub-process run is completed. Picture a multi-instance sequential sub-process with a cardinality of 100. One hundred items in a list occupies some memory. That will not stand. Consequently, they are now removed when iteration completes and eventually collected by gc.

- Major bump [`bpmn-elements@12`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

## 17.1.1

- Finetuning Engine.execute and Engine.resume callback arg typization by @bestmazzo
- Patch [`bpmn-elements`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

## 17.1.0

- Clear arbitrary engine timers on end and error, not just on stop as it was before
- Bump [`smqp@8`](https://github.com/paed01/smqp/blob/default/CHANGELOG.md)

## 17.0.0

- Even slimmer state from [`bpmn-elements@11`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md). In most cases it should be safe to update, unless you inspect element states for some reason
- Remove node v14 build because it fails with `node:stream/promises` reasons. Still developing and running tests with node v14 since it works on my machine

## 16.1.0

- Introduce lane behaviour by upgrading [`bpmn-elements@10.1.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)
- stop apparently returns a promise, adjust type declaration to reflect that

## 16.0.1

- Patch [`bpmn-elements@10.0.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

## 16.0.0

- Refactor type declarations using types from bpmn-elements, smqp, etc
- add activity status property
- Bump [`bpmn-elements@9.1.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

## 15.1.3

- fix(types): add missing `settings` option

## 15.1.2

- Patch [`bpmn-elements@8.2.2`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

## 15.1.1

- Patch [`bpmn-elements@8.2.1`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

## 15.1.0

- Bump [`bpmn-elements@8.2.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)
- Bump [`smqp@6.1.0`](https://github.com/paed01/smqp/blob/default/CHANGELOG.md)

## 15.0.0

### Breaking

- Drop node 12 support

## 14.1.1

- fix(types): add missing `moddleContext` option

## 14.1.0

- Bump [`bpmn-elements@8.1.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md) with support for bound non-interrupting repeating timeCycle

## 14.0.0

### Breaking

- Engine is prototyped, can still be invoked without new
- Bump [`bpmn-elements@8.0.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md) with support for bpmn:CallActivity (#97)
- Bump [`smqp@6.0.0`](https://github.com/paed01/smqp/blob/default/CHANGELOG.md)

## 13.0.2

- fix for removing wrong listener on error by @allain

## 13.0.1

### Type definition

- fix: set the correct `Logger` type in `BpmnEngineOptions` by @leon19

## 13.0.0

- Slimmer state from [`bpmn-elements@6`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md). In most cases it should be safe to update, unless you inspect the broker states for some reason

## 12.0.5

- Prettify and actualize ts types

## 12.0.4

Update package.json to reflect what was stated in v12.0.3.

- And add tests for issue #142

## 12.0.3

- Bump [`bpmn-elements@5.2.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md) with support for bpmn:Property (#139)
- Bump [`smqp@5`](https://github.com/paed01/smqp/blob/default/CHANGELOG.md)

## 12.0.2

- Bump [`bpmn-elements@5.1.2`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)
- Bump [`smqp@4`](https://github.com/paed01/smqp/blob/default/CHANGELOG.md)

## 12.0.1

- Bump [`bpmn-elements@5.1.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md) with "support" for bpmn:Group and Category. Kinda bugfix for the engine to be honest.

## 12.0.0

- Something about loop characteristics in [`bpmn-elements@5.0.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md). Not sure that a major was necessary, but semver is semver. In most cases it should be safe to update, unless you have used parallel loops without collection or cardinality (∞)?

## 11.4.2

- Bump [`bpmn-elements@4.4.2`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)
- Add badge [![Coverage Status](https://coveralls.io/repos/github/paed01/bpmn-engine/badge.svg?branch=master)](https://coveralls.io/github/paed01/bpmn-engine?branch=master)

## 11.4.1

- Patch `moddle-context-serializer@0.16.1`
- Patch [`bpmn-elements@4.3.4`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

## 11.4.0

- Expose execution api on property `engine.execution` since it is basically the same as when returned on events

## 11.3.2

- Bump [`bpmn-elements@4.3.2`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)
- Add tests for issue #125

## 11.3.1

### Type definition

- Engine.resume returns Promise that resolves BpmnEngineExecutionApi by @mdwheele

## Misc

- Pick recovered definition source from passed sources if not present on definition state

## 11.3.0

- Bump [`bpmn-elements@4.3.1`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md) to version with timer tracking
- Add the above timers, i.e. `setTimeout` and `clearTimeout`, to inline script context
- Clear all timers when execution is stopped

## 11.2.1

- [`bpmn-elements@4.1.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)
- `bpmn-moddle` patch

## 11.2.0

- Major bump of [`bpmn-elements@4`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md). No apparent breaking change to engine except that gives more power to a custom script handler

## 11.1.0

- [`bpmn-elements@3.1.0`](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

## 11.0.0

All conditional flows from `bpmn-elements@3`.

### Breaking

- Outbound sequence flow with script condition requires `next(err, result)` to be called where result decides if it should be taken or discarded

### Addititions

- Outbound sequence flow conditions are evaluated for all activities, as well as default flow
- Process now also have `cancelActivity` function for facilitation

## 10.1.2-3

Type definitions courtesy of @saeedtabrizi.

- Some type fix and add engine broker types

## 10.1.1

- Add type definition to package.json

## 10.1.0

- Bump bpmn-elements to 2.1, adding support for Transaction and CancelEventDefinition see [change log](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

## 10.0.0

Untangle issue #105 which resulted in refactoring outbound sequence flow handling.

- Bump bpmn-elements from 1.6 to 2, see [change log](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)

### Breaking

- No more `flow.pre-flight` events from sequence flows, not sure that anyone used them, but still
- Activities now publish (or emit) `activity.leave` when all outbound flows have been taken/discarded

## 9.2.0

- Bump bpmn-elements from 1.2 to 1.6, see [change log](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md)
- Support adding definition source with `addSource` function

## 9.1.1

- Bump bpmn-elements to version with ability to signal waiting start event from definition

## 9.1.0

- Bump bpmn-elements to version with shake activity functionality
- Bump moddle-context-serializer@0.16 with scripts and timers

### Additions

- Add engine option `sourceContext` to hold pre-serialized context

## 9.0.0

### Additions

- Add signal function to engine execution api

### Breaking changes

- Bump bpmn-elements to v1.0.0 with some [breaking changes](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md) regarding MessageEventDefinition and SignalEventDefinition

## 8.7.0

- Bump bpmn-moddle, bpmn-elements, and smqp to latest

## 8.6.0

- Add typescript declaration file (Saeed Tabrizi)

## 8.5.0

- Bump [bpmn-elements@0.12.1](https://github.com/paed01/bpmn-elements/blob/master/CHANGELOG.md#0121)

## 8.4.0

- Bump bpmn-elements@0.11.0 with new ability to use process extensions

## 8.3.0

- Bump bpmn-elements@0.9.0 to support compensation

## 8.2.1

- Bump bpmn-elements@0.8.1 that expose sequence flow name

## 8.2.0

- Bump bpmn-elements@0.8.0 and moddle-context-serializer to support StandardLoopCharacteristics

## 8.1.0

- Bump bpmn-elements@0.7.0 to support LinkEventDefinition

## 8.0.0

### Breaking changes

- Bump bpmn-elements to v0.6.0 with refactored MessageEventDefinition, ReceiveTask, and some bug fixes from @TallaInc

### Additions

- Recover takes optional options that completely overrides environment and passes it along to the recovered definitions

## 7.1.0

- Bump bpmn-elements to v0.5.0

## 7.0.0

Bump bpmn-elements and bpmn-moddle (which now has a node dist :).

### Breaking changes

- Implementation of ErrorEventDefinition is now closer to the BPMN 2.0 spec

### Additions

- Start sub-process' sub-process if sub-process throws an error
- Expose the name of the element that emitted event

## 6.2.0

### Additions

- Bump bpmn-elements and serializer and thereby add support for ConditionalEventDefinition

## 6.1.0

### Additions

- Expose humanPerformer and potentialOwner

## 6.0.0

Use [bpmn-elements](https://github.com/paed01/bpmn-elements) to execute elements.

Behind the scenes the entire definition execution is replaced with [bpmn-elements](https://github.com/paed01/bpmn-elements)

### Breaking changes

- Node version >= 10 is required
- Events are not emitted with name of the activity, i.e. no more `enter-task_a8dje7` emits
- Most events are emitted with the type of element as prefix, e.g. `activity.start`, one exception is `wait` wich is still emitted as `wait`
- `getPendingActivities()` is renamed to `getPostponed()`

### Changes

- Change license to MIT

## 5.0.0

### Breaking changes

- Engine `execute` callback is called when execution completes
- Node version >= 8.9 is supported
- `SendTask` message requires output
- `ParallelGateway` emits `start` on first taken inbound, i.e. discarded inbound are just registered
- Extensions have been moved to separate project [bpmn-engine-extensions](https://github.com/paed01/bpmn-engine-extensions)

### Additions

- Support for parallell task loop

## 4.0.0

### Breaking changes

- Parallel gateway `getState()` returns pending inbound and/or pending outbound, so old states are not supported

### Changes

- Add support for Manual task
- Support camunda input/output for Exclusive Gateways, input is passed to conditional flows
- Support camunda errorCodeVariable and errorMessageVariable for Error Events

## 3.2.0

- Add support for SendTask and ReceiveTask

## 3.1.0

### Changes

- A start event with form key will also emit wait

## 3.0.0

### Breaking changes

- The `Engine` now handles definitions instead of processes, hence:
  - `execute(callback)` returns executed definition in callback instead of process
  - `getState()` returns executing definition instead of processes
- Engine `getState()` and `resume(state)` does no longer return or need the actual definition source. They work with moddle contexts.
- `Transformer` is now called `transformer` since it is not called with `new`
- Engine instance `resume()` is now a "static" function on engine, i.e. `Engine.resume`

### Changes

- `Definition` is exposed and can be executed with moddle context and options, see [documentation](/docs/Definition.md)
- `validation` is exposed and harbours functions for validating moddle context and execute options
- Support camunda input forms for user task and start event

## 2.0.0

- Output from tasks with defined `camunda:inputOutput` now updates context variables. The previous behavior was to save result to `variables.taskInput`. That will still happen if no output is defined.

### Changes

- Support service connector (#4)
- Support map and list input/output types from modeller (#5)
