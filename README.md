# 🛡️ Secure P2P Crypto Escrow Telegram Bot

> **Note:** This is a **Showcase Repository**. The source code is kept private to protect the proprietary business logic and commercial value of the product. 

An enterprise-grade, production-ready Telegram Bot designed to facilitate secure, trustless peer-to-peer (P2P) crypto-to-fiat trading within communities. It acts as an automated, impartial escrow agent, ensuring 100% secure transactions for both buyers and sellers.

---

## 🎥 Project Demo

**[📺 Click Here to Watch the Full Demo Video on YouTube](https://youtu.be/9evaAvTL2No)**

---

## 🚀 Key Features

* **End-to-End Escrow Logic:** Robust Finite State Machine (FSM) that securely handles the exact sequence of a trade (Offer -> Escrow Lock -> Fiat Transfer -> Proof Upload -> Admin Release/Dispute).
* **Multi-Language Support (i18n):** Fully localized out-of-the-box (currently supporting English & Arabic) with dynamic language switching for each user.
* **Trader Reputation System:** Post-trade 5-star rating system. Ratings and total successful trades are dynamically displayed on public channel offers to build trust.
* **Immutable Audit Trail:** An internal database logging system that records every state transition, actor ID, and timestamp for admin dispute resolution.
* **Async Background Tasks:** Automated timeouts and auto-cancel features using `asyncio` loops. Stale or abandoned trades are automatically expired, releasing locked resources safely.
* **Dynamic Inline Pagination:** Clean UX for users to browse their active offers without spamming the chat history.
* **Channel Synchronization:** When an offer is deleted or a trade is completed, the bot automatically edits the original broadcasted message in the public channel with a `<s>strikethrough</s>` format and removes interaction buttons to prevent confusion.

---

## 💻 Technical Architecture & Stack

This bot was engineered with scalability, security, and asynchronous performance in mind.

* **Language:** Python 3.11+
* **Framework:** `aiogram 3.x` (Fully asynchronous Telegram Bot API framework)
* **Database & ORM:** `SQLAlchemy 2.0` (AsyncEngine) with SQLite (easily migratable to PostgreSQL for production scaling).
* **State Management:** Advanced FSM (Finite State Machine) using Aiogram's MemoryStorage (or Redis).
* **Concurrency:** Python native `asyncio` for non-blocking database queries, API calls, and background monitoring tasks.

---

## 🔄 The Trade Workflow

1. **Offer Creation:** Seller initiates a "Sell USDT" offer with dynamic limits and fiat payment methods.
2. **Admin Approval:** Offer is reviewed by an admin and broadcasted to the main public channel.
3. **Escrow Lock:** Buyer clicks "Start Buying". The bot prompts the seller to deposit USDT to a secure escrow wallet.
4. **Fiat Transfer:** Once escrow is confirmed, the buyer transfers fiat (e.g., Bank Transfer) to the seller's provided details and uploads a receipt.
5. **Release / Dispute:** Seller confirms receipt. Admin releases the USDT to the buyer's wallet. If a disagreement occurs, either party can open a Dispute, triggering the Audit Log for admin review.

---

## 👨‍💻 About the Developer

I am a **Software & Automation Engineer** specializing in bridging the gap between complex business workflows and seamless technological solutions. I build highly secure, scalable back-end architectures, AI integrations, and custom Telegram bots.

**Looking for a custom FinTech solution, Community Management bot, or Workflow Automation tool?** Let's build something great together.

* 💬 **Telegram:** [@MohALkher](https://t.me/MohALkher)
* 💼 **LinkedIn:** [Mohammed Al-Kheer](https://www.linkedin.com/in/mohammed-alkheer-eng/)
