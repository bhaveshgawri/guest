#!/usr/bin/python
import argparse
from selenium import webdriver
from selenium.webdriver.common.keys import Keys

parser = argparse.ArgumentParser(description=
								"""Open [proxysite.com] 
								or [images.google.com].
								<-Opens google.com by 
								default-> Use only one
								argument.""")
parser.add_argument('-p', action='store_true',
					dest='proxy',
					help='Open with proxysite.com')
				
parser.add_argument('-i', action='store_true',
					dest='images',
					help='Open with images.google.com')

results = parser.parse_args()
driver = webdriver.Chrome()
	
if results.images and results.proxy:
	driver.get("https://www.google.com")
elif results.images:
	driver.get("https://www.images.google.com")
elif results.proxy:
	driver.get("https://www.proxysite.com/")
else:
	driver.get("https://www.google.com")
