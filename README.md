# 🏆 MIDAS Trading Bot

**Machine Intelligence for Dynamic Asset Signals**

An advanced ML-powered trading bot for XAUUSD (Gold) with real-time signal generation and Discord notifications.

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![ML](https://img.shields.io/badge/ML-scikit--learn-orange?logo=scikit-learn)
![Discord](https://img.shields.io/badge/Notifications-Discord-5865F2?logo=discord)

---

## ✨ Features

### 🤖 Machine Learning
- **162 Technical Features** - RSI, MACD, Ichimoku, ADX, Fibonacci, divergences, and more
- **Multiple Models** - Random Forest (92.7%), Logistic Regression, Gradient Boosting, XGBoost
- **Ensemble Predictions** - Combines models for higher accuracy
- **LSTM/GRU Support** - Deep learning for time-series (PyTorch)

### 📊 Trading Styles
| Style | Timeframe | Target | Max Hold |
|-------|-----------|--------|----------|
| Scalping | 5m | 0.1% | 1 hour |
| Intraday | 15m | 0.3% | 6 hours |
| Swing | 1h | 0.5% | 3 days |
| Position | 4h | 1.0% | 1 week |

### 🔔 Notifications
- **Discord Webhooks** - Rich embeds with entry, SL, TP
- **Telegram Support** - Trade alerts and daily summaries

### 📈 Analysis
- **Multi-Timeframe** - HTF bias confirmation
- **Session Filters** - London, New York, Tokyo sessions
- **News Filters** - Avoid high-impact events
- **Advanced Indicators** - Ichimoku, ADX, CCI, Fibonacci, Divergences

---

## 🚀 Quick Start

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Configure Environment
```bash
cp .env.example .env
# Edit .env with your credentials
```

### 3. Train Models
```bash
python src/ml/train.py -t 1h
```

### 4. Generate Signals
```python
from strategy.styled_signal_generator import StyledSignalGenerator

gen = StyledSignalGenerator('swing', 'data', 'models')
signal = gen.generate_signal()
print(f"{signal.direction} | Confidence: {signal.confidence:.0%}")
```

---

## 📁 Project Structure

```
midas-trading-bot/
├── config/              # Configuration (Pydantic)
├── data/                # Historical XAUUSD data (Kaggle)
├── models/              # Trained ML models
├── src/
│   ├── ml/              # Machine Learning
│   │   ├── train.py            # Model training
│   │   ├── feature_engineering.py
│   │   ├── advanced_indicators.py
│   │   └── signal_generator.py
│   ├── strategy/        # Trading Strategies
│   │   ├── trading_styles.py
│   │   └── styled_signal_generator.py
│   ├── notifications/   # Discord & Telegram
│   ├── backtesting/     # Backtest engine
│   └── analysis/        # Technical analysis
└── requirements.txt
```

---

## ⚙️ Configuration

Edit `.env`:
```env
# Discord
DISCORD_WEBHOOK_URL=https://muiga01.github.io

# Trading
MIN_CONFIDENCE=0.8
SYMBOL=XAUUSD
TIMEFRAME=H1

# MT5 (optional)
MT5_LOGIN=
MT5_PASSWORD=
MT5_SERVER=
```

---

## 📊 Model Performance

| Model | Accuracy | F1 Score |
|-------|----------|----------|
| Random Forest | **92.7%** | 93.9% |
| Logistic Regression | 83.0% | 88.6% |
| Gradient Boosting | 61.5% | 74.1% |

Trained on 124,000+ hourly bars (2004-2024).

---

## 🛠️ Development

Built with ❤️ using:
- **Python 3.10+**
- **scikit-learn** - ML models
- **PyTorch** - Deep learning
- **pandas** - Data manipulation
- **Discord Webhook** - Notifications

---

## 📜 License

MIT License - See [LICENSE](LICENSE) for details.

---

## 👤 Contact
For questions, issues, or feature requests:
- Open a GitHub issue
- Discord: Add your bot to get started!

---

*MIDAS - Turning data into gold* 🥇
