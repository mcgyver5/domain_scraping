# domain_scraping

script to digest a list of domains  (in example.com format) and check if it is responding, if it has a redirect and if it is parked

pseudocode:
for each domain in text file, 
add "https://www." to front of domain
use python library to issue a GET request

if error (such as timeout), make note of that

if response is 200, check for a javascript redirect in content of page
  if yes:  make note of redirect
  if no:   look for keywords associated with parked domains

if response is 301 or 302, make note of redirect location

do another pass on redirected locations and check if those are parked 

print results out to text file
