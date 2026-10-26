# Mijn Weekmenu — MVP

Nederlandstalige mealplanner met React, Vite en TypeScript. Werkt zonder API-sleutel, account of externe database.

## Starten

Vereist: Node.js 20.19+ of 22+.

```bash
npm install
npm run dev
```

Open de URL die Vite in de terminal toont (meestal http://localhost:5173).

Productiebuild:

```bash
npm run build
npm run preview
```

## Op GitHub zetten

Maak een lege repository en voer in deze projectmap uit:

```bash
git init
git add .
git commit -m "Eerste versie mealplanner"
git branch -M main
git remote add origin https://github.com/JOUW-GEBRUIKERSNAAM/mijn-weekmenu.git
git push -u origin main
```

GitHub host broncode; voor een publiek bereikbare website gebruik je bijvoorbeeld Vercel of Netlify (build `npm run build`, output `dist`).

## Wat werkt

- Onboarding en voorkeuren in localStorage
- 16 voorbeeldrecepten, zoeken, toevoegen en bewerken
- Weekmenu genereren met personen, budgetindicatie, dagenaantal, dieetfilter, maximaal herhalen, niet-kookdagen en ingrediënten die op moeten
- Mobiele swipe-navigatie en weekoverzicht
- Receptwaardering en alternatieven
- Boodschappenlijst met geschaalde en opgetelde hoeveelheden, categorieën, basisvoorraad en afvinken
- Weekmenuhistorie en JSON-back-up

## Bekende beperkingen

- Geen accounts of synchronisatie tussen apparaten; browsergegevens kunnen gewist worden.
- Budget is een richtbedrag, geen harde optimalisatie. Prijzen zijn grove handmatige receptschattingen; geen live Nederlandse supermarktdata. Herhaalde maaltijden tellen één keer in de receptkosten, maar de boodschappenlijst telt alle porties op. Controleer dit bij mealprep.
- Geen vaste quota per categorie, uiterste houdbaarheidsdag voor op-te-maken ingrediënten of daadwerkelijke planning van voorbereiden; voorkeuren werken als filters/score.
- Geen tekst-, link- of foto-import, geen AI-module en geen echte reviewtekst in deze MVP.
- Afbeeldingen worden extern geladen vanaf Unsplash en zijn illustratief, niet altijd een exacte foto van het gerecht.
- Het toevoegen van recepten gebruikt een eenvoudig tekstformaat: `hoeveelheid; eenheid; naam; categorie`.

## Later uitbreiden

1. Supabase Auth, Postgres en Storage met gebruikers-/huishoudenscheiding en RLS.
2. Verplaats opslag naar repository-interfaces (RecipeRepository, PlanRepository, UserPreferencesRepository).
3. Maak een server-side AI-gateway (Supabase Edge Function) met provideradapters voor OpenAI, Anthropic of Hugging Face. Bewaar sleutels uitsluitend als server-side secrets. Valideer modeloutput met een schema voordat recepten opgeslagen worden.
4. Voeg echte budgetoptimalisatie, portieplanning, bewaartermijnen, categorieverhoudingen en ingredientnormalisatie toe.
5. Maak delen met vrienden via uitnodigingen en rollen in een huishouden.

**Veiligheid:** zet nooit een API-key in `VITE_*`-variabelen; die worden in de frontend ingebouwd.
