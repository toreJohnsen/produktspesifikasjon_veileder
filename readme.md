# Guide: Fork, GitHub Pages og GitHub Actions

Denne veiledningen viser hvordan du:
1. Lager en fork av repoet  
2. Setter opp GitHub Pages  
3. Gir riktige rettigheter til GitHub Actions  
4. Aktiverer GitHub Actions  

---

## 1️⃣ Lage en fork av repoet

1. Gå til repoet:  
   https://github.com/Arkitektum/produktspesifikasjon_mal
2. Klikk **Fork** (øverst til høyre)
3. Velg din konto eller organisasjon
4. Vent til kopien er opprettet

✅ Du har nå din egen fork av repoet

<details>
  <summary>Se skjermbilder</summary>
  
![Lage en ny fork](/veiledning/fork1.png)
![Lage en ny fork](/veiledning/fork2.png)
</details>

---

## 2️⃣ Sette GitHub Pages til "GitHub Actions"

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

## 3️⃣ Aktivere GitHub Actions

1. Gå til fanen **Actions**
2. Klikk **Enable / I understand my workflows**

✅ GitHub Actions er nå aktivert

<details>
  <summary>Se skjermbilder</summary>
  
![Klikk settings](/veiledning/actions1.png)
![Lage en ny fork](/veiledning/enableactions.png)
</details>

---

## 4️⃣ Aktivere “Allow GitHub Actions to create and approve pull requests”

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
- GitHub Pages aktivert  
- GitHub Actions konfigurert med riktige rettigheter  
- Workflows aktivert  

---

# Bruke løsningen: Generere produktspesifikasjon

Denne veiledningen viser hvordan du bruker løsningen etter at repoet er satt opp.

## 1️⃣ Fylle inn input-parametere

1. Åpne mal-filen mal.yml:

2. Finn seksjonen med input-parametere (øverst i filen)

3. Oppdater relevante verdier, for eksempel:
- metadataId
- product_slug  
- updated
- andre felt definert i malen  

💡 Tips: Verdiene du oppgir her brukes automatisk til å generere produktspesifikasjonen.

---

## 2️⃣ Kjøre workflow

1. Gå til fanen **Actions**
2. Velg workflow:
👉 **Generate produktspesifikasjon**
3. Klikk **Run workflow**
4. Velg branch (vanligvis `main`)
5. Klikk **Run workflow**

---

## 3️⃣ Pull Request opprettes automatisk

Når workflowen er ferdig:

1. Det opprettes automatisk en **Pull Request**
2. Gå til **Pull requests**
3. Åpne den nye PR-en
4. Se gjennom endringene

---

## 4️⃣ Merge Pull Request

1. Klikk **Merge pull request**
2. Bekreft med **Confirm merge**

✅ Produktspesifikasjonen er nå oppdatert  
✅ Endringene publiseres (via GitHub Pages hvis aktivert)

---

## Oppsummert

- Oppdater input i `mal.yml`  
- Kjør workflowen manuelt  
- Merge Pull Requesten som genereres  

---

🚀 Ferdig! Du har nå generert og publisert en produktspesifikasjon.
```
