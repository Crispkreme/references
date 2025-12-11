https://srmklive.github.io/laravel-paypal/docs.html

- go here create an account https://developer.paypal.com/home/
- paste this credentials to your .env file
Terminal: `Ubuntu`  
Command:  
```sh
    # paste to .env file
    # PAYPAL INTEGRATION
    CLIENT_ID = AaYrFvIhpUDoSsCb_ZQSpaZTXP6FYpZwfFNN93sNaKz6P0DGqXnTnbIbM3zT-6KJHH9BFl1w9e8-HBmt
    CLIENT_SECRET_KEY = EMKSrlVouK02tlG2bmGTz2ouU2zwD-TulgQy-BJM6cdCadZJHtnnZ4UaGbQcjJfUhF1cZ-fpxsyRaHiS
    PAYPAL_CURRENCY = USD

    # SANDBOX ACCOUNTS
    URL = https://sandbox.paypal.com
    SANDBOX_EMAIL = sb-xuvab33263525@business.example.com
    SANDBOX_PASSWORD = !>#RCwZ9
```
- create a model and migration
Terminal: `Ubuntu`  
Command:  
```sh
    # commands
    php artisan make:model Payment -m

    # schema
    # payment migration files
    public function up(): void
    {
        Schema::create('payment', function (Blueprint $table) {
            $table->id();
            $table->string('payment_id');
            $table->string('payer_id');
            $table->string('payer_email');
            $table->float('amount', 10, 2);
            $table->string('currency');
            $table->string('payment_status');
            $table->timestamps();
        });
    } 

    # models   
```