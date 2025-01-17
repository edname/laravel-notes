# Just some laravel notes for me

[Create product](#create-product).
[Laravel Breeze](#laravel-breeze).


# Create product
## Create products table
```bash
php artisan make:migration create_productss_table
```

## Add required fields to generated migration file
```
$table->string('name'); 
```
```
$table->text('text');
```

## Do migration
```bash
php artisan migrate
```

## If you need to rollback
```bash
php artisan migrate:rollback
```

## Create product controller
```bash
php artisan make:controller ProductController
```
Lets edit ProductController
Add name space on top
```
use App\Models\Product;
```
Retrieve all product and assign to variable
```
$products = Product::all();
```
return view with assigned variable
```
return view('product', compact('products')); 
```

## Create product model
```bash
php artisan make:model Product
```
Edit Models/Post.php
```
use Illuminate\Database\Eloquent\Factories\HasFactory;
```
```
    use HasFactory;
```
```
    protected $table = 'products';
```


## Let's create view product.blade.php
After that lets add foreach of our products
```
@foreach($products as $product)
  <p>{{ $product->title }}</p>
@endforeach
```

# Laravel Breeze

## Add Login/Register with Laravel Breeze to new/existing project

```bash
composer require laravel/breeze
```
```bash
php artisan breeze:install
```
