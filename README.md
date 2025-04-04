# Laravel Queue and Redis Setup

Follow these steps to set up and test Redis queues in your Laravel project.

## Steps to Run the Project

### 1. Set Environment Variables
Update your `.env` file with the following values:
```env
QUEUE_CONNECTION=redis
CACHE_DRIVER=redis
SESSION_DRIVER=redis
REDIS_HOST=127.0.0.1
REDIS_PORT=6379
```

### 2. Install Dependencies
Run the following command to install required dependencies:
```sh
composer install
```

### 4. Start Redis Server
Ensure Redis is running by executing:
```sh
redis-server
```

### 5. Verify Redis Connection in Tinker
```sh
php artisan tinker
use Illuminate\Support\Facades\Redis;
Redis::set('test-key', 'Redis is working!');
Redis::get('test-key');
```

### 6. Dispatch a Test Job
```sh
php artisan queue:work --queue=redis
```
