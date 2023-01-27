import json
from openpyxl import Workbook
from whoisapi import *

client = Client(api_key= "at_EIwpZw1XClvblOu94jPgobc9Hj1x4")
params = RequestParameters(ignore_raw_texts=1, da=2)
whois = client.data("whoisxmlapi.com", params)
client.parameters.output_format = "json"
iplist = []

ips = open("Python/ips.txt")
for i in ips:
    iplist.append(i.strip("\n"))

for i in range(0,len(iplist)):
    try:
        raw_data = client.raw_data(iplist[i])
        json_obj = json.loads(raw_data)
        whois_json = json_obj["WhoisRecord"]
        domain_name= whois_json["domainName"]
        path_absolute = pathlib.Path().absolute()
        registrar_name = whois_json["registrarName"]

    for i in ips:
        ips.append(i.strip)
        
