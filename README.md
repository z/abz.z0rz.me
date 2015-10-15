abz.z0rz.me
===========

An experiment in domain name length limitations, the alphabet and mathematical sequences.

http://abz.z0rz.me will expand to a longer URL with an exponential distribution of characters.

The domain is created to reach the maximum number of allowed characters (253) with an exponential curve in the length of the letters as you proceed through the alphabet. The formula used is "1 + 62 * (10/7)^(x-26)". It's colorful because I like colors and wanted to do a progressive "rainbow" animation in CSS3. The z.me domain contains the maximum, 63 characters.

These are some bash snippets I used to generate the URL and the contents:

`seq 26 | awk 'BEGIN { printf "http://" }; { n = int(1 + 62 * (10/7)^($1-26)); c = sprintf("%c",0x61 + $1-1); for(i=1;i<=n;i++) printf c; printf "."; }; END { printf "me\n"; }'`

`seq 26 | awk 'BEGIN { printf "<h1>" }; { printf "<i>"; n = int(1 + 62 * (10/7)^($1-26)); c = sprintf("%c",0x61 + $1-1); printf n c; printf "</i> "; }; END { printf "</h1>"; }'`
