# Credit-Card-Management-System  
A console-based C++ application that simulates a complete **Credit Card Management System**. It allows users to apply for credit cards, perform transactions securely, earn rewards, pay dues, and maintain credit history with **robust exception handling**.  

---

## 🚀 Features  
- Apply for different credit card types (**Silver, Gold, Platinum**) based on credit score.  
- Generate and update secure **4-digit PINs**.  
- Make payments with **PIN verification**.  
- Track **transaction history** and outstanding balances.  
- Earn **reward points** on spending.  
- Pay dues and maintain card health.  
- View detailed card information including **CVV, expiry date, and spending limit**.  
- Built using **Object-Oriented Programming** with **runtime polymorphism**.  
- Includes **robust exception handling** with custom exceptions.  

---

## 💻 Technologies Used  
- **C++**  
- **OOP (Object-Oriented Programming)**  
- **STL (Standard Template Library)**  
- **Exception Handling**  
- **Random Number & Time Generation** (for card numbers and expiry dates)  

---

## 🛡️ Custom Exceptions  

| Exception Class            | Purpose |
|-----------------------------|---------|
| `INVALID_PIN`               | Invalid PIN format |
| `INCORRECT_PIN_ERROR`       | Wrong PIN entered |
| `INSUFFICIENT_BALANCE`      | Spend limit exceeded |
| `NO_CARD`                   | Card operations attempted without a card |
| `INELIGIBLE_LIMIT_INCREMENT`| Limit increase attempted without eligibility |
| `DUE_PENDING`               | Card surrender attempted with pending dues |
| `INVALID_INPUT`             | General invalid input |
| `PIN_NOT_GENERATED_ERROR`   | PIN operation attempted before PIN generation |

---

## 💳 Class Overview  

### 🔹 `CreditCard` (Base Class)  
- Generates **random card numbers and CVV**.  
- Handles methods:  
  - `generatePIN()`  
  - `changePIN()`  
  - `Statement()`  
  - `cardDetails()`  
- Manages: **PIN, CVV, Spend Limit, Reward Points, Expiry Date, Transaction History**.  

### 🔹 Derived Classes  
| Class          | Spend Limit | Reward Multiplier |
|----------------|-------------|-------------------|
| `SilverCard`   | ₹20,000     | 1% |
| `GoldCard`     | ₹50,000     | 2% |
| `PlatinumCard` | ₹1,00,000   | 5% |

### 🔹 `CardHolder`  
Stores personal info and manages all cards.  
- Key Methods:  
  - `applyCreditCard()`  
  - `pay(receiver, amount, currentUser)`  
  - `duePayment(amount)`  
  - `displayCards()`  
  - `dropCard(index)`  

---

## ⏩ Flow of Execution  
1. **Apply Card** → Credit score checked, appropriate card issued.  
2. **Generate PIN** → Secure 4-digit PIN setup.  
3. **Make Payments** → PIN validated, spend limit checked.  
4. **View Transactions** → Detailed statement of credit activity.  
5. **Pay Dues** → Settle outstanding balances.  
6. **Display Cards** → View all cards and details.  

---

## 🎯 Sample Use Case  

```cpp
CardHolder user("Raghavendra", "Karnataka", "raghavendrasadare@gmail.com", "9380616288", 900);

user.applyCreditCard();               // Issues Platinum Card  
user.pay("Amazon", 3000.0, &user);    // Makes a secure transaction  
user.duePayment(3000.0);              // Pays due amount  
user.displayCards();                  // View all cards and details  
