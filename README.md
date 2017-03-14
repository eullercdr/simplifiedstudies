# Dicas Laravel 

### Usando o fork ao invés do Repositório de origem

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
