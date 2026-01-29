# 🚀 Guide de Déploiement - AppRepas

Ce guide vous explique comment déployer votre application AppRepas sur Vercel avec CI/CD automatique via GitHub Actions.

## 📋 Prérequis

- Compte GitHub (déjà configuré ✅)
- Compte Vercel (gratuit) - [vercel.com](https://vercel.com)
- Clés API Supabase et Gemini

## 🔧 Étape 1 : Créer un projet Vercel

1. Allez sur [vercel.com](https://vercel.com) et connectez-vous
2. Cliquez sur **"Add New Project"**
3. Importez le repository **lgaut/AppRepas**
4. Configurez le projet :
   - **Framework Preset** : Next.js
   - **Root Directory** : `./` (racine)
   - **Build Command** : `npm run build`
   - **Output Directory** : `.next`

## 🔑 Étape 2 : Configurer les variables d'environnement sur Vercel

Dans les paramètres du projet Vercel, ajoutez ces variables d'environnement :

```
NEXT_PUBLIC_SUPABASE_URL=https://pookipijifftnrhrrwsz.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=votre_cle_anon
GEMINI_API_KEY=votre_cle_gemini
GEMINI_MODEL=gemini-2.5-flash-lite
GEMINI_IMAGE_MODEL=gemini-2.5-flash-image
```

## 🔐 Étape 3 : Configurer les secrets GitHub

Pour activer le déploiement automatique via GitHub Actions, ajoutez ces secrets dans votre repository GitHub :

1. Allez sur **https://github.com/lgaut/AppRepas/settings/secrets/actions**
2. Cliquez sur **"New repository secret"** et ajoutez :

### Secrets Vercel

- **VERCEL_TOKEN** : Votre token Vercel
  - Obtenez-le sur : https://vercel.com/account/tokens
  
- **VERCEL_ORG_ID** : ID de votre organisation Vercel
  - Trouvez-le dans les paramètres de votre projet Vercel
  
- **VERCEL_PROJECT_ID** : ID de votre projet Vercel
  - Trouvez-le dans les paramètres de votre projet Vercel

### Secrets de l'application

- **NEXT_PUBLIC_SUPABASE_URL** : `https://pookipijifftnrhrrwsz.supabase.co`
- **NEXT_PUBLIC_SUPABASE_ANON_KEY** : Votre clé anonyme Supabase
- **GEMINI_API_KEY** : Votre clé API Gemini
- **GEMINI_MODEL** : `gemini-2.5-flash-lite`
- **GEMINI_IMAGE_MODEL** : `gemini-2.5-flash-image`

## 🎯 Étape 4 : Déploiement automatique

Une fois les secrets configurés :

1. **Push sur main** : Chaque push sur la branche `main` déclenchera automatiquement :
   - Installation des dépendances
   - Linting du code
   - Build de l'application
   - Déploiement sur Vercel

2. **Pull Requests** : Les PR seront également buildées pour vérification

## 📊 Vérifier le déploiement

1. Allez sur l'onglet **Actions** de votre repository GitHub
2. Vous verrez les workflows en cours d'exécution
3. Une fois terminé, votre application sera disponible sur l'URL Vercel

## 🌐 URL de production

Votre application sera accessible à :
- URL Vercel : `https://app-repas-xxx.vercel.app`
- Domaine personnalisé (optionnel) : Configurable dans Vercel

## 🔄 Workflow CI/CD

Le workflow automatique effectue :

```
1. Checkout du code
2. Setup Node.js 20
3. Installation des dépendances (npm ci)
4. Linting (npm run lint)
5. Build (npm run build)
6. Déploiement sur Vercel
```

## 🐛 Dépannage

### Le déploiement échoue

- Vérifiez que tous les secrets GitHub sont correctement configurés
- Vérifiez les logs dans l'onglet Actions de GitHub
- Assurez-vous que les variables d'environnement sont correctes

### L'application ne fonctionne pas

- Vérifiez les variables d'environnement sur Vercel
- Consultez les logs de l'application dans le dashboard Vercel
- Vérifiez que Supabase et Gemini API sont accessibles

## 📝 Commandes utiles

```bash
# Déploiement manuel depuis votre machine
npm install -g vercel
vercel login
vercel --prod

# Vérifier le build localement
npm run build
npm run start
```

## 🎉 Félicitations !

Votre application est maintenant déployée avec CI/CD automatique ! 🚀

Chaque modification poussée sur GitHub sera automatiquement déployée sur Vercel.
