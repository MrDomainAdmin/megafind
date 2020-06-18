[Usage]
./megafind domain.tld

**Recommend running in a screen or TMUX

Description:
This tool will grep for [domain.tld] in popular password dumps such as LinkedIn and Collections1-5. The paths in this script will need to be altered to ensure it is reading files from the correct directories. It will do all files from each collection in parallel.

Output:
[domain.tld].txt - sorted, unique, lowercase email addresses that match the domain provided.

Search Formats:

.txt
grep -r --no-filename "$domain" "$file"   > tmp/$(basename "$file").txt &

.zip
find /data/password_dumps/collection1/*/*.zip -type f -exec zipgrep $domain {} \; &


.tar.gz
zgrep -a "$domain" "$file"  > tmp/$(basename "$file").txt &