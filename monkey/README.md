# monkey

[![GoDoc](https://godoc.org/github.com/quii/mockingjay-server/monkey?status.svg)](https://godoc.org/github.com/quii/mockingjay-server/monkey)

Adds bad behaviour to a http.Handler from a YAML config. Useful for simulating those troublesome integration points 

````yaml
---
# Writes a different body 50% of the time
- body: "This is wrong :( "
  frequency: 0.5

# Delays initial writing of response by a second 20% of the time
- delay: 1000
  frequency: 0.2

# Returns a 404 30% of the time
- status: 404
  frequency: 0.3

# Write 10,000,000 garbage bytes 10% of the time
- garbage: 10000000
  frequency: 0.09
````