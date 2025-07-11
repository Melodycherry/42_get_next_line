# 📜 get_next_line 

## 🎯 Objectifs

Développer une fonction `get_next_line()` qui permet de :
- Lire **ligne par ligne** à partir d’un descripteur de fichier.
- Gérer plusieurs appels successifs pour lire l'intégralité d'un fichier.
- S’adapter à différents types de flux : **fichiers classiques** et **entrée standard** (`stdin`).
- Utiliser un buffer de lecture dont la taille est définie à la compilation via une **macro `BUFFER_SIZE`**.

## 🔍 Comportement attendu

- 🔁 Chaque appel renvoie **la ligne suivante** du fichier (`\n` inclus si présent).
- 📁 À la **fin du fichier**, ou en cas d’**erreur**, la fonction retourne **`NULL`**.
- 📜 Si la **dernière ligne ne se termine pas** par un `\n`, elle est tout de même **retournée telle quelle**.
- 📂 La fonction fonctionne aussi bien avec des **fichiers classiques** qu’avec **l’entrée standard** (`stdin`).

## ⚙️ Compilation

Le projet doit pouvoir être compilé **avec ou sans** la macro `BUFFER_SIZE`  
*💻 Exemple de compilation (avec `BUFFER_SIZE = 42`) :*  
```c
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 get_next_line.c get_next_line_utils.c main.c
```  
💡 Remarque : La Moulinette et les évaluateurs doivent tester avec différentes tailles de buffer, comme :  
`BUFFER_SIZE=1`  
`BUFFER_SIZE=9999`  
voire `BUFFER_SIZE=10000000`

---

🧠 **Ce que j’ai appris**  

•	🔒 L’utilisation des variables statiques pour conserver un état entre plusieurs appels de fonction  
•	⚠️ La gestion de la mémoire (malloc/free) dans un contexte itératif  
•	📈 L’optimisation des appels à read() : lire le moins de données possible à chaque appel  
•	💥 La robustesse : gérer toutes les erreurs possibles (mauvais fd, EOF, etc.)  

---  

✅ **STATUT:**  
📅 Date de rendu : 15.12.2024  
📝 Note obtenue : 100/100

---
