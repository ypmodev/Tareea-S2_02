# Sprint 2 - TypeScript Basics

Aquest projecte conté exercicis pràctics per aprendre els conceptes bàsics de TypeScript i els tipus de transformació. Els exercicis estan organitzats en dos fitxers de test principals.

## Requisits

- Node.js (v20 o superior)

## Instal·lació

1. Clona el repositori:

```bash
git clone <url-del-repositori>
cd it-sprint2-basics-ts
```

2. » Desconnecta el teu repositori del repositori de IT Academy. Utilitza la següent ordre de git:
```bash
git remote rm origin
```

3. Instal·la les dependències:

```bash
npm install
```

## Executar els Tests

Per executar tots els tests:

```bash
npm test
```

Per executar només la validació de tipus:

```bash
npm test:types
```

## Git Hooks amb Husky

Aquest projecte utilitza **Husky** per automatitzar la validació del codi abans de fer commits. Això garanteix que només es pugui fer commit de codi que passi tots els tests i validacions de TypeScript.

### Què fa Husky?

Quan intentes fer un commit (`git commit`), Husky executa automàticament:

1. `npm run test` - Executa tots els tests amb Vitest
2. `npm run test:types` - Valida els tipus amb el compilador de TypeScript

**Si qualsevol d'aquestes validacions falla, el commit es cancel·larà** fins que resolvis els errors. Això ajuda a mantenir la qualitat del codi i evita commits amb errors.

### Consell

Abans de fer commit, pots executar manualment les comandes per assegurar-te que tot està correcte:

```bash
npm test
npm run test:types
```

## Exercicis

### Basics Refactor (`basics-refactor.test.ts`)

Aquest fitxer conté 18 reptes que cobreixen els conceptes fonamentals de TypeScript:

#### Repte 1: Migració des de JavaScript

Llegeix l'article ["Migrating from JavaScript" a la documentació de TypeScript](https://www.typescriptlang.org/docs/handbook/migrating-from-javascript.html) i troba com solucionar errors de TypeScript bàsics.

#### Repte 2: Objectes com a paràmetres

Descobreix com tipar params com un objecte amb una clau `first` que sigui un nombre i una clau `second` que també sigui un nombre.

#### Repte 3: Propietats opcionals en objectes

Has d'esbrinar com tipar l'objecte perquè `last` sigui opcional.

#### Repte 4: Paràmetres opcionals

Has d'esbrinar com marcar el paràmetre `last` com a opcional.

#### Repte 5: Assignació de tipus a variables

Consulta la [documentació de TypeScript](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html) i determina com canviar `defaultUser` perquè el test passi.

#### Repte 6: Unions

Actualitza la interfície User per restringir la propietat `role` a una de les opcions establertes: 'admin', 'user' o 'super-admin'.

#### Repte 7: Arrays

Has de solucionar aquest error de tipus esbrinant com representar arrays.

#### Repte 8: Anotacions de tipus de retorn de funció

Anota la funció `makeUser` perquè sempre retorni un `User`.

#### Repte 9: Promeses

Has d'esbrinar com actualitzar l'anotació del tipus de retorn perquè TypeScript estigui satisfet.

#### Repte 10: Set

Actualitza `guitarists` perquè estigui tipat com un Set de strings.

#### Repte 11: Record

Consulta la documentació de TypeScript i esbrina què pot estar causant aquest problema. Actualitza `cache` perquè estigui tipat correctament i els errors desapareguin.

#### Repte 12: Filtratge amb typeof

Escriu la funció perquè els tests passin.

#### Repte 13: Blocs catch

Has de convertir el tipus 'unknown' en un tipus on sàpigues què és. Hi ha diverses maneres de resoldre aquest repte!

#### Repte 14: Herència amb extends

Aquí, la propietat `id` es comparteix entre les tres interfícies. Pots trobar una manera de refactoritzar això per fer-ho més DRY?

#### Repte 15: Intersecció de tipus

Actualitza el tipus de retorn de la funció perquè sigui 'User i { posts: Post[] }'.

#### Repte 16: Omit i Pick

Com creem un nou tipus d'objecte amb NOMÉS les propietats `firstName` i `lastName` de User? Llegeix la documentació de TypeScript sobre Utility Types.

#### Repte 17: Tipus de funció

La funció 'onFocusChange' és actualment 'unknown'. Visita la documentació de TypeScript i esbrina el tipus apropiat per la funció.

#### Repte 18: Tipus de funció amb promeses

Tipa les funcions perquè els errors desapareguin. Consulta la sintaxi de tipatge de funcions i Promise.

### Transformation Types (`transformation-types.test.ts`)

Aquest fitxer conté 13 reptes sobre tipus de transformació i conceptes avançats:

#### Repte 1: ReturnType

Llegeix la documentació de TypeScript sobre Utility Types i esbrina com utilitzar `ReturnType` per extreure el tipus de retorn de `myFunc`. Pista: pots utilitzar `typeof` per obtenir el tipus d'una variable o funció.

#### Repte 2: Parameters

Utilitza `Parameters` per obtenir el tipus dels paràmetres de la funció `makeQuery`.

#### Repte 3: ReturnType amb funcions asíncrones

Utilitza `ReturnType` per obtenir el tipus de retorn de `getUser`.

#### Repte 4: Claus d'un objecte

Obté les claus d'un objecte com a tipus d'unió.

#### Repte 5: Indexed access amb objectes

Utilitza indexed access types per obtenir el tipus d'una propietat concreta d'un objecte.

#### Repte 6: Indexed access amb unions

Utilitza indexed access types per obtenir el tipus d'una propietat concreta d'una unió d'objectes.

#### Repte 7: Tipus dels valors d'un array

Utilitza indexed access types i unions per obtenir el tipus dels valors d'un array.

#### Repte 8: Tipus dels valors amb as const

Utilitza indexed access types per obtenir el tipus dels valors d'un objecte amb `as const`.

#### Repte 9: Terminologia de tipus

Dona un exemple de terminologia: union, discriminated union i enum.

#### Repte 10: Extract d'una discriminated union

Extreu un tipus d'un element concret d'una discriminated union.

#### Repte 11: Exclude d'una discriminated union

Exclou un tipus concret d'una discriminated union.

#### Repte 12: Tipus del discriminador

Extreu el tipus del discriminador d'una discriminated union.

#### Repte 13: Tipus a partir d'un array

Utilitza l'array per resoldre els dos tipus:

- `AppleOrBanana`, que ha de ser una unió dels dos primers valors de l'array ("apple" | "banana").
- `Fruit`, que ha de ser una unió de tots els valors de l'array ("apple" | "banana" | "orange").

Llegeix la secció sobre Indexed Access Types de la documentació de TypeScript. Pista: pots utilitzar l'operador `typeof` per obtenir el tipus de l'array i després accedir als seus valors amb l'índex `[number]` o amb una tupla d'índexs específics.

## Com treballar amb els exercicis

**Important**: Descomenta els reptes **d'un en un** per resoldre'ls progressivament.

1. Obre el fitxer de test corresponent (`basics-refactor.test.ts` o `transformation-types.test.ts`)
2. Descomenta **només** el bloc de codi del primer repte que vols resoldre
3. Resol l'exercici seguint les instruccions del comentari
4. Executa `npm test` per verificar que la solució és correcta
5. Un cop completat i verificat, torna a comentar el repte resolt i descomenta el següent
6. Repeteix el procés amb cada repte

> **Nota**: Si descomentes tots els reptes alhora, els errors es poden acumular i dificultar la identificació del problema específic de cada exercici.

## Recursos

- [Documentació oficial de TypeScript](https://www.typescriptlang.org/docs/)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [Utility Types](https://www.typescriptlang.org/docs/handbook/utility-types.html)
- [Indexed Access Types](https://www.typescriptlang.org/docs/handbook/2/indexed-access-types.html)

## Llicència

GPL-3.0
