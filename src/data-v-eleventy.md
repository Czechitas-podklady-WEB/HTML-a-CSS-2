---
layout: base
title: Data v Eleventy
---

## Front Matter

V ukázce níže ukládáme do proměnné `nadpis` hodnotu `Kontakt` a do `adresa` `Václavské náměstí 11`. Tyto proměnné jsou dostupné jen na dané stránce.

```liquid
{% raw %}---
layout: zakladni
nadpis: Kontakt
adresa: Václavské náměstí 11
---{% endraw %}
```

## Výpis

Hodnoty proměnných vypisujeme pomocí `{% raw %}{{ nazev_promenne }}{% endraw %}`.

```liquid
<h1>{% raw %}{{ nadpis }}{% endraw %}</h1>
<address>{% raw %}{{ adresa }}{% endraw %}</address>
```

## Společná data pro více stránek

Data v souborech ve složce `src/data/` ve formátu `.json` můžeme vypisovat na všech stránkách.

### `src/data/pobocky.json`

```json
[
	{
		"nazev": "Praha",
		"adresa": "Václavské náměstí 837/11"
	},
	{
		"nazev": "Brno",
		"adresa": "Škrobárenská 511/3"
	},
	{
		"nazev": "České Budějovice",
		"adresa": "Lipová 1789/9"
	}
]
```

Názvy hodnot a textové hodnoty musí být obalené ve dvojitých uvozovkách `"…"`.

Hranaté závorky `[…]` značí kolekci více položek.

Složené závorky `{…}` obalují podrobnosti položky.

Všechna data v souboru `pobocky.json` jsou k dispozici za tečkou `{% raw %}{{ pobocky.* }}{% endraw %}`.

## Výpis kolekce

V JSON ukázce výše máme kolekci. Pro výpis všech položek za sebou použijeme smyčku `for`.

```liquid
{% raw %}<h1>Pobočky</h1>
{% for pobocka in pobocky %}
	<section>
		<h2>{{ pobocka.nazev }}</h2>
		<address>{{ pobocka.adresa }}</address>
	</section>
{% endfor %}{% endraw %}
```

## Více stránek podle jedné šablony

Kolekci můžeme využit pro vytvoření několika stránek podle jedné šablony. Vytvoříme novou stránku, třeba `pobocka.njk`, které do Front Matter dáme následující:

```liquid
{% raw %}---
layout: zakladni
pagination:
  data: pobocky
  size: 1
  alias: pobocka
permalink: '/pobocka/{{ pobocka.nazev | slug }}/'
---

<h1>{{ pobocka.nazev }}</h1>
<address>{{ pobocka.adresa }}</address>{% endraw %}
```

Eleventy pro každou pobočku vytvoří vlastní HTML soubor.

Pokud bychom na jednotlivé stránky chtěli odkazovat, použijeme formát ze sekce `permalink`.

```liquid
{% raw %}<a href="/pobocka/{{ pobocka.nazev | slug }}/">{{ pobocka.nazev }}</a>{% endraw %}
```

## Úkol na teď

Postupuj podle zadání na [github.com/…/Cviceni-Eleventy-galerie](https://github.com/Czechitas-podklady-WEB/Cviceni-Eleventy-galerie).
