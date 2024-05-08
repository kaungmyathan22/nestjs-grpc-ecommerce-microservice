## Register
```bash
$ curl -X POST http://localhost:3000/auth/register -H "Content-Type: application/json" -d '{"email": "elon@gmail.com", "password": "12345678"}'
```

## Login
```bash
$ curl -X PUT http://localhost:3000/auth/login -H "Content-Type: application/json" -d '{"email": "elon@gmail.com", "password": "12345678"}'
```

## Create Product
```bash
curl -X POST http://localhost:3000/product -H "Content-Type: application/json" -d '{"name": "Test A", "sku": "A00001", "price": 100, "stock": 5}'
```

## Create Order
```bash
curl -X POST http://localhost:3000/order -H "Content-Type: application/json" -d '{"productId": 1, "quantity": 1}'
```