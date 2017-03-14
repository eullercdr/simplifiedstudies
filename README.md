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
