## Récupérer la précédente URL

```php
<? php

class MyController {

	function movieDetail(RequestStack $requestStack): Response
	{
		// Récuperer l'URL de départ dans php vanilla
		previousUrl = $_SERVER['HTTP_REFERER']
	
		// la même chose sous Symfony
		$previousUrl2 = $requestStack
		->getCurrentRequest()
		->server
		->get('HTTP_REFERER');
	}
}

```

```twig
{#Nom de la route de la page en cours# }
{# ex. : app_home #}
{{app.request.get('_route')}}
{# On peut stocker cette info dans une variable Twig #}
{% set route = app.request.get('_route') %}
<a href="..." class="nav-link" {{ route = 'app_home' ? 'active'}}">Home</a>
```
	