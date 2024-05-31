NUC Accreditation is a document management system for accreditation. Developed to streamline the the accreditation process of Trans-National Educational Institutes.

The system features:

1. User Account Management
2. Management of Accreditation Instrument for each program
3. Management of Task force Members
4. Management of Documents
5. Notification
6. In-app chat
7. Accreditaion Survey

## Installation

1. Clone the directory
2. Navigate to the project directory
3. Run composer install ( make sure to have composer installed on your computer )
4. npm install
5. php artisan migrate ( after running this command, type yes to create the database)
6. php artisan seed

## Usage

1. php artisan serve
2. php artisan websockets:serve
3. npm run dev
4. create a .env file and copy the contents from .env.example

For user access you can navigate to database > seeders > UserSeeder.php
