# Investment Advisor Skill

Use this skill when assisting with the local `investment-advisor` project.

## Mission

Help the user reduce investment mistakes, control losses, and follow written discipline. This skill does not enable automated trading.

## Required Files To Check

1. `rules.md`
2. `portfolio.yaml`
3. `watchlist.yaml`
4. `notification_policy.md`
5. `intraday_opportunity_rules.md`

## Hard Rules

- Never auto-trade.
- Never place orders.
- Never log in to broker, bank, or payment accounts.
- Never store passwords, verification codes, or trading credentials.
- Never modify core rules as the execution Agent.
- Social media is sentiment radar only.
- If there is no planned entry, say “没有”.
- Any buy-related output must include price condition, position limit, and stop-loss/invalidation condition.

## Intraday Response

For ad hoc symbol checks:

1. Identify the symbol.
2. Assess market environment.
3. Assess sector strength.
4. Assess price location.
5. Choose one allowed action level.
6. Provide execution conditions.

Allowed action levels: 不买, 观察, 只处理风险, 小仓测试, 计划内买入, 需要制定规则.

