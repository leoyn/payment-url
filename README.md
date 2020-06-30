
```
 /$$$$$$$                                                         /$$           /$$   /$$ /$$$$$$$  /$$      
| $$__  $$                                                       | $$          | $$  | $$| $$__  $$| $$      
| $$  \ $$ /$$$$$$  /$$   /$$ /$$$$$$/$$$$   /$$$$$$  /$$$$$$$  /$$$$$$        | $$  | $$| $$  \ $$| $$      
| $$$$$$$/|____  $$| $$  | $$| $$_  $$_  $$ /$$__  $$| $$__  $$|_  $$_/        | $$  | $$| $$$$$$$/| $$      
| $$____/  /$$$$$$$| $$  | $$| $$ \ $$ \ $$| $$$$$$$$| $$  \ $$  | $$          | $$  | $$| $$__  $$| $$      
| $$      /$$__  $$| $$  | $$| $$ | $$ | $$| $$_____/| $$  | $$  | $$ /$$      | $$  | $$| $$  \ $$| $$      
| $$     |  $$$$$$$|  $$$$$$$| $$ | $$ | $$|  $$$$$$$| $$  | $$  |  $$$$/      |  $$$$$$/| $$  | $$| $$$$$$$$
|__/      \_______/ \____  $$|__/ |__/ |__/ \_______/|__/  |__/   \___/         \______/ |__/  |__/|________/
                    /$$  | $$                                                                                
                   |  $$$$$$/                                                                                
                    \______/                                                                                 
```

This is just a concept and rather a RFC which needs more work.

# Table of contents

1. Why?
2. How?
3. Possible use cases

## Why?

We can sum up the advantages in three points:
* Fewer errors compared to manually typing IBAN.
* You can place them everywhere you want
  * Websites
  * QR-Codes
  * Using link shorteners
* Easier, since banking apps or browsers might recognize them and redirect the users to the banking site rather than typing them in manually.

## How?

Payment URLs will look like this.

`payment://identifier@service/type?options`

* `identifier`: can be things like IBAN or other means such as email addresses which are used by paypal.
* `service`: can be a specific service provided by a compny or a general service like a bank
  * General purpose services: `bank`, `bitcoin` (TODO)
* `type`: specifies what should be done. `transaction` might be one thing. This is mainly reserved for future use.
* `options`: defines options like amount of money to be sent, currency and name of recipient. Options are seperated by a `&` sign.

## Use case

Person B wants to pay his bill. Person A provides the QR Code which includes the payment URL as plain text. Person A and B will transfer money by bank. So the included payment URL looks like this:

`payment://DE123456789012345678@bank/transfer?name=Person%20A&currency=EUR`

Keep in mind that bank is not the name of the bank but rather tells the applications which handles that this payment will be made by a bank transfer. All bank transfers have `bank` as `service` no matter which bank a persons has their bank account.
