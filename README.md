# siege-engine
A general basic Python-powered SYN flooder bot.

Installation and operation
==========================

Just type:

```bash
pip install siege-engine
python -m siege_engine 300 tass.com
```

Note that a helpful error message will be displayed if you just type:

```bash
python -m siege_engine
```

Please set the 300 value regarding your network conditions. This is the amount of threads
that will be spawned. Obviously, more is better (I bet your network could hold about 2000
of them).

Note that increasing thread count about 100% CPU usage is pointless, because of the GIL.
You can, altogether, fire up multiple instances :D 

Just note that GIL is not a practical limit, I've tested it on my PC with 15k threads and it ate
only 23% of the CPU, so it's more academic concern.

Note that if zero connections were made, that means the target server is no longer responding,
which is a good thing.

# Change log

* v2.0: Better messages
* v1.9: added a total counter for wasted bytes
* v1.8: fixed problems with termination
* v1.7: Removed scapy
* v1.6: Added scapy
* v1.5: SSL socket will be picked upon now
* v1.4: fixed a critical bug
* v1.3: significantly refactored the code
* v1.2: since v1.1 we're been hosted on PyPI, removed these nasty entry points
* v1.1: added graceful support for time-out sessions

## How to adjust thread count.

Start from 13000. The startup time for 25000 threads is pretty rough, but overall the app manages to start.
If the process manages to hit a single core 100%, start a new program, or just reduce 
the amount of threads. The process is network-bound.

## Valid targets

* tass.com
* kremlin.ru
* eng.putin.kremlin.ru
* eng.constitution.kremlin.ru
* eng.flag.kremlin.ru
* lenta.ru
* government.ru
* rt.com

If you have any better ideas, PRs are welcome!