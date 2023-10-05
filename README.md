import requests
from bs4 import BeautifulSoup

class CurrencyConverter:
    def __init__(self, exchange_rate):
        self.exchange_rate = exchange_rate

    def convert_to_usd(self, amount):
        usd_amount = amount / self.exchange_rate
        return usd_amount

def main():
   
    url = 'URL_НАЦІОНАЛЬНОГО_БАНКУ_ВАШОЇ_КРАЇНИ'
    response = requests.get(url)
    soup = BeautifulSoup(response.text, 'html.parser')
    # Знаходження курсу долара США на сторінці
    exchange_rate = YOUR_CODE_TO_FIND_EXCHANGE_RATE

    converter = CurrencyConverter(exchange_rate)

   
    amount = float(input("Введіть суму валюти вашої країни: "))

   
    usd_amount = converter.convert_to_usd(amount)
    print(f"{amount} {YOUR_CURRENCY} = {usd_amount:.2f} USD")

if __name__ == "__main__":
    main()
