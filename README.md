# UnrealEngine5_Project
DOCUMENTAȚIE

Nume Materie: Dezvoltare de jocuri 3D

Descriere

   In starea actuala, jocul are implementat doua nivele, acțiunile pe care
caracterul principal le poate face și anume: WA/S/D mișcarea, Space pentru Jump, SHIFT pentru Sprint, P pentru Meniul de Pauza, tasta 2 pentru a intrat în modul de lupta (apăsarea din nou a tastei 2 pentru a ieși), tasta 1 pentru a intra în modul pasiv, Click stanga pentru a ataca, Click Dreapta pentru a block un atac.
   Landscape-ul a fost creat prin modul de Modeling din Unreal. În acesta putem găsi următoarele camera:
camera in care jucatorul porneste (se afla o usa sugestiva ca acolo a ramas blocat in templu)
antecamera principala (unde se afla și primul Checkpoint de tip Actor BP)
camera principala a primul nivel (unde se afla o fantana, coloane, un mormant) si din aceasta poti avea 2 variante de drumuri
camera sicrielor, unde sunt cateva sicrie ale gărzii personale a persoanei anonime din mormant
o camera mica de legatura 
camera unde se afla primul inamic
camera finală care face transpunerea între nivelul 1 și nivelul 2 (înainte de a intra în subnivelul 2 prin intrarea in coliziune cu un Box pentru a incarca nivelul, exista deasemenea aici un Checkpoint pentru a mai salva o data înainte de a intra în nivel)
   In momentul actual, jocul porneste dintr-un templu si are ca scop găsirea ieșirii din acest templu printr-un dungeon.
   Nivelul 1. Cum apasam PLAY GAME din Main Menu în fata se afla primele camera din joc și Checkpointul. După aceste camere jucătorul va trebui sa îsi gaseasca drumul prin templu ca sa ajungă în dungeon. În dungeon înainte de prima camera, este marcată de o luptă cu un inamic, acesta inițial se deplaseaza pe un spline, dacă este întrerupt (de un atac al playerului) acesta se va opri din patrulare (passive mode) și va începe sa atace instigatorul (intra în combat mode). De asemenea el se mai poate opri din patrula dacă îl ataci pana sa te vadă el. Dacă treci de acesta vei putea sa mergi mai departe. În caz contrar dacă el reușește sa te omoare va apărea un widget (Death Screen) care te întreabă dacă vrei sa reiei de la ultimul Checkpoint sau dacă vrei sa te duci înapoi în meniul principal. Daca il omori in schimb, ajungi inauntrul dungeonului, ai un ultim Checkpoint de salvare și se va încărca Nivelul 2.
   Nivelul 2. În acest subnivel, playerul se afla în adancul templului, mai exact în dungeon. El va vedea în fata o camera principala cu coloane și în capătul acesteia o usa mare, în dreapta o camera de depozitare, si-n stanga o biblioteca. În biblioteca exista un raft special care dacă playerul îl găsește va putea parcurge mai departe în dungeon. După găsirea raftului se va deschide un pasaj secret și playerul ajunge la cea de a doua lupta care dacă o va castiga (momentan) termina jocul. (zic momentan că acolo trebuia sa fie un obiect care după ce se termina lupta il colecat si putea sa deschidă o ușă ca să continue drumul spre ieșire).



Specificatii tehnice

   Sistemul de operare pe care va putea fi jucat este PC, nu necesita pachete adiționale, momentan este gandit doar ca SinglePlayer, deci fără conexiune la rețea și este făcut în UE 5.3 (updatat la 5.4).
   Categoriile jocului: RPG, Acțiune, Aventura, Puzzle.
   Taguri: RPG, Story, Adventure, Single Player, Third Person, Puzzle, Medieval, Action.

Acțiuni Disponibile: - WASD > move
- L SHIFT > Sprint
- P > Meniu Pauza
- 1 intrare în Passive Mode
- 2 intrare în Combat Mode
- Left Click > Atac
- Right Click > Block

   Dispozitive: Mouse + Tastatura
   Clasele proprii folosite: Am folosit clase blueprint de tip Actor , Pawn, Characters, Actor Components.

   Actori:
- Actorul Weapon+ai sai copii (childs)/BP_Projectile_parent + ai sai copii
- Actorul Checkpoint (care ne salveaza progresul și în caz ca murim ne întoarce la ultimul Checkpoint);
- Actorul BP_LoadUnloadLevel, care incarca subnivelul 2 cand intram în coliziune cu Box-ul sau
- Actorul BP_BibliotecaAscunda, care are un box de coliziune pentru a afișa un text iar dacă facem ce ne zice textul se va deschide un pasaj secret;
   Pioni:
- Pionul BP_PawnCamera, care are rol de a ne prezenta un “background” mai special in meniul principal
   Caractere:
-  Caracterul principal BP_Player, are toate funcțiile menționate la acțiuni, este
singurul caracter care are implementate toate acțiunile posibile și singurul
care va putea fi controlat de către jucător.
- Caracterul inamic (BP_Enemy_Base) + BP_Enemy_Melee si BP_ENemey_Mage care sunt childs ai actorului parent BP_Enemy_Base

Bibliografie:
- Cursuri si laboratoare
- https://docs.unrealengine.com/5.3/en-US/
- YouTube 


 
