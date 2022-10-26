---
id: how-to-replay-a-workflow-execution-in-typescript
title: How to replay a Workflow Execution in TypeScript
sidebar_label: Replay a Workflow Execution
description: Replay a Workflow Execution
tags:
  - developer-guide
  - sdk
  - typescript
---

Use [worker.runReplayHistories](https://typescript.temporal.io/api/classes/worker.Worker#runreplayhistories)
or [worker.runReplayHistory](https://typescript.temporal.io/api/classes/worker.Worker#runreplayhistory)
to replay multiple or one Workflow Histories.

In the following example, histories are downloaded from the server, and then replayed:

```ts
const histories = # TODO: Use list workflows API once it's ready
await Worker.runReplayHistories(
  {
    workflowsPath: require.resolve('./your/workflows'),
  },
  { histories }
);
```

In the next example, a single history is loaded from a JSON file on disk:

```ts
const filePath = './history_file.json';
const hist = await JSON.parse(fs.promises.readFile(filePath, 'utf8'));
await Worker.runReplayHistory(
  {
    workflowsPath: require.resolve('./your/workflows'),
  },
  hist,
);
```

In both examples if Workflow History is non-deterministic, an error will be thrown. You can choose
to wait until all histories have been replayed with `runReplayHistories` by setting the `failFast`
option to `false`.

See a video on how to replay in [here](https://www.youtube.com/watch?v=fN5bIL7wc5M).
