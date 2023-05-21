Table 1: SALES.STG.SALES_DETAILS (Stores SALES information)

This table contains the personal information of SALESs who have made purchases on the platform.

SALES_ID: Number (38,0) [Primary Key, Not Null] - Unique identifier for SALESs
FIRST_NAME: Varchar (255) - First name of the SALES
LAST_NAME: Varchar (255) - Last name of the SALES
EMAIL: Varchar (255) - Email address of the SALES
PHONE: Varchar (20) - Phone number of the SALES
ADDRESS: Varchar (255) - Physical address of the SALES
Table 2: SALES.STG.ORDER_DETAILS (Stores order information)

This table contains information about orders placed by SALESs, including the date and total amount of each order.

ORDER_ID: Number (38,0) [Primary Key, Not Null] - Unique identifier for orders
SALES_ID: Number (38,0) [Foreign Key - SALES_DETAILS(SALES_ID)] - SALES who made the order
ORDER_DATE: Date - Date when the order was made
TOTAL_AMOUNT: Number (10,2) - Total amount of the order
Table 3: SALES.STG.PAYMENTS (Stores payment information)

This table contains information about payments made by SALESs for their orders, including the date and amount of each payment.

PAYMENT_ID: Number (38,0) [Primary Key, Not Null] - Unique identifier for payments
ORDER_ID: Number (38,0) [Foreign Key - ORDER_DETAILS(ORDER_ID)] - Associated order for the payment
PAYMENT_DATE: Date - Date when the payment was made
AMOUNT: Number (10,2) - Amount of the payment
Table 4: SALES.STG.PRODUCTS (Stores product information)

This table contains information about the products available for purchase on the platform, including their name, category, and price.

PRODUCT_ID: Number (38,0) [Primary Key, Not Null] - Unique identifier for products
PRODUCT_NAME: Varchar (255) - Name of the product
CATEGORY: Varchar (255) - Category of the product
PRICE: Number (10,2) - Price of the product
Table 5: SALES.STG.TRANSACTIONS (Stores transaction information)

This table contains information about individual transactions that occur when SALESs purchase products, including the associated order, product, quantity, and price.

TRANSACTION_ID: Number (38,0) [Primary Key, Not Null] - Unique identifier for transactions
ORDER_ID: Number (38,0) [Foreign Key - ORDER_DETAILS(ORDER_ID)] - Associated order for the transaction
PRODUCT_ID: Number (38,0) - Product involved in the transaction
QUANTITY: Number (38,0) - Quantity of the product in the transaction
PRICE: Number (10,2) - Price of the product in the transaction