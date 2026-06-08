# 🧭 Guide: Fork, GitHub Pages og GitHub Actions

Denne veiledningen viser hvordan du:
1. Lager en fork av repoet  
2. Setter opp GitHub Pages  
3. Gir riktige rettigheter til GitHub Actions  
4. Aktiverer GitHub Actions  

---

## 1️⃣ Lage en fork av repoet

1. Gå til repoet:  
   https://github.com/Arkitektum/produktspesifikasjon_malkan  
2. Klikk **Fork** (øverst til høyre)
3. Velg din konto eller organisasjon
4. Vent til kopien er opprettet

✅ Du har nå din egen fork av repoet

---

## 2️⃣ Sette GitHub Pages til "Deploy from branch"

1. Gå til din fork
2. Klikk **Settings**
3. Velg **Pages** i menyen til venstre
4. Under **Build and deployment**:
   - Source: **Deploy from a branch**
   - Branch: `main` (eller `gh-pages` hvis aktuelt)
   - Folder: `/ (root)`
5. Klikk **Save**

✅ GitHub Pages er nå konfigurert

---

## 3️⃣ Aktivere “Allow GitHub Actions to create and approve pull requests”

1. Gå til **Settings**
2. Velg **Actions → General**
3. Scroll ned til **Workflow permissions**
4. Velg:
   - ✅ **Read and write permissions**
   - ✅ **Allow GitHub Actions to create and approve pull requests**
5. Klikk **Save**

✅ GitHub Actions har nå nødvendige rettigheter

---

## 4️⃣ Aktivere GitHub Actions

### Alternativ A (første gang)
1. Gå til fanen **Actions**
2. Klikk **Enable / I understand my workflows**

### Alternativ B
1. Gå til **Settings → Actions → General**
2. Under **Actions permissions**:
   - Velg ✅ **Allow all actions and reusable workflows**

✅ GitHub Actions er nå aktivert

---

## ✅ Ferdig

Du har nå:
- En egen fork av repoet  
- GitHub Pages aktivert  
- GitHub Actions konfigurert med riktige rettigheter  
- Workflows aktivert  

---

🚀 Tips: Når du gjør endringer i repoet, kan de automatisk deployes via GitHub Actions og bli synlige på GitHub Pages.