# flowbook

A limit order book and agent-based market simulation library in Go.

flowbook provides a price-time priority matching engine and a continuous-time
simulation loop for driving heterogeneous trading agents against it. It is
intended for market microstructure research, strategy prototyping, and
generating synthetic order flow.

## Features

- Limit order book with FIFO price levels and O(log n) best-price lookup
- Matching engine for market, limit, cancel and replace actions
- Continuous-time (Gillespie) simulation with a pluggable agent interface
- Deterministic runs from a seed
- Integer prices and quantities throughout; no floating point in the book
- Standard library only

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
