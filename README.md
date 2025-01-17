# Just some laravel notes for me

## Create products table
```
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
```
php artisan migrate
```

## If you need to rollback
```
php artisan migrate:rollback
```

## Create product controller
```
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
```
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
```laravel
@foreach($products as $product)
  <p>{{ $product->title }}</p>
@endforeach
```
