
New Laravel Api Project details:
Composer create-project Laravel/Laravel Api “9.*”
Changes in .env file for Db connections
Php artisan make:model Post -mcr


Php artisan migrate
Then goes to Post Model
Add $fillable
And then goes to api.php
Route::apiResource(‘posts’, PostController::class);
Now write logic inside controller
Php artisan make:factory Post –model=Post
Inside definition function and  return array:
    protected $model = Post::class;
    public function definition()
    {
        return [
            //
            'title' => $this->faker->sentence(),
            'content' => $this->faker->paragraph(),
            'status' => $this->faker->numberBetween(0,1),
        ];
    }

Php artisan make:seeder PostSeeder

Php artisan db:seed

Php artisan migrate –seed
OR
Php artisan db:seed --class=Database\Seeders\PostsTableSeeder

git config –list
ctrl+shift+esc
git init in a new project
