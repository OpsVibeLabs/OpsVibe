# ADR-001: Repository Strategy

## Status

Accepted

## Date

2026-07-18

## Context

OpsVibe consists of multiple applications and shared libraries, including the dashboard, backend API, background workers, SDK, shared UI components, shared types, and engineering tooling.

A repository strategy is required to enable efficient development, code reuse, consistent tooling, and scalable collaboration.

## Decision Drivers

- Shared domain models
- Shared TypeScript types
- Shared UI components
- Unified engineering standards
- Simplified local development
- Efficient CI/CD
- Ease of refactoring

## Considered Options

### Option 1: Polyrepo

Each application and shared library exists in its own Git repository.

### Option 2: Monorepo

All applications and shared packages exist in a single repository managed with workspaces.

## Decision

OpsVibe will use a **Monorepo** managed with **pnpm Workspaces** and **Turborepo**.

Applications will remain logically separated while sharing common libraries through workspace packages.

## Consequences

### Positive

- Shared code without package publishing
- Consistent tooling and configuration
- Simplified refactoring
- Unified CI/CD
- Better developer experience
- Easier onboarding

### Negative

- Larger repository size
- Additional workspace tooling
- Build orchestration complexity

These trade-offs are acceptable given the project's goals and expected growth.