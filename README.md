# Using php dotenv in PHP

To use `phpdotenv`, follow these steps:

1. **Create Library folder
    ```
    mkdir -p library/dotenv
    ```
    
2. **Install the package** via Composer:
   ```
   composer require vlucas/phpdotenv
   ```

3. **Create a `.env` file** in your project's root directory and add the environment variables you want:
   ```
   APP_NAME=MyApp
   DB_HOST=localhost
   DB_USERNAME=root
   DB_PASSWORD=password
   ```

4. **Load the `.env` file** in your PHP script:
   ```
   <?php
   require_once __DIR__ . '/vendor/autoload.php';

   // Initialize Dotenv and load variables
   Dotenv\Dotenv::createImmutable(__DIR__)->load();

   // Access variables
   echo getenv('APP_NAME');
   echo getenv('DB_HOST');

    // OR
   echo $_ENV['APP_NAME'];

    // OR
    echo $_SERVER['APP_NAME'];
   ```

5. **Access the environment variables** using `getenv()`:
   ```
   $appName = getenv('APP_NAME');
   echo $appName;  // Outputs 'MyApp'
   //or
    echo $_ENV['APP_NAME'];
   //or
    echo $_SERVER['APP_NAME'];
   ```
