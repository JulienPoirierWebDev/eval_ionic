# Evaluation

Cette évaluation se compose d'une app Ionic composé de plusieurs pages et consommant deux api disctinctes. Il n'y a pas de cohérence entre les deux parties de l'app, il s'agit simplement d'un exercice de mise en pratique.

La première api est `https://tyradex.vercel.app/`, une API sur POKEMON : - `https://tyradex.vercel.app/api/v1/pokemon` pour la liste des pokemons - `https://tyradex.vercel.app/api/v1/pokemon/:id` pour un pokemon en particulier
La seconde api est `http://movies-api.julienpoirier-webdev.com/`, une API sur les films et les series : - `http://movies-api.julienpoirier-webdev.com/api/movies` pour les films - `http://movies-api.julienpoirier-webdev.com/infos/movies/:id` pour un film en particulier - `http://movies-api.julienpoirier-webdev.com/api/series` pour les series - `http://movies-api.julienpoirier-webdev.com/infos/series/:id` pour une serie en particulier

## Workflow

Vous allez travailler a 2 ou 3, il faut donc être organisé. Celui qui a créer le projet doit donner les autorisations aux autres pour qu'ils puissent eux aussi écrire dessus.

![Voici où ajouter des collaborateurs](image.png)

Une fois le nom d'utilisateur de vos camarades ajouté, ils recevront un mail et devront accepter l'invitation.

Vous pouvez travailler a 3 sur le même écran en partage sur TEAMS ou bien vous répartir le travail et chacun créer une branche sur GITHUB pour votre travail. Si vous faites des branches, pensez a bien faire des pull requests. Si vous travaillez a 3 sur MAIN, vous risquez d'avoir des conflicts.

## Etape 1

Créer une application IONIC avec les commandes habituelles. Choisissez le template TABS qui vous fournira un menu tout fait.
Créer un repository github et sauvegarder votre travail dessus.

## Etape 2

Créer une page qui affiche la liste des pokemons. Vous devrez consommer l'api `https://tyradex.vercel.app/pokemon` pour afficher les pokemons. Vous pouvez afficher les pokemons sous forme de liste ou de carte, c'est vous qui voyez.

Cette page sera le premier onglet de votre application.

Affichez au minimum le nom et l'image du pokemon.

Pour vous aider, voici le type de données que vous pouvez récupérer :

```tsx
type Pokemon = {
	pokedex_id: number;
	generation: number;
	category: string;
	name: {
		fr: string;
		en: string;
		jp: string;
	};
	sprites: {
		regular: string;
		shiny: string;
		gmax: string | null;
	};
	types: {
		name: string;
		image: string;
	}[];
	talents: {
		name: string;
		tc: boolean;
	}[];
	stats: {
		hp: number;
		atk: number;
		def: number;
		spe_atk: number;
		spe_def: number;
		vit: number;
	};
	resistances: {
		name: string;
		multiplier: number;
	}[];
	evolution: {
		pre:
			| {
					pokedex_id: number;
					name: string;
					condition: string;
			  }[]
			| null;
		next:
			| {
					pokedex_id: number;
					name: string;
					condition: string;
			  }[]
			| null;
		mega:
			| {
					orbe: string;
					sprites: {
						regular: string;
						shiny: string;
					};
			  }[]
			| null;
	};
	height: string;
	weight: string;
	egg_groups: string[];
	sexe: {
		male: number;
		female: number;
	};
	catch_rate: number;
	level_100: number;
	formes: any;
};
```

Idéalement, vous devriez afficher :

-   Le nom du pokemon
-   L'image du pokemon
-   Les types du pokemon
-   Les résistances du pokemon (optionnel)
-   L'évolution du pokemon (optionnel)
-   La taille du pokemon (optionnel)
-   Le poids du pokemon (optionnel)

Bonus :

-   Ajouter un selecteur de type.
-   Ajouter un champ de recherche pour filtrer les pokemons par nom.

## Etape 3

Créer une page qui affiche les détails d'un pokemon. Vous devrez consommer l'api `https://tyradex.vercel.app/v1/pokemon/` pour afficher les détails du pokemon. Vous pouvez afficher les détails sous forme de liste ou de carte, c'est vous qui voyez.

Bonus :

-   Permettre d'arriver sur la page de détails d'un pokemon en cliquant sur un pokemon de la liste.
-   Ajouter un bouton pour revenir à la liste des pokemons.
-   Ajouter des boutons pour naviguer entre les pokemons (précédent et suivant).

## Etape 4

Créer une page qui affiche la liste des films. Vous devrez consommer l'api `http://movies-api.julienpoirier-webdev.com/api/movies` pour afficher les films. Vous pouvez afficher les films sous forme de liste ou de carte, c'est vous qui voyez.

Cette page sera le second onglet de votre application.

Affichez au minimum le titre et l'image du film.

Bonus : - Ajouter les 100 premiers characters du synopsis
# eval_ionic
