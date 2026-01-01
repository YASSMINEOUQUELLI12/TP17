# 📦 JSON vs XML vs Protobuf — Lab de Sérialisation (Node.js)

## 🔎 Aperçu

Ce lab montre comment :

- Créer une petite liste d’employés en JavaScript.  
- Sérialiser cette liste en **JSON**, **XML** et **Protobuf**.  
- Sauvegarder chaque format dans un fichier.  
- Comparer la **taille des fichiers**.  
- Mesurer le **temps d’encodage / décodage**.  

👉 À la fin, on comprend pourquoi **gRPC préfère Protocol Buffers** plutôt que JSON ou XML.

---

## 🎯 Objectifs pédagogiques

À la fin du lab, l’étudiant sera capable de :

- Créer un projet Node.js minimal.
- Utiliser `JSON.stringify` et `JSON.parse`.
- Générer un fichier XML avec `xml-js`.
- Définir un schéma Protobuf (`.proto`).
- Encoder / décoder avec `protobufjs`.
- Comparer tailles et performances des formats.

---


<img width="960" height="516" alt="TP17" src="https://github.com/user-attachments/assets/f03e0262-bc27-4f91-88ec-ee0d5caafd59" />
## ✅ Prérequis

- **Node.js v14+**
- Connaissances de base :
  - JavaScript côté serveur
  - JSON
- Un éditeur de code (VS Code, WebStorm, etc.)

---

## 🏗️ Étape 0 — Préparer le projet

```bash
mkdir json-xml-protobuf-lab
cd json-xml-protobuf-lab
npm init -y
📦 Étape 1 — Installer les dépendances
npm install xml-js protobufjs
📄 Étape 2 — Définir le schéma Protobuf
:

syntax = "proto3";

message Employee {
  int32 id = 1;
  string name = 2;
  int32 salary = 3;
}

message Employees {
  repeated Employee employee = 1;
}

🧠 Étapes 3 à 10 — Script principal

Créer index.js et y ajouter :

création des employés

sérialisation JSON / XML / Protobuf

écriture des fichiers

mesure des tailles

mesure des temps encode/decode

👉 Le code complet du script est donné dans les consignes du TP (copier tel quel).

▶️ Exécution
node index.js

Exemple de sortie
Taille de 'data.json' : 127 octets
Taille de 'data.xml'  : 224 octets
Taille de 'data.proto': 41 octets


et :

JSON encode: X ms
JSON decode: X ms
...

🧩 Interprétation
XML

Très verbeux

Fichiers plus gros

Parsing plus lent

JSON

Plus compact

Simple à manipuler

Très utilisé dans les APIs REST

Protobuf

Format binaire

Très compact

Super rapide

Idéal pour gRPC et services distribués

➡️ Protobuf est le plus performant.

🔬 Extensions possibles

Ajouter des champs (email, date d’embauche…)

Tester JSON.stringify(obj, null, 2) pour voir l’impact

Relire data.proto et redécoder

Intégrer l’exemple dans un projet gRPC

🏁 Conclusion

Ce lab montre clairement que :

JSON est pratique et simple,

XML devient vite lourd,

Protobuf offre le meilleur compromis performance + taille, ce qui explique son adoption dans gRPC.



