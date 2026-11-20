# gatewayd quote service

A small Express REST service skeleton for building payment quotes for a Ripple gateway. The npm package name is `quotes-service` (version 0.0.0).

> **Status: abandoned sketch, dormant since 2014.** Two commits on 2014-12-20, part of Steven Zeiler's Ripple Labs era work on gateways and bridge payments. It is an unfinished skeleton: the quote logic is stubbed. It has not been run as part of this documentation pass. See [docs/STATUS.md](docs/STATUS.md).

## Install

    git clone https://github.com/stevenzeiler/gatewayd-quote-service
    cd gatewayd-quote-service
    npm install

The package is not published to npm.

## Usage

    npm start        # builds with gulp, then runs the built service

The service listens on port 5100 unless `PORT` is set. Routes:

    GET /v1/quotes
    GET /v1/quotes/:destination_address/:destination_amount
    GET /v1/quotes/:destination_address/:destination_amount/:source_address
    GET /v1/quotes/:destination_address/:destination_amount/:source_address/:source_amount

`destination_amount` is written as `amount+currency`, for example `10+USD`. `GET /v1/quotes` returns a description of the three quote URL shapes.

## Config

- `PORT`: port to listen on (default 5100).
- The gateway domain is hard-coded in `src/index.js` as the sample value `america-bank-a.gatewayd.org`.

## How it works

- `src/index.js` builds an Express app, wires the routes to a `Controller`, and starts it when run directly. It can also be exported as a plugin for another Express app.
- `src/controller.js` splits the destination amount, then says whether the destination address contains the configured domain (`local`) or not (`federated`).
- `gulpfile.js` transpiles `src/` to `build/` with `gulp-6to5` (an early Babel).

## Status

Skeleton only: no real quotes are computed, and the quote responses are incomplete. See [docs/STATUS.md](docs/STATUS.md).

## License

ISC. See [LICENSE](LICENSE).
