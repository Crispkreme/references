## SETUP FOR FILAMENT PROJECTS
Installing the laravel and filaments
Terminal: `Ubuntu`  
Command:  
```sh
    composer create-project laravel/laravel example-app
    composer require filament/filament:"^3.2" -W
    php artisan filament:install --panels
    php artisan migrate
```

## CREATING THE FILAMENT USER
Terminal: `Ubuntu`  
Command:  
```sh
    php artisan make:filament-user

    Name: Admin Account #your input
    Email: admin@admin.com #your input
    Password: yourpassword #your input
```

## CLEARING THE FILAMENT CACHE
Terminal: `Ubuntu`  
Command:  
```sh
    php artisan filament:optimize-clear
```

## BASIC CRUD IN FILAMENT
Terminal: `Ubuntu`  
Command:  
```sh
    php artisan make:mode YourModel -m # CREATING THE YOUR-MODEL AND YOUR-MIGRATION
    php artisan make:filament-resource YOUR-MODEL # CREATING FILAMENT RESOURCES
```

## UPDATING THE SIDEBAR ICON
Steps
- go to the app/filament/resources/UserResources.php 
- update the protected static ?string $navigationIcon = 'heroicon-o-users'; 
- icon url https://heroicons.com/
- save

## UPDATING FORMS
Steps
- go to the app/filament/resources/UserResources.php 
- look for public static function form(Form $form): Form
- update the return $form->schema([ // ]);
- save

## ONE TO ONE RELATIONSHIP
Steps
go to the model first the add relationship function 
  
Command:  
```php
    // like this
    public function usertype() {
        return $this->belongsTo(UserType::class);
    }
```
then edit the your resources file in this location 
app/filament/resources/UserResources.php 

Command:  
```php
    // like this
    return $form
    ->schema([
        Select::make('usertype')
            ->label('Owner Type')
            ->relationship(
                'category',  # model relations
                'name'       # data from table column then it also display the data into the select/dropdown
            )
            ->searchable()
            ->required(),
    ]);
```

when showing the relationship data into the table

Command:  
```php
    // like this
    public static function table(Table $table): Table
    {
        return $table
            ->columns([
                TextColumn::make('room.room_number')->label('Room'),
            ]);
    }
```

other way is to user relationship manager

Terminal: `Ubuntu`  
Command:  
```sh
    php artisan make:filament-relation-manager ReadingResource rooms room_number

    # ReadingResource is the name of the resource class for the owner (parent) model.
    # rooms is the name of the relationship you want to manage.
    # room_number is the name of the attribute that will be used to identify posts.
```

after you execute this command you must register this into the ReadingResource
go to the resources folder
Command:  
```php
    // edit this parts
    public static function getRelations(): array
    {
        return [
            RoomsRelationManager::class
        ];
    }
```