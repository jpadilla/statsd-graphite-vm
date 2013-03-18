# Vagrant VM for StatsD + Graphite

Vagrant VM for StatsD and Graphite with the help of [@hectcastro's](https://github.com/hectcastro/) graphite, statsd, and node.js cookbooks.

## To get started
You need to have Vagrant installed.

	$ librarian-chef install
	$ vagrant up
	$ vagrant ssh

## Graphite
	$ open http://localhost:8080
Graphite's credentials default to username `root` and password `root`.

## StatsD with Python

```python
from statsd import StatsClient
statsd = StatsClient()
statsd.incr('foo')
```