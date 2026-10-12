# Ghid de Instalare și Configurare Oracle SQL Developer

Acest ghid prezintă pașii necesari pentru descărcarea și instalarea **Oracle SQL Developer**, mediul grafic de dezvoltare (IDE) oficial și gratuit oferit de Oracle pentru lucrul cu bazele de date.

## 1. Descărcarea aplicației

SQL Developer nu necesită o instalare clasică (prin *wizard*), ci este livrat sub forma unei arhive care trebuie doar extrasă.

### Pasul 1: Accesarea paginii de descărcare
Navigați către pagina oficială de descărcare Oracle SQL Developer:
[https://www.oracle.com/database/sqldeveloper/technologies/download/](https://www.oracle.com/database/sqldeveloper/technologies/download/)

### Pasul 2: Alegerea versiunii potrivite
Pe pagină veți găsi mai multe pachete disponibile. Alegeți varianta corespunzătoare sistemului dumneavoastră de operare:

* **Pentru Windows (Recomandat):** 
  Selectați pachetul **"Windows 64-bit with JDK included"**. Această variantă este cea mai simplă, deoarece include mediul de execuție Java (JDK) necesar pentru rularea aplicației, scutindu-vă de o instalare separată.
* **Pentru macOS sau Linux / Alte platforme:** 
  Selectați pachetele specifice (care nu includ JDK).
  > ⚠️ **Atenție:** Dacă alegeți o versiune fără JDK inclus, va trebui să aveți instalat pe sistem **Java Development Kit (JDK) 11 sau 17** înainte de a rula aplicația.

### Pasul 3: Autentificarea
Faceți clic pe butonul de descărcare. Vi se va solicita să acceptați acordul de licență (*Oracle License Agreement*) și veți fi redirecționat către pagina de autentificare.
Folosiți **același cont Oracle** creat anterior pentru descărcarea imaginii de container Docker/Podman.

## 2. Instalarea și prima pornire

### Pasul 1: Instalarea (Dezarhivarea)
1. După finalizarea descărcării, veți obține un fișier `.zip`.
2. Extrageți conținutul arhivei într-o locație accesibilă de pe discul dumneavoastră (de exemplu: `C:\oracle\sqldeveloper` sau `D:\Programe\sqldeveloper`). 
   *Nu extrageți în directoare cu permisiuni stricte precum `Program Files` pentru a evita problemele de scriere ale setărilor.*

### Pasul 2: Lansarea aplicației
1. Navigați în folderul unde ați extras arhiva și rulați fișierul **`sqldeveloper.exe`** (sau `sqldeveloper.sh` pentru Linux/Mac).
2. **La prima pornire:** 
   * Dacă vă întreabă dacă doriți să importați preferințe dintr-o instalare anterioară, selectați **"No"**.
   * Dacă ați descărcat versiunea fără JDK, aplicația vă va cere să introduceți calea către folderul unde este instalat JDK-ul (ex: `C:\Program Files\Java\jdk-17`).
3. (Opțional) La solicitarea privind urmărirea statisticilor de utilizare, puteți debifa opțiunea dacă doriți.

## 3. Conectarea la baza de date locală

Odată ce interfața SQL Developer s-a încărcat, puteți adăuga conexiunea către baza de date Oracle 19c creată în Podman.

1. În panoul din partea stângă, secțiunea **Connections**, faceți clic pe pictograma **verde cu un plus `+`** pentru a adăuga o conexiune nouă.
2. Completați formularul de conexiune cu următoarele date:
   * **Name:** `Conexiune_Local_UniBuc` *(sau orice nume descriptiv doriți)*
   * **Username:** `myuser` *(numele utilizatorului creat în ghidul anterior)*
   * **Password:** Parola aleasă (ex: `MyStrongPassword123`) -> bifați **Save Password**.
   * **Connection Type:** `Basic`
   * **Role:** `default`
   * **Hostname:** `localhost` *(sau `127.0.0.1`)*
   * **Port:** `1521`
   * Selectați butonul radio pentru **Service name** și introduceți: `ORCLPDB1`

3. Faceți clic pe butonul **Test**. În stânga jos, pe status bar, ar trebui să apară mesajul **`Status: Success`**.
4. Faceți clic pe **Save** pentru a salva conexiunea, apoi pe **Connect** pentru a deschide foaia de lucru SQL.

Sunteți gata să începeți lucrul! 🚀
