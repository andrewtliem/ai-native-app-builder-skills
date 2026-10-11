# Architecture Plan

## Sources Read

## Summary

## Technical Context

## Architecture Diagram / Component Map

Use Mermaid so both people and AI agents can read the diagram. Add diagrams only where prose is easy to misread:

- `stateDiagram-v2` for each entity with a lifecycle (status field)
- `sequenceDiagram` for flows with more than two parties or an external service, including the failure path
- `erDiagram` when three or more entities are related

For each diagram, write one line: who reads it and what it helps check.

## Data Model

| Entity | Fields | Relationships | Validation |
|---|---|---|---|

## Contracts

| Contract | Input | Output | Error States |
|---|---|---|---|

## Research Notes

| Decision | Option Chosen | Alternatives | Rationale |
|---|---|---|---|

## Risks and Constraints

## Quickstart Validation

## Read-Back Assumptions

Behavior shown in a diagram or the data model that the PRD does not state. The student confirms or rejects each one; a rejection means the PRD needs an update.

| # | Assumption | Where It Appears | Student Decision | PRD / Clarification Update | Tag |
|---|---|---|---|---|---|
