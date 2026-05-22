---
name: institutional-stock-research
description: Use when the user asks to research or select a stock, fund, sector, market theme, mainline opportunity, "主力" behavior, quant harvesting risk, retail sentiment, or whether a watched ticker has a buy/sell/add/reduce opportunity. Produces evidence-based institutional-style research using macro, sector, fundamentals, valuation, capital flow, price action, social sentiment, and the user's portfolio discipline. Never automates trades.
---

# Institutional Stock Research

## Purpose

Research stocks, funds, sectors, and market themes with an institutional-style evidence chain. Do not guess hidden "main force" intentions. Infer only from observable data such as price, volume, sector strength, filings, announcements, fund flows, margin financing, ETF behavior, 龙虎榜, and sentiment signals.

This skill supports analysis and decision discipline only. It must never place trades, log in to brokerage/payment accounts, or ask for passwords or verification codes.

## Required Project Context

Before answering, read or use:

- `research_framework.md`
- `portfolio.yaml`
- `rules.md`
- `watchlist.yaml`
- `notification_policy.md`
- `intraday_opportunity_rules.md`

If a file is unavailable, say which piece is missing and continue conservatively.

## Workflow

1. Classify the request:
   - Long-term core research.
   - Trend/opportunity research.
   - Short-term lottery trade check.
   - Fund/sector/theme research.
   - Live intraday buy/sell/add/reduce question.

2. Collect current evidence:
   - Broad market and relevant indices.
   - Sector relative strength, turnover, breadth, policy/industry catalysts.
   - Instrument quote, intraday high/low, volume/turnover, support/resistance, close confirmation if after market.
   - Fundamentals: business, financials, announcements, earnings, valuation, fund holdings if relevant.
   - Capital behavior: volume-price, closing strength, 龙虎榜, margin financing, ETF/fund flow, institutional holdings when available.
   - Sentiment: social media, public accounts, forums, group notes, but only as sentiment/crowding.

3. Separate evidence quality:
   - `facts`: observed data and official disclosures.
   - `inference`: reasoned interpretation from facts.
   - `missing`: important data not yet checked.
   - `opinion`: final judgment after rules.

4. Score with the 100-point framework from `research_framework.md`:
   - Market environment 15.
   - Mainline/sector 15.
   - Fundamentals/fund quality 20.
   - Valuation/safety margin 15.
   - Capital behavior 15.
   - Sentiment crowding 10.
   - Trade plan completeness 10.

5. Apply veto rules before any positive conclusion:
   - No stop-loss/invalidating condition for a short-term idea.
   - Short-term lottery exposure over limit or in observation zone while user wants to add.
   - Broad market risk-off day for a new short-term trade.
   - Buy reason only comes from social media.
   - The trade would contaminate a short-term thesis into a long-term account.

6. Map to the user's account type:
   - `core`: long-term quality or broad exposure; use DCA or planned batches.
   - `core_trend`: long-term/trend holding; add only by plan.
   - `theme_opportunity`: sector/theme opportunity; use smaller planned batches.
   - `short_term_lottery`: strict cap, no losing add, stop must be written first.
   - `avoid`: insufficient evidence, too crowded, broken thesis, or poor risk/reward.

## Main-Force / Capital-Behavior Rules

Use "主力" language only as shorthand for observable capital behavior.

Allowed statements:

- "资金行为偏强，因为板块强于大盘、个股放量收高、回踩缩量。"
- "疑似诱多风险，因为放量冲高回落、尾盘走弱、社媒热度突然升温。"
- "无法判断主力意图，只能说当前证据不支持追高。"

Forbidden statements:

- "主力一定没走。"
- "主力要拉涨停。"
- "庄家在洗盘，所以可以扛。"
- "博主/群里说有资金，所以直接买。"

## Quant-Harvesting / Retail-Crowding Checks

Flag high risk when several appear together:

- Rapid intraday spike followed by upper wick or close away from high.
- Turnover jumps but price cannot hold a key level.
- Social media suddenly concentrates on one ticker after it already rallied.
- Small-cap or low-liquidity name with aggressive promotion.
- User wants to buy because of FOMO, not because a plan triggered.
- The stop-loss would be too far relative to allowed position size.

If high risk is flagged, default to `观察` or `不买`; if already held, suggest protecting profit or reducing risk according to plan.

## Output Format

Use this format for stock/fund research:

```text
【研究结论】
标的：
账户类型：
结论：
可行动作：
禁止动作：

【市场与主线】
市场状态：
行业主线：
是否属于主线：

【证据链】
事实：
推断：
缺失信息：

【资金行为与情绪】
资金行为：
散户情绪：
量化/收割风险：

【打分】
市场环境：
行业主线：
基本面/基金质量：
估值/安全边际：
资金行为：
情绪拥挤度：
交易计划：
总分：

【交易计划】
买入/加仓条件：
仓位上限：
止损/失效：
目标/复盘位：
什么情况说明我错了：
```

For urgent intraday questions, be shorter but still include conclusion, price condition, max size, stop/invalidating condition, and one sentence explaining the key evidence.

## Default Decision Language

Use only these final labels:

- `不买`
- `只观察`
- `可以按计划小仓测试`
- `可以按计划分批`
- `持有`
- `减仓/止盈`
- `风控退出`
- `回避`

Never use guaranteed-profit language.
