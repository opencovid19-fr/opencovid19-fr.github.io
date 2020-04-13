# Data Against Covid-19 website

Data against Covid est une organisation informelle issue de la société civile avec des développeurs, des data scientist, des ingénieurs, des chefs de projets et talents de tous corps de métiers qui s'organisent ensemble pour fournir des données consolidées sur l'épidémie de covid 19 et proposer des outils de visualisation et de prédiction.

Téléchargez la présentation de l'initiative et de ses projets [`Data_Against_Covid19.pdf`](https://drive.google.com/file/d/11enKiBPKxGW4b0eLi_IlN68MbXGdk7nc/view).

## Comment

## Ajouter un nouveau projet

Prenons l'exemple d'ajouter un projet nommé `FOOBAR`:

### 1. Créer une catégorie correspondant au nouveau projet dans `_data/category_list.yml` (ne pas mettre de )
	
	projet-foobar:
	  name: Le Projet Foobar
	  description: une description courtedu projet Foobar (optionnel)
		  
NB: ne pas mettre de '_' dans le nom de la catégorie ajoutée.
	
	  
### 2. Créer un article en [markdown](https://wprock.fr/blog/markdown-syntaxe/) selon le modèle suivant et complété de façon ad hoc
		
	---
	layout: post
	title: "Le projet Foobar"
	date: 1970-01-01 08:44:38 -0400 
	category: projet-foobar
	author: Liste des autours
	short-description: Description courte du projet
	---
	
	-----
	
	# Headliner du projet Foobar en texte libre
	
	**Product Owner** : Liste des responsables de projets		
	**Objectif** : Description du projet Foobar en texte libre plus long.s
	
	**Livrable** : [nom du site web](https://<url du site web>)
	
	**Organisation du projet :**
	- Canaux slack :
	    - canal du projet sur le slack de data againt covid19
	
	**Outils utilisés :**
	- Liste des briques techniques utilisées

- Enregistrer cet article dans `_post/foobar/1970-01-01-foobar.md` par exemple.
- S'assurer que dans le `category`qui se trouve dans le header du post markdown est celui créé dans le fichier `category_list.yml` juste avant.

	
### 3. Ajouter une landing page

- A la racine du repo, créer un fichier `projet-foobar.html` correspondant au nom de la catégorie crée ci-avant.
- Il y a deux cas:
	- Il y a de multiples posts dans cette catégorie alors le fichier aura la structure suivante:

			---
			layout: category
			category: projet-foobar
			title: Le projet Foobar
			---
			
			
			{% for post in site.categories.projet-foobar %}
			  {% include article-card.html %}
			{% endfor %}

		
	- Il n'y a qu'un post:

			---
			layout: category
			category: projet-foobar
			title: Le projet Foobar
			---
			
			
			
			<meta http-equiv="refresh" content="0; URL={{ site.url }}{{ site.baseurl }}/projet-foobar/foobar" />
				
### 4. Pousser les fichiers sur le site pour qu'il soit construit sur Github Pages

				
	


