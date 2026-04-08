# scoop-nimbus

Official Scoop bucket for **[Nimbus](https://testnimbus.dev)** — run Salesforce Apex tests locally, without an org.

---

## The problem

Running Apex tests requires a connected Salesforce org. That means waiting for scratch org provisioning, managing org pools in CI, debugging shared-org pollution, and spending days onboarding new developers before they can run a single test.

Meanwhile, every other language just runs tests locally.

## What Nimbus does

Nimbus runs your Apex tests on your machine — no Salesforce connection, no Docker, no setup beyond pointing it at your SFDX project.

```
❯ nimbus test "*"

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
scoop bucket add nimbus https://github.com/nimbus-solution/scoop-nimbus
scoop install nimbus
```

## Upgrade

```powershell
scoop update nimbus
```

## Verify

```powershell
nimbus --version
```

---

[Documentation](https://testnimbus.dev/docs) · [Website](https://testnimbus.dev) · [Releases](https://github.com/nimbus-solution/nimbus-releases)
