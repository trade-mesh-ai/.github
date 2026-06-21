# ⚡ trade-mesh-ai

> Algorithmic trading infrastructure for Indian markets — built on Java, Spring Boot, and AI.

---

## 🎯 What We Build

**trade-mesh-ai** is an open ecosystem of algorithmic trading tools, strategies, and intelligence services for retail traders in India. Our platform targets NIFTY and BankNIFTY options on NSE, powered by real-time market intelligence, pluggable strategies, and AI-assisted decision making.

We believe retail traders deserve institutional-grade tools — built with transparency, extensibility, and smart risk management at the core.

---

## 🧠 Core Philosophy

```
❌  Don't predict market direction
✅  Understand market conditions

❌  Run one strategy blindly
✅  Let market intelligence select the right strategy

❌  Manual trading with emotions
✅  Rule-based automation with strict risk controls

❌  Hold overnight and hope
✅  Defined risk, defined exit, always
```

---

## 🏗️ Platform Architecture

```
                    ┌─────────────────────────┐
                    │   Zerodha Kite Connect   │
                    │  WebSocket + REST API    │
                    └────────────┬────────────┘
                                 ↓
                    ┌─────────────────────────┐
                    │  Market Intelligence    │
                    │  VIX · OI · Max Pain    │
                    │  PCR · Greeks · Events  │
                    └────────────┬────────────┘
                                 ↓
                    ┌─────────────────────────┐
                    │   Strategy Selector     │
                    │  Condition → Strategy   │
                    └────────────┬────────────┘
                                 ↓
          ┌──────────────────────┼──────────────────────┐
          ↓                      ↓                      ↓
  ┌───────────────┐    ┌───────────────┐    ┌───────────────┐
  │ Expiry Day    │    │ Theta Spread  │    │ Bull Put      │
  │ Selling       │    │ Strategy      │    │ Spread        │
  └───────────────┘    └───────────────┘    └───────────────┘
                                 ↓
                    ┌─────────────────────────┐
                    │    Risk Management      │
                    │  Position · Stop Loss   │
                    │  Margin · Weekly Limit  │
                    └────────────┬────────────┘
                                 ↓
                    ┌─────────────────────────┐
                    │   Order Execution       │
                    │  Paper · Live · Track   │
                    └─────────────────────────┘
```

---

## 📁 Repositories

| Repository | Description | Status |
|---|---|---|
| [trade-mesh-ai](https://github.com/trade-mesh/trade-mesh-ai) | Core monolithic trading platform | 🚧 Active |
| [trade-mesh-intelligence](https://github.com/trade-mesh/trade-mesh-intelligence) | Market intelligence library | 🔜 Coming |
| [trade-mesh-backtest](https://github.com/trade-mesh/trade-mesh-backtest) | Historical strategy backtesting engine | 🔜 Coming |
| [trade-mesh-dashboard](https://github.com/trade-mesh/trade-mesh-dashboard) | React trading dashboard | 🔜 Coming |
| [trade-mesh-docs](https://github.com/trade-mesh/trade-mesh-docs) | Documentation and guides | 🔜 Coming |

---

## 🧩 Core Features

### 📡 Market Intelligence Layer
Runs continuously — calculates everything once, shared across all strategies:
- **VIX Monitor** — Volatility regime detection
- **OI Analyser** — Institutional call/put wall detection
- **Max Pain Calculator** — Weekly expiry price prediction
- **PCR Tracker** — Put call ratio sentiment
- **Greeks Engine** — Delta, Theta, Vega, Gamma in real time
- **Event Calendar** — Auto skip RBI, Fed, Budget days

### 🎯 Pluggable Strategy Engine
Add new strategies without touching core logic:
```java
@Component
public class MyStrategy implements TradingStrategy {
    public boolean isApplicable(MarketCondition condition) { ... }
    public Mono<TradeSignal> execute(MarketIntelligence intel) { ... }
}
```

### 🛡️ Risk Management
- Position sizing based on capital and volatility
- Stop loss enforced automatically
- Weekly loss limit — auto pause on breach
- Margin checker before every order
- Paper trading mode — test without real money

### 🤖 AI Layer (Coming Phase 3)
- Claude AI integration for market analysis
- Pre-trade risk assessment
- Strategy recommendation based on conditions
- Natural language trade explanations

---

## 🔌 Broker Support

| Broker | Status | Type |
|---|---|---|
| Zerodha Kite Connect | ✅ Phase 1 | Primary |
| Upstox Pro API | 🔜 Phase 3 | Secondary |
| Angel One SmartAPI | 🔜 Phase 4 | Tertiary |
| Paper Trading | ✅ Built-in | Simulation |

Adding a new broker:
```java
@Service
public class UpstoxAdapter implements BrokerAdapter {
    // implement interface — plugs in automatically
}
```

---

## 📊 Market Streams Roadmap

| Stream | Status |
|---|---|
| NIFTY Options | ✅ Phase 1 |
| BankNIFTY Options | ✅ Phase 1 |
| NIFTY Futures | 🔜 Phase 2 |
| Cash / Equity | 🔜 Phase 3 |
| Crypto | 🔜 Future |

---

## 🛠️ Tech Stack

```
Language     →  Java 21 (Virtual Threads)
Framework    →  Spring Boot 3.3
Reactive     →  Spring WebFlux
Build        →  Gradle (Kotlin DSL)
Database     →  SQLite → PostgreSQL
Cache        →  Redis (Lettuce reactive)
Messaging    →  Apache Kafka (Phase 2)
AI           →  Anthropic Claude API
Alerts       →  Telegram Bot
Containers   →  Docker → Kubernetes (Phase 5)
```

---

## 📅 Roadmap

```
2025 Q3  ✅  Project foundation
             Zerodha auth + KiteTicker
             Market Intelligence Layer
             Paper trading engine
             Expiry Day strategy

2025 Q4  🚧  Live trading — Zerodha
             Risk engine
             Multiple strategies
             Telegram alerts

2026 Q1  🔜  AI integration — Claude
             Options strategy expansion
             Backtest engine
             Second broker — Upstox

2026 Q2  🔜  SaaS / Rental platform
             Multi-tenant architecture
             Stripe billing
             Strategy marketplace

2026 Q3+ 🔜  Scale and expand
             Kubernetes
             Global markets
             AutoML optimizer
```

---

## 💰 SaaS Vision

trade-mesh-ai is not just a personal trading tool — it is a **rental platform** for retail algo traders in India.

| Plan | Price | Features |
|---|---|---|
| Starter | ₹999/month | 1 strategy · Paper trading · Basic alerts |
| Pro | ₹2,999/month | All strategies · Live trading · AI signals · Risk engine |
| Elite | ₹7,999/month | Custom strategies · White label · Priority support |

> Own broker credentials, own capital, own risk — we provide the intelligence and automation.

---

## 🤝 Contributing

We welcome contributions from algo traders, quant developers, and Java engineers.

```
1. Fork the repository
2. Create feature branch
3. Implement TradingStrategy or BrokerAdapter interface
4. Write unit tests
5. Submit pull request
```

Read our [Contributing Guide](CONTRIBUTING.md) before submitting.

---

## ⚠️ Disclaimer

All tools in this organization are for **educational and personal use only**. Algorithmic trading involves significant financial risk. Past strategy performance does not guarantee future results. Always paper trade before going live. The maintainers are not responsible for any financial losses incurred through use of this software.

---

## 👤 Maintainer

**Kuldeep Singh**  
Associate Principal Engineer · LTIMindtree · Noida, India  
13+ years Java · Spring Boot · Kafka · Microservices · Fintech

[![GitHub](https://img.shields.io/badge/GitHub-kuldeepsingh123-181717?style=flat&logo=github)](https://github.com/kuldeepsingh123)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-kuldeepsingh--engineer-0A66C2?style=flat&logo=linkedin)](https://linkedin.com/in/kuldeepsingh-engineer)
[![Org](https://img.shields.io/badge/Org-microminds--ai-6366f1?style=flat&logo=github)](https://github.com/microminds-ai)

---

<div align="center">

**⚡ trade-mesh-ai — Where market intelligence meets algorithmic precision**

*Built with ☕ Java · ⚡ Spring WebFlux · 🧠 Claude AI · 📈 Zerodha Kite*

</div>
