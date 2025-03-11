
sublist3r -d example.com -o results.txt
amass enum -passive -d example.com -o results.txt

cat domains.txt | httpx -sc -title -server -screenshot -o results.txt
screen shots 
