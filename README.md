# flowbook

An embeddable order book and agent-based market simulation engine in Go.

flowbook models a single instrument on a single venue: a central limit order
book and the agents that trade on it. It ships with a matching engine, a
continuous-time simulation loop, and a set of ready-made agents, so you can
build an exchange simulator with a few lines of Go and then customise the
scenario, the agents, or the market rules.

It is built for teaching and learning how markets work: order priority,
spreads, market impact, market making, and how different kinds of participants
shape price. The default agent mix is calibrated so that an out-of-the-box run
reproduces the well-known stylised facts of real markets: fat-tailed returns,
volatility clustering, absence of return autocorrelation, and realistic
spread and order-flow distributions.

**It is not a backtesting framework for retail or HFT trading, nor does it aim
to be.**

## Roadmap

- [ ] `orderbook`: orders rest, match and cancel with price-time priority
- [ ] `matcher`: order actions produce correct execution reports
- [ ] `sim`: agents act in continuous time through a pluggable interface
- [ ] `agent`: ready-made participants covering the main types found in real
      markets
- [ ] `stylised`: metrics for the stylised facts, and a default scenario that
      passes them
- [ ] `calibrate`: tunes agent parameters to hit a chosen set of target
      statistics
- [ ] `portfolio`: agents hold positions, and orders are checked against them
      before reaching the book
- [ ] `replay`: any run can be reproduced exactly from its seed
- [ ] `cmd/flowbook`: runs launch from the command line and export data for
      analysis
- [ ] `stream`: external clients observe the market and submit orders over the
      network

## Status

Early development. The API is not yet stable.

## Development

```
make fmt    # gofumpt
make lint   # vet, staticcheck, revive
make test   # go test -race -cover
make bench  # benchmarks, output in bench.txt
```

Requires Go 1.25 or later.

## License

MIT
