# 🍽️ AppRepas - Générateur de Recettes IA

> Application moderne de génération de recettes personnalisées propulsée par l'IA Gemini et Supabase

![Next.js](https://img.shields.io/badge/Next.js-15-black)
![TypeScript](https://img.shields.io/badge/TypeScript-5-blue)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3-38bdf8)
![Gemini](https://img.shields.io/badge/Gemini-AI-orange)

## ✨ Fonctionnalités

- 🤖 **Génération IA** : Recettes personnalisées générées par Gemini AI
- 🥗 **Sélection d'ingrédients** : Choisissez vos protéines préférées
- 📊 **Nutrition** : Estimation automatique des macronutriments
- 🖼️ **Images IA** : Génération d'images de plats avec Gemini
- ✅ **Gestion** : Acceptez ou refusez les propositions
- 🎨 **Design moderne** : Interface élégante et responsive

## 🚀 Technologies

- **Framework** : Next.js 15 (App Router)
- **Langage** : TypeScript
- **Styling** : TailwindCSS + shadcn/ui
- **Base de données** : Supabase
- **IA** : Google Gemini (génération de recettes et images)
- **Déploiement** : Vercel

## 📦 Installation

```bash
# Cloner le repository
git clone https://github.com/lgaut/AppRepas.git
cd AppRepas

# Installer les dépendances
npm install

# Configurer les variables d'environnement
cp .env.example .env.local
# Éditer .env.local avec vos clés API

# Lancer le serveur de développement
npm run dev
```

## 🔑 Variables d'environnement

Créez un fichier `.env.local` avec :

```env
NEXT_PUBLIC_SUPABASE_URL=votre_url_supabase
NEXT_PUBLIC_SUPABASE_ANON_KEY=votre_cle_anon_supabase
GEMINI_API_KEY=votre_cle_api_gemini
GEMINI_MODEL=gemini-2.5-flash-lite
GEMINI_IMAGE_MODEL=gemini-2.5-flash-image
```

## 🎯 Utilisation

1. **Générer une recette** : Sélectionnez vos protéines préférées et le type de repas
2. **Consulter** : Visualisez la recette générée avec ingrédients et étapes
3. **Décider** : Acceptez ou refusez la proposition
4. **Historique** : Retrouvez toutes vos recettes dans la liste

## 📱 Pages

- `/` - Page d'accueil
- `/generate` - Génération de recettes
- `/recipes` - Liste des recettes
- `/recipes/[id]` - Détail d'une recette

## 🛠️ Scripts

```bash
npm run dev      # Développement
npm run build    # Build production
npm run start    # Serveur production
npm run lint     # Linter
```

## 📄 Licence

MIT © 2026

## 👤 Auteur

**lgaut**
- GitHub: [@lgaut](https://github.com/lgaut)

---

⭐ N'oubliez pas de mettre une étoile si ce projet vous plaît !
