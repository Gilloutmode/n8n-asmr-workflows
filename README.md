# 🚨 N8N ASMR Workflows - EMERGENCY BACKUP

## 📋 INFORMATIONS CRITIQUES

**Workflow Principal:** FULL PROD RESTOR  
**ID Original:** PYah5PXnV8cewWD1  
**Fichier de sauvegarde:** `production/FULL_PROD_RESTOR_COMPLETE.json`

## 🔧 RESTAURATION IMMÉDIATE

### Étape 1: Récupérer le fichier
```bash
# Télécharger directement
curl -o workflow.json https://raw.githubusercontent.com/Gilloutmode/n8n-asmr-workflows/main/production/FULL_PROD_RESTOR_COMPLETE.json
```

### Étape 2: Importer dans N8N
1. Aller sur votre N8N: https://gilloutmode.app.n8n.cloud
2. Cliquer sur **"+ Add workflow"**
3. Sélectionner **"Import from file"** ou **"Import from URL"**
4. Coller le contenu du fichier JSON ou utiliser l'URL:
   ```
   https://raw.githubusercontent.com/Gilloutmode/n8n-asmr-workflows/main/production/FULL_PROD_RESTOR_COMPLETE.json
   ```

### Étape 3: Reconfigurer les credentials
Après import, vous devrez reconnecter:
- ✅ Google Sheets (ID: QThik6pkSDGoqjj6)
- ✅ FAL AI (ID: 0HqTwtiVCKLW5dZq) 
- ✅ OpenAI (ID: rN03lkUSMUTmFWoD)
- ✅ Perplexity (ID: a3xpuIFkGfsR2oe2)

## 🎯 FONCTIONNALITÉS CORRIGÉES

### ✅ Perplexity Unique Search
- **Problème résolu:** Recherches répétitives
- **Solution:** Identifiant unique avec timestamp + random seed
- **Code:** `{{ new Date().toISOString() }}-{{ Math.floor(Math.random() * 1000000) }}`

### ✅ FAL AI Wait System  
- **Problème résolu:** Pas d'attente pour génération vidéo
- **Solution:** Système de polling avec retry
- **Nœuds:** Wait for FAL Generation → Check FAL Status → Check Completion Status

### ✅ Google Sheets Integration
- **Sheet ID:** 1A7saFJS9IUd8rtlYbhipWnblr55brVwDmgPZHD9gWW4
- **Mode:** Production
- **Row validation:** Force row_number ≥ 2 (jamais 1 = headers)

## 🔄 WORKFLOW COMPLET

### Triggers
- **Schedule Trigger:** Toutes les 6 heures
- **Manual Test:** Test manuel

### Processus Principal
1. **Get Pending Video** → Récupère ligne "pending" 
2. **Check Mode** → Auto/Manuel
3. **Get ASMR Trends** → Recherche Perplexity unique
4. **Generate ASMR Scenes** → 6 scènes via OpenAI
5. **Generate Prompts** → Prompts Seedance Pro
6. **Generate Video (FAL)** → 6 vidéos avec attente
7. **Update Google Sheets** → URLs + statut

### Configuration FAL AI
```json
{
  "model": "seedance-lite",
  "aspect_ratio": "1:1", 
  "resolution": "720p",
  "duration": "10s"
}
```

## 🆘 EN CAS DE PROBLÈME

1. **Workflow disparu:** Utiliser ce backup GitHub
2. **Erreurs de connexion:** Vérifier credentials
3. **FAL AI timeout:** Vérifier Wait nodes (120s)
4. **Google Sheets erreur:** Vérifier row_number ≥ 2

## 📞 SUPPORT

Repository créé le: 2025-07-09T11:48:00Z  
Dernière sauvegarde: 2025-07-09T11:49:36Z  
Version: 429b881a-0704-44b7-85a7-76a0f045dc2f

**🔗 Lien direct vers le fichier:**  
https://github.com/Gilloutmode/n8n-asmr-workflows/blob/main/production/FULL_PROD_RESTOR_COMPLETE.json