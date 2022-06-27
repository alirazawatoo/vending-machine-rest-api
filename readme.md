# Vending Machine REST API

A Rails API for authenticated buyers and sellers, product CRUD, coin deposits, purchases, change calculation, and deposit resets.

## Purchase flow

```text
buyer session -> deposit accepted coin values -> select product
              -> validate stock and balance -> vend -> return change -> reset deposit
```

Money values should be treated as integer minor units rather than floating point.

```bash
cp .env.sample .env
bundle install
bundle exec rails db:create db:migrate
foreman start
```

Swagger/rswag request specifications and Rails tests are included. Replace example tokens with locally issued credentials. Production use needs transaction/locking review for concurrent purchases, strict accepted-coin validation, idempotency, seller authorization, and consistent error responses.
