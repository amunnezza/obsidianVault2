Visti tutti i nuovi arrivati, mi spertico in un post per spiegare cos'è Bitcoin, nella speranza che sia utile per loro.
Prima di parlare di Bitcoin vale la pena menzionare il problema che risolve. 
Come si garantisce il fatto che un soldo non sia spendibile due volte?
Nella storia dell'umanità  questo problema è stato risolto in 2 modi:
1) i soldi sono costituiti da qualcosa di fisico, una moneta, una banconota, difficile da copiare e pertanto una volta trasferito il soldo non appartiene più alla persona che lo ha speso;
2) nel mondo digitale il primo metodo fallisce per la facilita di copia dei dati  (i soldi sono un numero in un database) e dunque come si fa? 
Si mette in mezzo un fiduciario che garantisce la regolarità  delle transazioni: la banca.
Di fatto nessuno nel mondo digitale oggi può più spendere i soldi, sono solo gli intermediari 
a permettere gli acquisti perchè dipendiamo da loro per la catena di fiducia.
Satoshi Nakamoto ha risolto questo problema in un terzo modo: Bitcoin (e per questo è un genio).
Che dice Satoshi? Dice: facciamo un registro pubblico, dove chiunque possa andare a scrivere 
la transazione e chiunque possa andare a leggere, in questo modo uno non può barare.
Se io ho un soldo e lo voglio dare a Franco dentro al registro scrivo: Emanuele da a Franco 1 soldo
 (bitcoin) firmato Emanuele.
Chiunque può leggere che io ho dato il bitcoin a Franco e quindi io non posso dire più di avere quel bitcoin.
Questo sistema è molto semplice e funziona, tuttavia io posso essere un criminale.
 Di giorno io do un bitcoin a Franco in cambio di una merce (per esempio un computer) 
 e lo scrivo nel registro pubblico. Poi di notte vado nel registro e cancello la transazione, per cui 
 il bitcoin di fatto non mi ha mai lasciato ma io ho il computer "comprato" da Franco, di fatto derubandolo.
Nel mondo normale si vedrebbe la cancellazione nel registro, ma nel mondo digitale se si cancella un dato non si lascia traccia. 
Allora è necessario che una volta scritta una cosa nel registro sia impossibile modificarla. E questo è tutto il casino che sta dietro a Bitcoin.
Per fare questo immaginiamo che le pagine del registro siano fatte da una carta speciale che vada presa nella foresta della Papuasia minore. 
Tale carta richiede un trattamento specifico per diventare pagina, e tutto questo lavoro Ã¨ molto molto complicato.
Una volta creata una di queste pagine si possono scrivere dentro le transazioni e questa pagina viene incollata nel registro alla pagina precedente.
Se qualcuno vuole alterare la pagina la deve staccare, riscrivere le transazioni cancellando quella 
che vuole alterare e rincollare la nuova pagina, ma non puÃ² farlo come vuole, deve usare quella carta speciale della Papuasia minore che deve andare a  procurarsi di persona impiegando un sacco di tempo. 
Non solo, siccome ogni pagina Ã¨ attaccata alla precedente, quando stacca quella che interessa a lui per manipolarla, nel riattaccarla deve rifare anche tutte le pagine successive, impiegando un sacco di tempo perchÃ¨ tutte vanno rifatte con la carta speciale.
Ora si capisce che fare una pagina non Ã¨ un lavoro facile, richiede tempo e denaro, quindi perchÃ¨ qualcuno deve mettersi a fare sto lavoraccio per far funzionare il registro?
PerchÃ¨ chi fabbrica una nuova pagina ha il diritto di scriverci dentro una transazione particolare 
dove si assegna automaticamente dei bitcoin (12.5 oggi).
Quindi ha un premio per aver fatto la pagina. 
Non solo, chi vuole scrivere la propria transazione dentro la pagina deve pagare una piccola
 (oggi grande ma la risolveremo) commissione per avere la propria transazione inserita in quella pagina.
Questo meccanismo fa si che ci siano persone volenterose che realizzino nuove pagine del registro ogni giorno, anzi ogni 10 minuti. Includendo tutte le transazioni che noialtri facciamo ogni giorno.
Siccome ogni volta che una nuova pagina viene creata la persona che la crea prende 12.5 bitcoin, 
il numero di bitcoin totale circolante Ã¨ in aumento. 
Ogni 4 anni tale numero si dimezza, fra tre anni e mezzo sarÃ  quindi di 6.25 bitcoin, fino ad andare a zero. 
Quindi il numero totale di bitcoin Ã¨ limitato e questo limite sarÃ  di 21 milioni.
Per allinearsi alla terminologia corretta faccio le debite traduzioni:
- il registro ï¿½ la blockchain;
- le pagine del registro sono i blocchi;
- le persone che creano i nuovi blocchi sono i miners;
Quindi quando facciamo una transazione in bitcoin, creiamo una scritta del tipo: Emanuele da a Franco 1 bitcoin, firmato Emanuele e la mettiamo in un 
posto che si chiama mempool. Il miner lavora per creare il blocco e quando lo crea pesca le transazioni dalla mempool e le inserisce nel blocco 
attaccando il blocco alla blockchain. 
La catena continuerï¿½ con altri blocchi e piï¿½ ne vengono attaccati maggiore ï¿½ la nostra sicurezza che quella transazione non potrï¿½ piï¿½ essere manipolata 
perchï¿½ se cambiano il blocco dove si trova la nostra transazione si devono cambiare tutti i blocchi successivi.
Visto che il post ï¿½ giï¿½ chilometrico lo fermo qui e se interessa ne posso fare un altro su cosa sono i wallet e come funzionano in un post successivo.
#spiegone

Per la serie di Bitcoin per tutti parliamo di wallet.
Va bene il wallet su blockchain? Su coinbase? E ledger? E i paper pallet? E il wallet di mio cuggino mio cuggino?
Per capire cos'ï¿½ un wallet e come usarlo ï¿½ necessario prima di tutto capire come funziona Bitcoin e la sua blockchain. Una spiegazione la trovate qui: https://www.facebook.com/groups/bitcoinitalia/permalink/1561890950548961/ e se non l'avete letta ï¿½ meglio che lo facciate prima di proseguire nella lettura.
Se avete capito come funziona Bitcoin ormai saprete un concetto fondamentale: i bitcoin esistono solo ed esclusivamente dentro i blocchi custoditi dalla blockchain (che non ï¿½ il sito blockchain.info, quello ha solo rubato il nome dalla tecnologia di Bitcoin).
Questo significa che un wallet non "contiene" nessun bitcoin e allora che cos'ï¿½ un wallet?
Quando un utente di bitcoin opera una transazione scrive, nella blockchain, una cosa tipo: Emanuele dï¿½ a Franco 1 bitcoin, firmato Emanuele.
Il wallet ï¿½ un software che si occupa di preparare questa scrittura e inviarla ad un nodo, il quale la replicherï¿½ agli altri nodi fino a quando un miner non la inserirï¿½ in un blocco rendendola effettiva ed immutabile per sempre.
Quindi un wallet deve saper comunicare con i nodi, e deve saper preparare la scrittura con indirizzo di sorgente (Emanuele), indirizzo di destinazione (Franco) importo (1 bitcoin) e firma (firmato Emanuele).
Di queste informazioni una ï¿½ molto piï¿½ importante delle altre, ed ï¿½ ovviamente la firma. Per capirci meglio immaginate che il wallet prepari la transazione scrivendola su un foglio che inserisce in una busta. La firma ï¿½ un bollo ci ceralacca che sigilla la busta con le vostre credenziali rendendola impossibile da falsificare. La busta viene poi presa dal miner e messa nei blocchi della blockchain.
Il timbro che imprime sulla ceralacca il vostro sigillo si chiama chiave privata ed ï¿½ un numero molto lungo contenuto dentro al wallet. Se qualcuno entra in possesso di tale numero, puï¿½ siglare una transazione al posto vostro e per la blockchain questa cosa ï¿½ perfettamente valida, non potrï¿½ distinguere il ladro da voi.
Se questo ï¿½ chiaro, allora possiamo dire che la sicurezza di un wallet dipende da quanto bene viene protetta la chiave privata (il sigillo). Personalmente io distinguo tre possibili tipi di sicurezza.
Tipo 1: estremamente insicuro. Qualsiasi wallet gestito da un sito web. Quindi tutti gli exchange, tutti i wallet per cui dovete loggarvi su un sito per vedere i vostri coin. Perchï¿½ sono insicuri? Perchï¿½ la vostra chiave privata risiede sul computer di chi gestisce il sito web, e voi non ne siete i possessori. Come ho spiegato, se uno ha la vostra chiave privata puï¿½ firmare per voi e prendersi tutto. Questo puï¿½ avvenire perchï¿½ fra chi gestisce il sito web c'ï¿½ una persona disonesta, oppure il sito web stesso puï¿½ essere o diventare disonesto (tipo Mt.Gox) o puï¿½ essere attaccato con successo da qualcuno che riesce a rubare le chiavi private. Non importa quante garanzie vi danno, di fatto la chiave privata non ï¿½ da voi, quindi dovete considerarla un po' di tutti, come i vostri coin.
Tipo 2: mediamente insicuro. Un qualunque wallet che risieda su un vostro dispositivo (computer o telefonino) che collegate regolarmente ad internet. Questa soluzione ï¿½ migliore rispetto al Tipo 1, ma sempre passibile di ruberia. In che modo? Beh dovete considerare che i vostri coin potrebbero valere molto in futuro e molte persone saranno interessate ad essi, quindi verranno creati dei virus appositi che infetteranno i computer ed i telefoni in cerca di wallet. Una volta identificato un wallet, anche se super sicuro, crittato e protetto da password, il virus rimarrï¿½ con pazienza ad aspettare la prima occasione in cui lo userete, leggendo le vostre password mentre le digitate (spiando la tastiera o il touch screen) e di fatto rubando la chiave privata che verrï¿½ mandata a chi vi sta spiando.
Tipo 3: piuttosto sicuro. Un wallet la cui chiave privata risiede da qualche parte offline, disconnessa da internet e che non andrï¿½ mai online. Questo sistema ï¿½ il modo migliore per assicurare valido livello di sicurezza. Alcune persone stampano la chiave privata (su carta, legno, alluminio) e non la tengono nemmeno su un dispositivo digitale, mentre altre utilizzano un computer solo per tenere la chiave privata del wallet. Per esempio i vari wallet hardware che potete comprare online (tipo il Ledger) non sono altro che dei computerini che gestiscono una chiave privata da tenere offline.
Quando si usa un wallet di questo tipo ï¿½ possibile avere un wallet collegato a internet (senza chiave privata ovviamente) che genera gli indirizzi per ricevere le transazioni e crea le transazioni quando volete inviare un bitcoin. In quest'ultimo caso perï¿½ il wallet richiederï¿½ di firmare offline la transazione, quindi dovrete spostarla in qualche modo (QR code, chiavetta USB o altro) dal computer online a quello offline per firmarla e poi riportare la transazione firmata online per essere inviata ai nodi.
Tutti i wallet vanno bene a seconda dei casi: per esempio se fate trading giornaliero usare un wallet con la chiave offline ï¿½ tedioso e lento e puï¿½ essere meglio lasciare i coin sul sito dell'exchange. Se volete comprarvi il cappuccino la mattina, un wallet sul telefonino ï¿½ ottimo per gestire i soldi per le spese di tutti i giorni (quando le fee ce lo permetteranno). Se invece pensate di tenere i bitcoin per il lungo termine, un wallet offline ï¿½ la scelta migliore.
In qualunque caso il suggerimento ï¿½ sempre lo stesso: domandatevi prima di tutto in che categoria si colloca il wallet che volete utilizzare (tipo 1, 2 o 3) e datevi una risposta chiara di cosa state facendo. Se non siete sicuri o non avete capito ï¿½ meglio informarsi di piï¿½ perchï¿½ rischiate di mettere in pericolo i vostri soldi.


Like
Show more reactions
