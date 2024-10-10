# README
- API tutorial - https://www.youtube.com/watch?v=FJiIvFoxqsc 0:00 - 4:44
    - Streak (Stripe rival for payment processing)
- rails new streak --api
- set route in route.rb
    - resources :payments, only: :index --GET /payments
- rails g controller PaymentsController index
- payments_controller in index action
    - head :ok
- rails s
    - curl http://localhost:3000/payments -v

- 4:44 - 9:10
- rails g model Payment amount:decimal description:string
- rails c
- Payment.create!(description: 'Apple Macbook', amount: 1600)
- Payment.create!(description: 'Starbucks', amount:5)

- 9:10 - End
- updated routes
    - resources :payments, only: [:index, :create]
    - removed get 'payments/index'
- payments controller
    - create a payment, attempt to save the payment
    - 422 error thrown if payment cannot be created
- Within Postman
    - POST: http://localhost:3000/payments
    - Body > Raw += {"amount": 50,"description": "Hello youtube"}
