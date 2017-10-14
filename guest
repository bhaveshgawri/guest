#!/usr/bin/python
import argparse
from selenium import webdriver

class Parser():
	def __init__(self):
		self.parser = argparse.ArgumentParser(description=
										"""Open [proxysite.com],
										[youtube.com],
										[facebook.com] 
										or [images.google.com].
										<<<Opens google.com by 
										default>>>.""")
		self.results = None
		self.to_open = []
		self.driver = None
		self.DEFAULT_URL = "https://google.com"
		self.add_arguments()
		self.find_results()
		self.find_input_argument_count()
		
	def add_arguments(self):
		"""
		To add new arguments insert the websites here
		Note: Keep the `dest` argument in `add_argument`
			  function same as the name of the website.
			  Exp: for www.facebook.com use `dest` = 'facebook'
		"""
				
		self.parser.add_argument('-i', action='store_true',
								dest='images.google',
								help='Open with images.google.com')

		self.parser.add_argument('-y', action='store_true',
								dest='youtube',
								help='Open with youtube.com')

		self.parser.add_argument('-f', action='store_true',
								dest='facebook',
								help='Open with facebook.com')
		
		self.parser.add_argument('-p', action='store_true',
								dest='proxysite',
								help='Open with proxysite.com')
		
	def find_results(self):
		"""
		Get all the possible arguments
		
		"""
		self.results = self.parser.parse_args()
	
	def find_input_argument_count(self):
		"""
		Filter inputs inputted on the terminal
		
		"""
		for result in self.results.__dict__:
			if self.results.__dict__[result] == True:
				self.to_open.append(result)
	
	def open_links(self):
		"""
		Open the websites taken as argument by the user
		Open the first link directly from webdriver and
		rest(if there) by javascript's window.open method
		
		"""
		self.driver = webdriver.Chrome()
		if len(self.to_open) == 0:
			try:
				self.driver.get(self.DEFAULT_URL)	
			except:
				print("Unable to open website(s)")
		
		_ = 0
		first_link = ""	
		for website in self.to_open:
			link = "https://www." + website + ".com"
			if _ == 0:
				first_link = website
				try:
					self.driver.get(link)	
				except:
					print("Unable to open website(s)")
					break
				_ = 1
			else:
				if link != first_link:
					try:
						self.driver.execute_script('''
							window.open("{}","_blank");
							'''.format(link))
					except:
						print("Unable to open: "+link)
	
	def get_results(self):
		return self.results
	
	def get_input_argument_names(self):
		return self.to_open

if __name__ == '__main__':
	p = Parser()
	p.open_links()
