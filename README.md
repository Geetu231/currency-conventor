# currency-conventor

# Predefined exchange rates (example: base is USD)
exchange_rates = {
    'USD': 1.0,
    'EUR': 0.93,
    'INR': 83.5,
    'GBP': 0.80,
    'JPY': 154.2,
    'CAD': 1.37
}

def convert_currency(amount, from_currency, to_currency):
    from_currency = from_currency.upper()
    to_currency = to_currency.upper()

    if from_currency not in exchange_rates or to_currency not in exchange_rates:
        print("Currency not supported.")
        return

    # Convert to USD first, then to target currency
    usd_amount = amount / exchange_rates[from_currency]
    converted_amount = usd_amount * exchange_rates[to_currency]

    print(f"{amount} {from_currency} = {converted_amount:.2f} {to_currency}")

# Example usage
try:
    amount = float(input("Enter the amount: "))
    from_currency = input("From currency (e.g., USD): ")
    to_currency = input("To currency (e.g., INR): ")
    convert_currency(amount, from_currency, to_currency)
except ValueError:
    print("Please enter a valid number.")

