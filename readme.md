# Guide: Sette opp og bruke løsningen

---

## Innhold

1. [Sette opp løsningen: Fork, GitHub Pages og GitHub Actions](#sette-opp-løsningen-fork-github-pages-og-github-actions)
   1. [Lage en fork av repoet](#1️⃣-lage-en-fork-av-repoet)
   2. [Sett GitHub Pages til å basere seg på "GitHub Actions"](#2️⃣-sett-github-pages-til-å-basere-seg-på-github-actions)
   3. [Aktiver GitHub Actions](#3️⃣-aktiver-github-actions)
   4. [Gi nødvendige rettigheter til GitHub Actions](#4️⃣-gi-nødvendige-rettigheter-til-github-actions)
2. [Bruke løsningen: Generere produktspesifikasjon](#bruke-løsningen-generere-produktspesifikasjon)
   1. [Fylle inn input-parametere](#1️⃣-fylle-inn-input-parametere)
   2. [Kjøre workflow](#2️⃣-kjøre-workflow)
   3. [Se gjennom og merge pull request](#3️⃣-se-gjennom-og-merge-pull-request)

---

## Sette opp løsningen: Fork, GitHub Pages og GitHub Actions

Denne denne av veiledningen viser hvordan du:
1. Lager en fork av mal-repoet  
2. Setter opp GitHub Pages  
3. Aktiverer GitHub Actions   
4. Gir nødvendige rettigheter til GitHub Actions 

---

### 1️⃣ Lage en fork av repoet

1. Gå til mal-repoet:  
   https://github.com/Arkitektum/produktspesifikasjon_mal
2. Klikk **Fork** (øverst til høyre)
3. Velg å legge forken på din egen konto eller under din organisasjon
4. Vent til kopien er opprettet

✅ Du har nå din egen fork av repoet

<details>
  <summary>Se skjermbilder</summary>
  
![Lage en ny fork](/veiledning/fork1.png)
![Lage en ny fork](/veiledning/fork2.png)
</details>

---

### 2️⃣ Sett GitHub Pages til å basere seg på "GitHub Actions"

1. Gå til din fork
2. Klikk **Settings**
3. Velg **Pages** i menyen til venstre
4. Under **Build and deployment**:
   - Source: **GitHub Actions**
5. Klikk **Save**

✅ GitHub Pages er nå konfigurert

<details>
  <summary>Se skjermbilder</summary>
  
![Klikk settings](/veiledning/settings.png)
![Klikk Pages](/veiledning/pages1.png)
![Velg source GitHub Actions](/veiledning/pages2.png)
</details>

---

### 3️⃣ Aktiver GitHub Actions

1. Gå til fanen **Actions**
2. Klikk **Enable / I understand my workflows**

✅ GitHub Actions er nå aktivert

<details>
  <summary>Se skjermbilder</summary>
  
![Klikk settings](/veiledning/actions1.png)
![Lage en ny fork](/veiledning/enableactions.png)
</details>

---

### 4️⃣ Gi nødvendige rettigheter til GitHub Actions

1. Gå til **Settings**
2. Velg **Actions → General**
3. Scroll ned til **Workflow permissions**
4. Velg:
   - ✅ **Read and write permissions**
   - ✅ **Allow GitHub Actions to create and approve pull requests**
5. Klikk **Save**

✅ GitHub Actions har nå nødvendige rettigheter

<details>
  <summary>Se skjermbilder</summary>
  
![Klikk settings](/veiledning/settings.png)
![Velg General under Actions](/veiledning/actions2.png)
![Allow GitHub Actions to create and approve pull requests](/veiledning/actions3.png)
</details>

---

Du har nå:
- En egen fork av repoet  
- GitHub Pages er aktivert  
- GitHub Actions er konfigurert med nødvendige rettigheter  
- Actions/Workflows er aktivert for generering av forenklete produktspesifikasjoner

---

## Bruke løsningen: Generere produktspesifikasjon

Denne veiledningen viser hvordan du bruker løsningen etter at repoet er satt opp.

### 1️⃣ Fylle inn input-parametere

1. Åpne mal-filen mal.yml:

2. Finn seksjonen med input-parametere (øverst i filen)

3. Oppdater relevante verdier, for eksempel:
    - metadataId
    - product_slug  
    - updated
    - andre felt definert i malen  

💡 Tips: Verdiene du oppgir her brukes til å generere produktspesifikasjonen.

#### Eksempel mal.yml - xmi fra sosi-modellregister

```yaml
metadataId: 041f1e6e-bdbc-4091-b48f-8a5990f3cc5b
output_directory: produktspesifikasjon
product_slug: admenheter
updated: 2026-06-01
scopes: 
  - name: datafangst
    url: https://sosi.geonorge.no/svn/SOSI/SOSI Del 3/Kommunal- og moderniseringsdepartementet/Arealplan/Arealplan 5.0/PlanleggingIgangsatt.xml
    generator: xmi
    description: Datamodellen brukes for å legge ved gml filer for planområdet som brukes i tjenesten for varsel om planoppstart.
```

#### Eksempel mal.yml - ogc-api

```yaml
metadataId: 041f1e6e-bdbc-4091-b48f-8a5990f3cc5b
output_directory: produktspesifikasjon
product_slug: admenheter
updated: 2026-06-01
scopes: 
  - name: innsynstjeneste
    url: https://plandata.ft.dibk.no/services/planleggingigangsatt/collections
    generator: ogc_feature_api
    description: Tjeneste for innsyn i planområder som er varslet for planlegging igangsatt.
```

#### Eksempel mal.yml - xmi fra sosi-modellregister og ogc-api (to scopes)

```yaml
metadataId: 041f1e6e-bdbc-4091-b48f-8a5990f3cc5b
output_directory: produktspesifikasjon
product_slug: admenheter
updated: 2026-06-01
scopes: 
  - name: datafangst
    url: https://sosi.geonorge.no/svn/SOSI/SOSI Del 3/Kommunal- og moderniseringsdepartementet/Arealplan/Arealplan 5.0/PlanleggingIgangsatt.xml
    generator: xmi
    description: Datamodellen brukes for å legge ved gml filer for planområdet som brukes i tjenesten for varsel om planoppstart.
  - name: innsynstjeneste
    url: https://plandata.ft.dibk.no/services/planleggingigangsatt/collections
    generator: ogc_feature_api
    description: Tjeneste for innsyn i planområder som er varslet for planlegging igangsatt.
```

---

### 2️⃣ Kjøre workflow

1. Gå til fanen **Actions**
2. Velg workflow: **Generate produktspesifikasjon**
3. Klikk **Run workflow**
4. Velg branch (vanligvis `main`)
5. Klikk **Run workflow**

---

### 3️⃣ Se gjennom og merge pull request

Når workflowen har kjørt ferdig:

1. Det opprettes automatisk en **Pull Request**
2. Gå til **Pull requests**
3. Åpne den nye PR-en
4. Se gjennom endringene
5. Klikk **Merge pull request**
6. Bekreft med **Confirm merge**

✅ Produktspesifikasjonen er nå oppdatert  
✅ Endringene publiseres til GitHub pages

---

Du har nå:
- Oppdatert input parameterene i `mal.yml`
- Kjørt workflowen manuelt som generer produktspesifikasjonen
- Merget Pull Requesten som inneholder produktspesifikasjonen, og blir publisert via GitHub Pages

---

Du har nå generert og publisert en forenklet produktspesifikasjon