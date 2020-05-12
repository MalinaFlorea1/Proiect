# Documentație Proiect Cloud
##	Introducere. Noțiuni teoretice RESTful API
API RESTful este o interfață de program de aplicație (API) care folosește solicitări HTTP la datele GET, PUT, POST și DELETE. API pentru un site web este codul care permite două programe software să comunice între ele. API precizează modul corect pentru un dezvoltator de a scrie un program care solicită servicii de la un sistem de operare sau o altă aplicație.
API RESTful - denumită, de asemenea, un serviciu web RESTful sau API REST - se bazează pe transferul reprezentativ de stat (REST), un stil arhitectural și o abordare a comunicațiilor utilizate deseori în dezvoltarea serviciilor web.
Tehnologia REST este de regulă preferată decât cea mai robustă tehnologie SOAP (Simple Object Access Protocol), deoarece REST folosește mai puțin lățime de bandă, ceea ce o face mai potrivită pentru utilizarea eficientă a internetului.
API RESTful descompun o tranzacție pentru a crea o serie de module mici. Fiecare modul se adresează unei anumite părți subiacente a tranzacției. Această modularitate oferă dezvoltatorilor o multă flexibilitate, dar poate fi dificil pentru dezvoltatori să-și proiecteze API-ul REST de la zero. În prezent, mai multe companii oferă modele pe care dezvoltatorii să le folosească; modelele furnizate de Amazon S3, Cloud Data Management Interface (CDMI) și OpenStack Swift sunt cele mai populare.
API RESTful utilizează metodologii HTTP existente definite prin protocolul RFC 2616. Ei folosesc GET pentru a prelua o resursă; PUT pentru a schimba starea sau a actualiza o resursă, care poate fi un obiect, fișier sau bloc; POST pentru a crea acea resursă; și Ștergeți-l pentru al elimina
Cu REST, componentele în rețea sunt o resursă la care utilizatorul solicită acces - o casetă neagră ale cărei detalii de implementare nu sunt clare. Toate apelurile sunt apatride; nimic nu poate fi reținut de serviciul RESTful dintre execuții.

**Descriere problemă**
Pentru implementarea cerințelor proiectului am realizat o pagină web în care am implementat API-uri disponibile prin intermediul Google Developers. Așadar, am implementat opțiunea de conectare prin intermediul contului de Gmail, utilizând API-ul pus la dispoziție de Google. De asemenea, pentru aceasta opțiune, am creat separat și un buton de Sign Out pentru a permite utilizatorilor sa se deconecteze de la contul curent și să se poată conecta ulterior cu altul, sau doar pentru a rămâne deconectați din contul de Gmail.
Ulterior, folosind un an alt API oferit de cei de la Google, respectiv Calendar, am realizat o interfață care permite utilizatorului să vizioneze propriile evenimente viitoare, fiind disponibile atât numele evenimentelor, status-ul acestora, data de început, adresa de Gmail a celui care a creat evenimetele respective, data creării acestora, cât și data la care se încheierii lor. 
În final, folosind de asemenea un API de la Google, și anume cel pentru Gmail, am implementat în pagina web etichetele disponibile, acestea fiind principalele mijloace de clasificare și organizare a mail-urilor utilizatorului. O etichetă are o relație de many-to-many cu mail-urile: un singur mail poate avea mai multe etichete aplicate și o singură etichetă poate fi aplicată mai multor mail-uri. Etichetele vin de asemenea cu două clasificări: sistem și utilizator. Etichetele de sistem, cum ar fi INBOX, TRASH sau SPAM, sunt create intern și nu pot fi create, șterse sau modificate. Cu toate acestea, unele etichete de sistem, cum ar fi INBOX, pot fi aplicate sau eliminate din mail-uri. Etichetele utilizatorului pot fi adăugate, șterse sau modificate de către utilizator sau de către o aplicație.

## **Descrierea API-urilor utilizate**
Un prim API folosit de la Google a fost cel pentru a implementa butonul de Sign-In în pagina web. Conectarea prin intermediul Google gestionează fluxul OAuth 2.0 și ciclul de viață al tokenilor, simplificând integrarea cu API-urile Google. Un utilizator are întotdeauna opțiunea de a revoca accesul la o aplicație în orice moment. Pentru a putea folosi acest API, a fost nevoie să îmi configurez un proiect pe Google Developers, de unde am folosit Client ID-ul generat de către proiect, pentru a avea acces la script-urile integrate în program. 
Mai departe, pentru integrarea celor 2 părți: pentru Calendar și Gmail, am avut nevoie de un API pentru Google Calendar, pentru a permite afișarea evenimentelor din calendar. Acest API poate fi integrat cu o varietate largă de limbaje de programare (Java, PHP, .NET, JavaScript, NodeJs, Ruby, Python, dar și Andorid și iOS). Ulterior, am utilizat un alt API pentru Gmail, care permite afișarea și gestionarea etichetelor mail-urilor user-ului autentificat.


## **Flux-ul de date**

Interacțiunile API includ o aplicație cloud care comunică cu un server, serverele comunicând între  ele, iar aplicațiile interacționează cu sistemele de operare. Astfel, protoculul de comunicare al unui API este de a permite dezvoltatorilor să construiască, să se conecteze și să integreze aplicații rapid. 

**Exemple de request/ response**

•	Metoda Get 
API-ul face o cerere prin intermediul funcției listUpcomingEvent() și afișează răspunsul în consolă sub următoarea formă:


![GitHub Logo](/Images/image1.png)


La fel se întâmplă și cu API-ul pentru Gmail, care prin intermediul funcției listLabels() afișează obiectul de tip labels cu atributele corespunzătoare:


![GitHub Logo](/Images/image2.png)


**Metode HTTP**
Metodele folosite în cadrul acestui proiect sunt, în mare parte, metode de tip GET, însă pe lângă acestea există și cele de POST, PUT și DELETE.

**Autentificarea și autorizarea serviciilor utilizate**
Pentru folosirea acestor API s-a folosit integrarea prin intermediul Oauth și s-a dat acces link-urilor de amazon și github, cât și a domeniului de github prin contul personal.


![GitHub Logo](/Images/image3.png)


## **Capturi ecran aplicație**
Ecranul înainte de a se face autentificarea prin Google: 


![GitHub Logo](/Images/image4.png)


Selectarea unui cont de Google:


![GitHub Logo](/Images/image5.png)


Extragerea datelor în urma autentificării și popularea tabelelor:

•	Tabelul care utilizează Google Calendar API:


![GitHub Logo](/Images/image6.png)


•	Tabelul care folosește Gmail API:


![GitHub Logo](/Images/image7.png)


Buton Sign Out:


![GitHub Logo](/Images/image8.png)


## **Referințe**

•	https://developers.google.com/

•	https://searchapparchitecture.techtarget.com/definition/RESTful-API

