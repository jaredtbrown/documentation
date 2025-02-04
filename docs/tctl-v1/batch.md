---
id: batch
title: tctl v1.16 batch command reference
sidebar_label: batch
description: How to use the tctl v1.16 batch command
toc_max_heading_level: 4
---

<!-- THIS FILE IS GENERATED. DO NOT EDIT THIS FILE DIRECTLY -->

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

**How to run a tctl batch command.**

A `tctl batch` command enables you to affect multiple existing <a class="tdlp" href="/workflows#workflow-execution">Workflow Executions<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">What is a Workflow Execution?</p><p class="tdlppd">A Temporal Workflow Execution is a durable, scalable, reliable, and reactive function execution. It is the main unit of execution of a Temporal Application.</p><p class="tdlplm"><a href="/workflows#workflow-execution">Learn more</a></p></div></a> with a single command.
A batch job runs in the background and affects Workflow Executions one at a time.

Use <a class="tdlp" href="#start">tctl batch start<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">tctl batch start</p><p class="tdlppd">How to start a batch job using tctl.</p><p class="tdlplm"><a href="#start">Learn more</a></p></div></a> to start a batch job.

When starting a batch job, you must provide a <a class="tdlp" href="/visibility#list-filter">List Filter<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">What is a List Filter?</p><p class="tdlppd">A List Filter is the SQL-like string that is provided as the parameter to an Advanced Visibility List API.</p><p class="tdlplm"><a href="/visibility#list-filter">Learn more</a></p></div></a> and the type of batch job that should occur.
Batch jobs run in the background and affect Workflow Executions one at a time.

The List Filter identifies the set of Workflow Executions to be affected by the batch job.
The `tctl batch start` command shows you how many Workflow Executions will be affected by the batch job and asks you to confirm before proceeding.

The batch type determines what other parameters you must provide and what is being affected.
There are three types of batch jobs:

- Signal: Send a Signal to the set of Workflow Executions that the List Filter specifies.
- Cancel: Cancel the set of Workflow Executions that the List Filter specifies.
- Terminate: Terminate the set of Workflow Executions that the List Filter specifies.

A successfully started batch job returns a Job ID.
You can use this Job ID in the `tctl batch describe` command, which describes the progress of a specific batch job.

You can also use the Job ID to terminate the batch job itself.
Terminating a batch job does not roll back the operations already performed by the batch job.

### tctl batch commands

- <a class="tdlp" href="#describe">`tctl batch describe`<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">tctl batch describe</p><p class="tdlppd">How to describe the progress of a batch job using tctl.</p><p class="tdlplm"><a href="#describe">Learn more</a></p></div></a>
- <a class="tdlp" href="#list">`tctl batch list`<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">tctl batch list</p><p class="tdlppd">How to list batch jobs using tctl.</p><p class="tdlplm"><a href="#list">Learn more</a></p></div></a>
- <a class="tdlp" href="#start">`tctl batch start`<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">tctl batch start</p><p class="tdlppd">How to start a batch job using tctl.</p><p class="tdlplm"><a href="#start">Learn more</a></p></div></a>
- <a class="tdlp" href="#terminate">`tctl batch terminate`<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">tctl batch terminate</p><p class="tdlppd">How to terminate a batch job using tctl.</p><p class="tdlplm"><a href="#terminate">Learn more</a></p></div></a>

## start

The `tctl batch start` command starts a batch job.

`tctl batch start --query <value> [<modifiers>]`

The following modifiers control the behavior of the command.

### `--query`

_Required modifier_

Specify the <a class="tdlp" href="/workflows#workflow-execution">Workflow Executions<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">What is a Workflow Execution?</p><p class="tdlppd">A Temporal Workflow Execution is a durable, scalable, reliable, and reactive function execution. It is the main unit of execution of a Temporal Application.</p><p class="tdlplm"><a href="/workflows#workflow-execution">Learn more</a></p></div></a> that this batch job should operate.

The SQL-like query of <a class="tdlp" href="/visibility#search-attribute">Search Attributes<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">What is a Search Attribute?</p><p class="tdlppd">A Search Attribute is an indexed name used in List Filters to filter a list of Workflow Executions that have the Search Attribute in their metadata.</p><p class="tdlplm"><a href="/visibility#search-attribute">Learn more</a></p></div></a> is the same as used by the `tctl workflow list --query` command.

Alias: `-q`

**Example**

```bash
tctl batch start --query <value>
```

### `--reason`

Specify a reason for running this batch job.

Alias: `--re`

**Example**

```bash
tctl batch start --query <value> --reason <string>
```

### `--batch_type`

Specify the operation that this batch job performs. The supported operations are `signal`, `cancel`, and `terminate`.

Alias: `--bt`

**Example**

```bash
tctl batch start --query <value> --batch_type <operation>
```

### `--signal_name`

Specify the name of a <a class="tdlp" href="/workflows#signal">Signal<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">What is a Signal?</p><p class="tdlppd">A Signal is an asynchronous request to a Workflow Execution.</p><p class="tdlplm"><a href="/workflows#signal">Learn more</a></p></div></a>. This modifier is required when `--batch_type` is `signal`.

Alias: `--sig`

**Example**

```bash
tctl batch start --query <value> --batch_type signal --signal_name <name>
```

### `--input`

Pass input for the <a class="tdlp" href="/workflows#signal">Signal<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">What is a Signal?</p><p class="tdlppd">A Signal is an asynchronous request to a Workflow Execution.</p><p class="tdlplm"><a href="/workflows#signal">Learn more</a></p></div></a>. Input must be in JSON format.

Alias: `-i`

**Example**

```bash
tctl batch start --query <value> --input <json>
```

### `--rps`

Specify RPS of processing. The default value is 50.

**Example**

```bash
tctl batch start --query <value> --rps <value>
```

### `--yes`

Disable the confirmation prompt.

**Example**

```bash
tctl batch start --query <value> --yes
```

## list

Alias: `l`

The `tctl batch list` command lists all batch jobs.

`tctl batch list [<modifiers>]`

The following modifier controls the behavior of the command.

### `--pagesize`

Specify the maximum number of batch jobs to list on a page. The default value is 30.

Alias: `--ps`

**Example**

```bash
tctl batch list --pagesize <value>
```

## describe

Alias: `desc`

The `tctl batch describe` command describes the progress of a batch job.

`tctl batch describe --job_id <id>`

The following modifier controls the behavior of the command.

### `--job_id`

_Required modifier_

Specify the job ID of a batch job.

Alias: `--jid`

**Example**

```bash
tctl batch describe --job_id <id>
```

## terminate

The `tctl batch terminate` command terminates a batch job.

`tctl batch terminate --job_id <id> [<modifiers>]`

The following modifiers control the behavior of the command.

### `--job_id`

_Required modifier_

Specify the job ID of a batch job.

Alias: `--jid`

**Example**

```bash
tctl batch terminate --job_id <id>
```

### `--reason`

Specify a reason for terminating this batch job.

Alias: `--re`

**Example**

```bash
tctl batch terminate --job_id <id> --reason <string>
```

