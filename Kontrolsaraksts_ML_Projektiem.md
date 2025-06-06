# Mašīnmācīšanās (Machine Learning) projekta kontrolsaraksts

Šis kontrolsaraksts var palīdzēt jums vadīt mašīnmācīšanās projektus. Ir astoņi galvenie soļi:

1. **Formulēt problēmu un apskatīt to plašākā kontekstā.**  
2. **Iegūt datus.**  
3. **Izpētīt datus, lai gūtu ieskatu.**  
4. **Sagatavot datus, lai labāk atklātu to iekšējās struktūras mašīnmācīšanās algoritmiem.**  
5. **Izpētīt dažādus modeļus un atlasīt daudzsološākos.**  
6. **Noregulēt (fine-tune) modeļus un apvienot tos labākajā risinājumā.**  
7. **Prezentēt savu risinājumu.**  
8. **Palaist, uzraudzīt un uzturēt sistēmu.**

*Protams, šo kontrolsarakstu var un vajag pielāgot konkrētajam mērķim.*

Pielāgots no: Hands-On Machine Learning, autors Aurélien Géron

---

## 1. Formulēt problēmu un apskatīt plašāku ainu

1. Definējiet mērķi biznesa terminos.  
2. Kā jūsu risinājums tiks izmantots?  
3. Kādi ir pašreizējie risinājumi/apvedceļi (ja tādi ir)?  
4. Kā šī problēma būtu jāformulē? (supervised/unsupervised, online/offline u.c.)  
5. Kā jānovērtē veiktspēja (performance)?  
6. Vai veiktspējas rādītājs ir saskaņots ar biznesa mērķi?  
7. Kāda ir minimālā nepieciešamā veiktspēja, lai sasniegtu mērķi?  
8. Kādas ir līdzīgas problēmas? Vai var izmantot iepriekšēju pieredzi vai rīkus?  
9. Vai ir pieejamas cilvēku zināšanas un ekspertīze?  
10. Kā problēmu atrisinātu manuāli?  
11. Uzskaitiet pieņēmumus, kas līdz šim izteikti.  
12. Ja iespējams, pārbaudiet pieņēmumus.

---

## 2. Iegūt datus

*Piezīme: automatizējiet pēc iespējas vairāk, lai varētu viegli iegūt jaunus datus.*

1. Uzskaitiet, kādi dati nepieciešami un cik daudz.  
2. Atrodiet un dokumentējiet datu avotus.  
3. Pārbaudiet, cik daudz vietas dati aizņems.  
4. Pārbaudiet juridiskās prasības un saņemiet atļaujas, ja nepieciešams.  
5. Iegūstiet piekļuves atļaujas.  
6. Izveidojiet darba vidi (ar pietiekami daudz vietas).  
7. Iegūstiet datus.  
8. Konvertējiet datus formātā, ko var viegli apstrādāt (nemainot pašus datus).  
9. Nodrošiniet, lai sensitīva informācija būtu izņemta vai aizsargāta (piemēram, anonimizēta).  
10. Pārbaudiet datu apjomu un tipu (laika rindas, izlases, ģeogrāfiski u.c.).  
11. Izveidojiet testa datu kopu, atliekiet to malā un vairs neskatieties tajā (nav datu noplūdes!).

---

## 3. Izpētīt datus

*Piezīme: centieties iegūt ieskatu no jomas ekspertiem.*

1. Izveidojiet datu kopiju izpētei (samaziniet apjomu, ja nepieciešams).  
2. Izveidojiet Jupyter piezīmju grāmatiņu (notebook), lai dokumentētu izpēti.  
3. Izpētiet katru atribūtu un tā īpašības:  
   - Nosaukums  
   - Tips (kategorisks, int/float, ierobežots/neierobežots, teksts, strukturēts u.c.)  
   - % trūkstošo vērtību  
   - Troksnis un tā veids (piemēram, anomālijas, noapaļošanas kļūdas)  
   - Lietderīgums uzdevuma veikšanai  
   - Sadales veids (normāla, vienmērīga, logaritmiska u.c.)  
4. Supervizētās mācīšanās (supervised learning) gadījumā identificējiet mērķa mainīgo.  
5. Vizualizējiet datus.  
6. Pētiet korelācijas starp atribūtiem.  
7. Apsveriet, kā problēmu atrisinātu manuāli.  
8. Identificējiet iespējamos noderīgos datu transformācijas paņēmienus.  
9. Identificējiet papildu datus, kas varētu būt noderīgi (atgriezties pie “Iegūt datus”).  
10. Dokumentējiet gūtos atklājumus.

---

## 4. Sagatavot datus

*Piezīmes: strādājiet ar datu kopijām. Rakstiet funkcijas transformācijām, lai tās varētu atkārtoti izmantot un izsekot.*

1. **Notīriet datus:**  
   - Izlabojiet vai izņemiet anomālijas (pēc izvēles).  
   - Aizpildiet trūkstošās vērtības (piemēram, ar 0, vidējo, mediānu) vai dzēsiet rindas/kolonnas.  

2. **Veiciet atribūtu izvēli (feature selection, izvēles gadījumā):**  
   - Noņemiet atribūtus, kas nesniedz noderīgu informāciju.  

3. **Veiciet atribūtu konstruēšanu (feature engineering), ja piemērojams:**  
   - Diskretizējiet nepārtrauktos atribūtus.  
   - Sadaliet sarežģītus atribūtus (piemēram, kategorijas, datumi/laiki).  
   - Pievienojiet daudzsološas transformācijas (piemēram, log(x), sqrt(x)).  
   - Apvienojiet atribūtus jaunās iezīmēs.  

4. **Veiciet atribūtu mērogošanu (feature scaling):**  
   - Standartizējiet vai normalizējiet atribūtus.

---

## 5. Atlasīt daudzsološākos modeļus

*Piezīme: lielu datu kopu gadījumā izmantojiet mazākus apmācības apjomus ātrākai testēšanai.*

1. Apmāciet daudz dažādu modeļu (piemēram, lineārie, SVM, lēmumu koki, neironu tīkli).  
2. Izmēriet un salīdziniet veiktspēju (piemēram, ar N-lokšņu krustvalidāciju – N-fold cross-validation).  
3. Analizējiet katra algoritma svarīgākos mainīgos.  
4. Pētiet kļūdu tipus un ko cilvēks izmantotu, lai no tām izvairītos.  
5. Veiciet ātru atribūtu izvēles/inženierijas kārtu.  
6. Atkārtojiet iepriekš minētos soļus vairākas reizes.  
7. Izvēlieties 3–5 modeļus, kas darbojas labi un rada dažādus kļūdu veidus.

---

## 6. Sistēmas pielāgošana (Fine-tuning)

*Izmantojiet pēc iespējas vairāk datu. Automatizējiet, kad iespējams.*

1. Regulējiet hiperparametrus (hyperparameters) ar krustvalidāciju:  
   - Iekļaujiet datu apstrādes izvēles kā hiperparametrus.  
   - Dodiet priekšroku nejaušai meklēšanai (random search) salīdzinājumā ar režģa meklēšanu (grid search). Ilgām apmācībām apsveriet Bayesa optimizāciju.  

2. Izmēģiniet ansambļu metodes (ensemble methods).  
3. Novērtējiet galīgo modeli uz testēšanas datu kopas, lai noteiktu vispārinājuma kļūdu.

⚠️ **Brīdinājums**: Nepārveidojiet modeli pēc testēšanas datu analīzes — tas var novest pie pārpielāgošanas (overfitting).

---

## 7. Prezentēt risinājumu

1. Dokumentējiet savu procesu un atklājumus.  
2. Izveidojiet skaidru, strukturētu prezentāciju:  
   - Sāciet ar kopējo ainu  
   - Paskaidrojiet, kā risinājums sasniedz biznesa mērķi  
3. Prezentējiet interesantus atklājumus un izaicinājumus.  
4. Uzskaitiet pieņēmumus un ierobežojumus.  
5. Izceliet galvenos atklājumus ar vizuāliem vai atmiņā paliekošiem kopsavilkumiem.

---

## 8. Palaišana!

1. Sagatavojiet sistēmu produkcijas videi (piemēram, integrācija ar datu plūsmām, vienību testi).  
2. Izstrādājiet uzraudzības rīkus:  
   - Noteikt veiktspējas pasliktināšanos laika gaitā  
   - Ja nepieciešams, izmantot cilvēku novērtēšanu  
   - Uzraudzīt ievaddatu kvalitāti  

3. Automatizējiet modeļu pārapmācīšanu ar jauniem datiem.