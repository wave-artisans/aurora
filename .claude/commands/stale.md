# Stale Command

Find outdated documents that need review.

## Usage

```
/stale [--threshold <days>] [--mode <mode>]
```

## Description

Identifies documents that haven't been updated recently and may contain outdated information. Helps maintain knowledge base freshness.

## Options

- `--threshold`: Days since last update (default: 90)
- `--mode`: Filter by Aurora mode

## Staleness Factors

1. **Last Updated**: Time since `updated` field changed
2. **Content Type**: Some docs age faster than others
3. **References**: Do linked docs still exist?
4. **Active Mode**: Archived docs excluded by default

## Content Type Thresholds

| Type | Default Threshold | Rationale |
|------|-------------------|-----------|
| Project docs | 30 days | Active work should update |
| Meeting notes | 180 days | Historical, less urgent |
| Specs | 60 days | Should track changes |
| Reference | 90 days | Periodic review needed |
| Personal | 365 days | Life docs age slower |

## Output

```
🍂 Stale Content Analysis

Threshold: 90 days
Documents checked: 145
Stale items found: 18

---

## Critical (Not updated in 6+ months)

1. **api-v1-spec.md** 🟢 Focus
   Last updated: 2025-06-15 (185 days ago)
   Reason: Still referenced by 3 active docs
   Risk: Outdated information in use
   → Action: Update or mark as superseded

2. **client-onboarding.md** 🟡 Ops
   Last updated: 2025-05-20 (210 days ago)
   Reason: Process doc, likely outdated
   Risk: New clients may get wrong info
   → Action: Review and update process

## Warning (90-180 days)

3. **security-policy.md** 📚 Library
   Last updated: 2025-09-01 (107 days ago)
   Reason: Policy docs need regular review
   → Action: Schedule policy review

4. **team-directory.md** 📚 Library
   Last updated: 2025-08-15 (124 days ago)
   Reason: Team may have changed
   → Action: Verify current team

[... more items ...]

---

## By Mode

| Mode | Stale | Total | % Stale |
|------|-------|-------|---------|
| 🟢 Focus | 5 | 42 | 12% |
| 🟡 Ops | 8 | 28 | 29% ⚠️ |
| 📚 Library | 5 | 15 | 33% ⚠️ |

## Recommendations

1. **Ops folder needs attention**
   High staleness rate suggests process docs outdated
   Consider: Monthly ops doc review

2. **Library review needed**
   Reference docs should be current
   Consider: Quarterly library audit

## Quick Actions

/retrieve mode:ops modified:<90d    # Find what IS current
/task new "Review stale ops docs"   # Create review task
```

## Excluding from Stale Check

Add to document front matter:
```yaml
stale-check: false  # Exclude from stale analysis
```

For intentionally static docs (historical records, archives).

## Related Commands

- `/validate` - System health checks
- `/gaps` - Find missing documentation
- `/toc-update` - Refresh navigation
