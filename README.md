# UnrealEngine5_Project - Joc de Acțiune-Aventură RPG

## Descriere Generală

Acest proiect reprezintă un joc de acțiune-aventură cu elemente RPG, dezvoltat în **Unreal Engine 5.3 (actualizat la 5.4)**. Jucătorul pornește într-un templu antic, având ca scop găsirea unei ieșiri printr-un sistem complex de temnițe (dungeon).

Jocul se desfășoară în modul **single-player** și pune accent pe explorare, rezolvarea unor mici puzzle-uri și lupte tactice.

## Starea Actuală a Jocului

### Niveluri Implementate

Jocul include în prezent două niveluri distincte:

* **Nivelul 1 (Templul Exterior):** Jucătorul începe într-o antecameră a templului, cu un prim Checkpoint. Acesta trebuie să-și croiască drum prin diverse camere tematice (fântâni, coloane, morminte, camera sicrielor) pentru a ajunge la intrarea în dungeon. Prima confruntare cu un inamic are loc înainte de intrarea propriu-zisă în dungeon, marcând o tranziție către o zonă mai periculoasă.

* **Nivelul 2 (Dungeon):** Odată ajuns în adâncul templului, jucătorul explorează o cameră principală, o cameră de depozitare și o bibliotecă. Găsirea unui raft special în bibliotecă deschide un pasaj secret către a doua și ultima confruntare cu un inamic. Victoria în această luptă marchează (momentan) finalul jocului.

### Mecanici de Joc și Caracteristici

* **Deplasare:**
    * **WASD:** Mișcare (Înainte, Înapoi, Stânga, Dreapta)
    * **Spațiu:** Săritură
    * **SHIFT stânga:** Sprint

* **Combat:**
    * **Click Stânga:** Atac
    * **Click Dreapta:** Blocare
    * **Tasta 1:** Intrare în Mod Pasiv (dezactivarea posturii de luptă)
    * **Tasta 2:** Intrare în Mod de Luptă (activarea posturii de luptă)

* **Alte Acțiuni:**
    * **P:** Meniu de Pauză

* **Sistem de Checkpoint:** Checkpoint-urile (Actor BP) salvează progresul jucătorului. În cazul morții, un ecran dedicat (Death Screen) oferă opțiunea de a reîncărca de la ultimul Checkpoint sau de a reveni la meniul principal.

* **Inamici:** Inamicii patrulează pe trasee predefinite (spline-uri). Dacă sunt atacați sau sesizează prezența jucătorului, trec din modul pasiv în modul de luptă și inițiază atacul.

* **Design Nivel:** Landscape-ul și structura nivelurilor au fost create folosind modul de Modeling din Unreal Engine.

## Specificatii Tehnice

* **Platforma:** PC
* **Mod de Joc:** Single-Player
* **Motor Grafic:** Unreal Engine 5.3 (actualizat la 5.4)
* **Genuri:** RPG, Acțiune, Aventură, Puzzle
* **Tag-uri:** RPG, Story, Adventure, Single Player, Third Person, Puzzle, Medieval, Action
* **Control:** Tastatură + Mouse
* **Dependențe:** Nu necesită pachete adiționale.

## Arhitectură Blueprints și Clase Proprii

Am utilizat extensiv clase Blueprint de tip `Actor`, `Pawn`, `Character` și `Actor Component` pentru implementarea funcționalităților jocului.

### Actori Notabili:

* **`BP_Weapon` (și copiii săi):** Clasele de bază pentru armele din joc și proiectile (`BP_Projectile_parent`).
* **`BP_Checkpoint`:** Gestionează salvarea progresului și punctul de respawn.
* **`BP_LoadUnloadLevel`:** Actor care declanșează încărcarea subnivelului 2 la intrarea în coliziune.
* **`BP_BibliotecaAscunsa`:** Include un box de coliziune care, la interacțiune, afișează un text sugestiv și deschide un pasaj secret odată ce condiția este îndeplinită.

### Pioni:

* **`BP_PawnCamera`:** Un pion utilizat pentru a oferi un "background" vizual dinamic în meniul principal.

### Caractere:

* **`BP_Player`:** Caracterul principal, controlat de jucător. Implementează toate acțiunile de mișcare, luptă și interacțiune.
* **`BP_Enemy_Base` (și copiii săi: `BP_Enemy_Melee`, `BP_Enemy_Mage`):** Clasa de bază pentru toți inamicii din joc, cu implementări specifice pentru tipurile de inamici (melee, mage).

## Bibliografie

* Cursurile și laboratoarele specifice materiei "Dezvoltare de jocuri 3D".
* Documentația oficială Unreal Engine: [https://docs.unrealengine.com/5.3/en-US/](https://docs.unrealengine.com/5.3/en-US/)
* Resurse educaționale de pe YouTube.
