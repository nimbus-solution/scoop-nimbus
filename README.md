# scoop-nimbus

Official Scoop bucket for **[Renmy](https://renmy.net)** (formerly Nimbus) — run Salesforce Apex tests locally, without an org.

---

## The problem

Running Apex tests requires a connected Salesforce org. That means waiting for scratch org provisioning, managing org pools in CI, debugging shared-org pollution, and spending days onboarding new developers before they can run a single test.

Meanwhile, every other language just runs tests locally.

## What Renmy does

Renmy runs your Apex tests on your machine — no Salesforce connection, no Docker, no setup beyond pointing it at your SFDX project.

```
❯ renmy test "*"

  ✓  AccountServiceTest.testCreateAccount     12ms
  ✓  AccountServiceTest.testBulkInsert         8ms
  ✓  CalculatorTest.testAddition               2ms
  ✓  CalculatorTest.testDivision               3ms
  ✓  AccountTriggerTest.testBeforeInsert       15ms
  ✓  AccountTriggerTest.testAfterInsert        11ms

  6 passed · 0 failed · 51ms total
```

Real SOQL. Real triggers. Real DML. Backed by an embedded PostgreSQL database — not a simulated environment.

## What it supports

| Area | Coverage |
|---|---|
| Language | Classes, interfaces, enums, inheritance, generics, exception handling |
| Data | SOQL, DML (insert, update, delete, upsert), bind variables, aggregates, relationships |
| Automation | Before/after triggers, record-triggered flows, platform event flows |
| Testing | `@isTest`, `@testSetup`, `System.assert`, Test.startTest/stopTest, per-test isolation |

## Why developers use it

- **Instant feedback** — tests run in milliseconds, not minutes
- **No org dependency** — works offline, works on CI without DevHub or scratch org pools
- **JUnit XML + Cobertura coverage** — plug into GitHub Actions, SonarQube, Codecov like any other language
- **AI-agent ready** — fast enough for write-test-fix loops with Claude Code, Cursor, or Copilot

---

## Install

```powershell
scoop bucket add renmy https://github.com/renmy-solutions/scoop-nimbus
scoop install renmy
```

The bucket keeps the repository name `scoop-nimbus` and publishes two manifests from every release: `renmy`, which installs `renmy.exe`, and `nimbus`, which installs `nimbus.exe`. Both are the same release. An existing install of `nimbus` keeps updating with `scoop update nimbus`.

## Upgrade

```powershell
scoop update renmy
```

## Verify

```powershell
renmy --version
```

---

[Documentation](https://renmy.net/docs) · [Website](https://renmy.net) · [Releases](https://github.com/renmy-solutions/renmy/releases)
