# Extract credentials from TRENDnet routers

TRENDnet routers such as the TEW-732BR save their configuration backups (config_rt) as base-64 encoded strings rather than ASCII. Usernames and passwords are otherwise plaintext - this allowed me to find my forgotten PPPoE credentials.

Just run with the config_rt (or other saved config file) as a parameter, e.g.  go run b64cfgdmp.go config_rt > readable.txt

With a TEW-72BR there are two lines of header to identify the product and version then many lines of the form

{key}<bold>=</bold>{value length}<bold>-</bold>{value}
