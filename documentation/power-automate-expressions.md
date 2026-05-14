# Power Automate Expressions

This document contains key expressions used in the AI-powered request automation flow.

## Clean Email Body Variable

```text
variables('varCleanBody')
```

## Request ID Extraction

```text
if(
  contains(variables('varCleanBody'), 'Request ID:'),
  trim(first(split(last(split(variables('varCleanBody'), 'Request ID:')), decodeUriComponent('%0A')))),
  ''
)
```

## Customer Extraction

```text
if(
  contains(variables('varCleanBody'), 'Customer:'),
  trim(first(split(last(split(variables('varCleanBody'), 'Customer:')), decodeUriComponent('%0A')))),
  ''
)
```

## Priority Extraction

```text
if(
  contains(variables('varCleanBody'), 'Priority:'),
  trim(first(split(last(split(variables('varCleanBody'), 'Priority:')), decodeUriComponent('%0A')))),
  'Unknown'
)
```

## Description Extraction

```text
if(
  contains(variables('varCleanBody'), 'Issue:'),
  trim(first(split(last(split(variables('varCleanBody'), 'Issue:')), decodeUriComponent('%0A')))),
  ''
)
```

## Stakeholders Extraction

```text
if(
  contains(variables('varCleanBody'), 'Stakeholders:'),
  trim(first(split(last(split(variables('varCleanBody'), 'Stakeholders:')), decodeUriComponent('%0A')))),
  ''
)
```

## Confidence and Unknown Routing

```text
or(
  less(variables('varAIConfidence'), 60),
  equals(body('Parse_JSON')?['requestType'], 'Unknown')
)
```

## Processing Status Logic

```text
if(
  equals(variables('varRouteDecision'), 'Manual Review'),
  'Manual Review',
  'AI Processed'
)
```

## SLA Due Date Examples

```text
addDays(utcNow(), 1)
addDays(utcNow(), 5)
addDays(utcNow(), 14)
addToTime(utcNow(), 4, 'Hour')
```

## Audit Log Example

```text
concat(
  'Created by flow on ',
  utcNow(),
  '. Route decision: ',
  variables('varRouteDecision'),
  '.'
)
```

## Duplicate Detection Condition

```text
greater(length(body('Get_items')?['value']), 0)
```

## Route Decision Variable

```text
variables('varRouteDecision')
```

## SLA Due Date Variable

```text
variables('varSLADueDate')
```
