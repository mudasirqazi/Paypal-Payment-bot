# PayPal Payment Bot

## Purpose
Telegram bot for processing PayPal subscription payments with multiple pricing tiers, user management, and automated subscription handling through PayPal REST SDK integration.

## Flow
1. User starts bot and gets registered in database
2. User selects /buy command to view subscription plans
3. Choose from available pricing tiers ($10-$50)
4. Confirm payment amount and proceed to PayPal
5. Bot creates PayPal payment and provides approval URL
6. User completes payment through PayPal interface
7. Bot verifies payment and activates subscription
8. Access to premium content through /news command

## Structure
```
paypal_payment_bot/
├── main2.py                          # Bot entry point and polling setup
├── paypal_record.db                  # SQLite database file
├── Credentials_Secrets.zip           # Encrypted credentials storage
├── callbacks/
│   └── Call_Backs.py                 # Main command and callback handlers
├── callback_factories/
│   ├── callback_plan_factory.py      # Plan selection callback factory
│   └── confirmation_factory.py       # Payment confirmation factory
├── database/
│   ├── model.py                      # SQLAlchemy database models
│   └── db_operations.py              # Database CRUD operations
├── keyboards/
│   └── keyboard.py                   # Inline keyboard generators
├── Messages/
│   └── message.py                    # Message text templates
└── paypal_integration/
    ├── paypal_setup.py               # PayPal REST SDK configuration
    └── paypal_sandbox_setup.py       # Sandbox environment setup
```

## Language
Python

## Tools
- **aiogram** - Telegram Bot API framework
- **paypalrestsdk** - PayPal REST API integration
- **SQLAlchemy** - Database ORM
- **requests** - HTTP requests for payment verification
