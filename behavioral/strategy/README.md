# Strategy Design Pattern

## Definition

Imagine you’re ordering a pizza 🍕 — you have different ways to pay:

- Cash 💵
- Credit Card 💳
- PayPal 🏦

Each method achieves the same result (payment) but works differently.

Similarly, the **Strategy Pattern**:

- Defines a family of algorithms.
- Encapsulates each algorithm.
- Makes them interchangeable.
- Allows algorithms to vary independently from clients that use them.

> **Goal**: Choose an algorithm at runtime without changing the main program.

## Structure

  <img src="images/strategy_structure.png" alt="Strategy Pattern Structure" width="600">

**Main Components**:

- **Context** — Maintains a reference to a Strategy object.
- **Strategy Interface** — Common interface for all strategies.
- **Concrete Strategies** — Implement different variations of the algorithm.

## Key Characteristics

- **Encapsulation of Behavior**  
  ➔ Each behavior (algorithm) is in its own class.  
  ➔ Easy modification without affecting others.

- **Interchangeability**  
  ➔ Strategies follow the same interface.  
  ➔ Easy swapping at runtime.

- **Decoupling**  
  ➔ Context doesn’t implement the algorithms directly.  
  ➔ Reduces dependencies.

- **Open/Closed Principle**  
  ➔ Open for extension, closed for modification.  
  ➔ Add new strategies without altering existing code.

## When to Use?

✅ **Dynamic Algorithm Switching**  

- Ex: Google Maps switching between Shortest, Fastest, Scenic routes.

✅ **Separation of Business Logic**  

- Ex: WinRAR supporting multiple compression formats (ZIP, RAR, GZIP).

✅ **Reduced Class Duplication**  

- Ex: Amazon Payment Gateway handling multiple payment methods.

✅ **Removing Complex Conditional Statements**  

- Ex: Loan interest calculations based on loan type.

## When NOT to Use?

❌ **Behavior Variations Are Rare**  

- If only 2–3 strategies exist, might be overkill.

❌ **Performance Overhead Concerns**  

- Introduces additional objects and dynamic method calls.

❌ **Client Should Not Manage Strategy**  

- If client shouldn’t handle strategy selection.

❌ **Behavior Tightly Coupled with Context**  

- Encapsulating strategy may break encapsulation.

❌ **Concrete Strategies Share Too Much Code**  

- Might lead to duplication instead of reuse.

## Code Example

```python
from abc import ABC, abstractmethod

# Strategy Interface
class PaymentStrategy(ABC):
    @abstractmethod
    def pay(self, amount):
        pass

# Concrete Strategies
class CreditCardPayment(PaymentStrategy):
    def pay(self, amount):
        print(f"Paid ${amount} using Credit Card.")

class PayPalPayment(PaymentStrategy):
    def pay(self, amount):
        print(f"Paid ${amount} using PayPal.")

# Context
class ShoppingCart:
    def __init__(self, payment_strategy: PaymentStrategy):
        self.payment_strategy = payment_strategy

    def checkout(self, amount):
        self.payment_strategy.pay(amount)

# Usage
cart1 = ShoppingCart(CreditCardPayment())
cart1.checkout(100)

cart2 = ShoppingCart(PayPalPayment())
cart2.checkout(200)
```

## Real-World Examples

| Scenario | Interface | Strategies | Context |
|:---------|:----------|:-----------|:--------|
| **Payment Methods in E-commerce** | `PaymentStrategy` | `CreditCardPayment`, `PayPalPayment` | `ShoppingCart` |
| **Route Calculation in Maps** | `RouteStrategy` | `CarRoute`, `BikeRoute`, `WalkingRoute` | `NavigationSystem` |
| **Email Sorting in Gmail** | `EmailSortingStrategy` | `PrimaryInbox`, `PromotionsInbox`, `SpamFilter` | `EmailClient` |
| **Image Filters in Instagram/Photoshop** | `ImageFilter` | `BlackAndWhiteFilter`, `SepiaFilter`, `BlurFilter` | `PhotoEditor` |
| **Video Playback Quality (YouTube/Netflix)** | `VideoQualityStrategy` | `AutoQuality`, `HDQuality`, `UltraHDQuality` | `VideoPlayer` |
| **Difficulty Modes in Games** | `DifficultyStrategy` | `EasyMode`, `NormalMode`, `HardMode`, `ExpertMode` | `GameEngine` |
| **Text-to-Speech Engines** | `VoiceStrategy` | `MaleVoice`, `FemaleVoice`, `AIEnhancedVoice` | `TextToSpeechEngine` |
| **Auto Text Formatting in Word Processors** | `TextFormatStrategy` | `BoldFormat`, `ItalicFormat`, `UnderlineFormat` | `WordProcessor` |
