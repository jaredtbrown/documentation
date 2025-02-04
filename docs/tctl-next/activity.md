---
id: activity
title: tctl version-next activity command reference
sidebar_label: activity
description: How to use the tctl version-next activity command
toc_max_heading_level: 4
---

<!-- THIS FILE IS GENERATED. DO NOT EDIT THIS FILE DIRECTLY -->

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

The `tctl activity` commands enable <a class="tdlp" href="/activities#activity-execution">Activity Execution<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">What is an Activity Execution?</p><p class="tdlppd">An Activity Execution is the full chain of Activity Task Executions.</p><p class="tdlplm"><a href="/activities#activity-execution">Learn more</a></p></div></a> operations.

Alias: `a`

- [`tctl activity complete`](/tctl-next/activity#complete)
- [`tctl activity fail`](/tctl-next/activity#fail)

## complete

The `tctl activity complete` command completes an <a class="tdlp" href="/activities#activity-execution">Activity Execution<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">What is an Activity Execution?</p><p class="tdlppd">An Activity Execution is the full chain of Activity Task Executions.</p><p class="tdlplm"><a href="/activities#activity-execution">Learn more</a></p></div></a>.

`tctl activity complete <modifiers>`

The following modifiers are supported and control the behavior of the command.
Always include required modifiers when executing this command.

- [--activity-id](/tctl-next/modifiers#--activity-id)
- [--identity](/tctl-next/modifiers#--identity)
- [--reason](/tctl-next/modifiers#--reason)
- [--run-id](/tctl-next/modifiers#--run-id)
- [--workflow-id](/tctl-next/modifiers#--workflow-id)

## fail

The `tctl activity fail` command fails an <a class="tdlp" href="/activities#activity-execution">Activity Execution<span class="tdlpiw"><img src="/img/link-preview-icon.svg" alt="Link preview icon" /></span><div class="tdlpc"><p class="tdlppt">What is an Activity Execution?</p><p class="tdlppd">An Activity Execution is the full chain of Activity Task Executions.</p><p class="tdlplm"><a href="/activities#activity-execution">Learn more</a></p></div></a>.

`tctl activity fail <modifiers>`

The following modifiers are supported and control the behavior of the command.
Always include required modifiers when executing this command.

- [--activity-id](/tctl-next/modifiers#--activity-id)
- [--detail](/tctl-next/modifiers#--detail)
- [--identity](/tctl-next/modifiers#--identity)
- [--reason](/tctl-next/modifiers#--reason)
- [--run-id](/tctl-next/modifiers#--run-id)
- [--workflow-id](/tctl-next/modifiers#--workflow-id)

