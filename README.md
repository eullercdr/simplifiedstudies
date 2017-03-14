# Dicas Laravel 

### Usando um fork pessoal, ao invés do repositório de origem

Assumindo um patch para corrigir um bug em um package, exemplo monolog.  

`{
    "repositories": [    
        {    
            "type": "vcs",    
            "url": "https://github.com/igorw/monolog"    
        }    
    ],    
    "require": {  
        "monolog/monolog": "dev-bugfix"  
    }  
}`  

### Corrigindo o problema mysql Laravel 5.4

`[Illuminate\Database\QueryException]
SQLSTATE[42000]: Syntax error or access violation: 1071 Specified key was too long; max key length is 767 bytes (SQL: alter table users add unique users_email_unique(email))`

Edite o AppService Provider e adicione  

`use Illuminate\Support\Facades\Schema;  

public function boot()  
{  
    Schema::defaultStringLength(191);  
}`    
