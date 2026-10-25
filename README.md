# esp-witness

Public anchor for the dreamballz ESP event chain.

`tips.jsonl` holds one line per change: the chain tip, its length, and the digest of every
event hash up to it. Each line is committed when the tip moves.

Verify any published tip against the live chain:

```
curl -s https://dreamballz.com/api/esp/export | node esp/witness.mjs --file /dev/stdin
```

A tip published here cannot be backdated: the commit timestamp belongs to GitHub, not to the box.
