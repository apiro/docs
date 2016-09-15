---

copyright:
  years: 2016

---

#	Utilizzo del piano Professional 1 Application
{: #using_mobilefoundation_p2}

Ultimo aggiornamento: 04 agosto 2016
{: .last-updated}

Con il piano Professional 1 Application gli utenti possono creare 1 applicazione mobile con più sistemi operativi.
Dopo che hai creato l'istanza del servizio {{site.data.keyword.mobilefoundation_short}}: Professional 1 Application, leggi la seguente procedura introduttiva al servizio.

## Prerequisiti
{: #prerequisites_p2}

Tieni conto di quanto segue, prima di configurare l'istanza del servizio {{site.data.keyword.mobilefoundation_short}}: Professional 1 Application
* {{site.data.keyword.mobilefoundation_short}}: Professional 1 Application è supportato solo con i piani {{site.data.keyword.Bluemix_notm}} {{site.data.keyword.dashdbshort_notm}}: Enterprise Transactional (con supporto di OLTP).

* Devi avere accesso alle credenziali dell'istanza del servizio {{site.data.keyword.dashdbshort_notm}} prima di poter configurare le impostazioni della tua istanza del servizio {{site.data.keyword.mobilefoundation_short}}.

**Nota**: l'istanza del servizio {{site.data.keyword.dashdbshort_notm}} può esistere in qualsiasi `Spazio` nella tua `Organizzazione` {{site.data.keyword.Bluemix_notm}} o in qualsiasi altra `Organizzazione` a cui hai accesso. Assicurati di disporre delle autorizzazioni per accedere allo `Spazio` dove è presente l'istanza del servizio {{site.data.keyword.dashdbshort_notm}}.


## Aggiunta della connessione al database
{: #configure_dashdb_p2}

###  Prime operazioni
{: #firststeps_p2}

Dopo che hai creato l'istanza del servizio {{site.data.keyword.mobilefoundation_short}}: Professional 1 Application, completa la seguente procedura per iniziare a utilizzarla.

### Impostazione della connessione all'istanza del servizio {{site.data.keyword.dashdbshort_notm}}
{: #connect_dashdb_p2}

Dopo che l'istanza del servizio {{site.data.keyword.mobilefoundation_short}}: Professional 1 Application è stata creata, vedrai la pagina *Panoramica*,
dove dovrai specificare le informazioni di connessione per l'istanza del servizio {{site.data.keyword.dashdbshort_notm}}: Enterprise Transactional.

1. Seleziona l'`Organizzazione` {{site.data.keyword.Bluemix_notm}} dove è presente l'istanza del servizio {{site.data.keyword.dashdbshort_notm}}.

+ Seleziona lo `Spazio`  {{site.data.keyword.Bluemix_notm}} in cui è presente l'istanza del servizio {{site.data.keyword.dashdbshort_notm}}, dall'elenco di spazi disponibili nell'`Organizzazione` selezionata.

**Nota:** se non vedi elencati l'`Organizzazione` e lo `Spazio` in cui è presente l'istanza del servizio {{site.data.keyword.dashdbshort_notm}} controlla di essere un membro di tali `Organizzazione` e `Spazio`.

+ Seleziona il `Nome servizio` {{site.data.keyword.dashdbshort_notm}} e le `Credenziali` per connetterti all'istanza del servizio  {{site.data.keyword.dashdbshort_notm}} esistente.

+  Verifica la connessione all'istanza del servizio {{site.data.keyword.dashdbshort_notm}}: Enterprise Transactional specificata.

+  Fai clic su **Continua**. Questa azione crea le tabelle richieste nell'istanza del servizio database {{site.data.keyword.dashdbshort_notm}} configurato.

**Nota**: non puoi modificare l'istanza del servizio {{site.data.keyword.dashdbshort_notm}} configurata per essere utilizzata dalla tua istanza del servizio {{site.data.keyword.mobilefoundation_short}}. Tuttavia, puoi utilizzare la stessa istanza del servizio {{site.data.keyword.dashdbshort_notm}} tra più istanze del servizio {{site.data.keyword.mobilefoundation_short}}, poiché ogni istanza di {{site.data.keyword.mobilefoundation_short}} crea il proprio schema nell'istanza del servizio  {{site.data.keyword.dashdbshort_notm}} selezionata.

* Dopo pochi secondi, puoi accedere alla pagina `Panoramica` che ti fornisce le esercitazioni e i video per aiutarti a iniziare a lavorare con il servizio  {{site.data.keyword.mobilefoundation_short}}.

## Avvio del server {{site.data.keyword.mobilefirst}}
{: #start_mobilefoundation_p2}

* Per avviare {{site.data.keyword.mfserver_short_notm}}, con le impostazioni predefinite, fai clic su **Avvia server di base**.

* Questa selezione fornisce un {{site.data.keyword.mfserver_long_notm}} con le seguenti impostazioni:
    -  1 GB di memoria. Questa dimensione è sufficiente per lo sviluppo, per delle attività moderate di test e i carichi di lavoro di produzione su piccola scala. 

    -	Il `nome utente` e la `password` ti vengono generati
automaticamente. Disporrai dell'accesso ad essi quando il server è avviato e in esecuzione.

Viene avviato il processo di provisioning del tuo server. Questo processo impiega circa 10 minuti e una finestra di messaggio
indica l'avanzamento di questa operazione. Al suo completamento, viene visualizzato un dashboard
dove puoi vedere:

  -	Lo stato del tuo server in esecuzione (stato, dimensione).

  -	La rotta del server viene creata per te. Utilizza questa rotta nella tua applicazione mobile per collegarti a {{site.data.keyword.mfserver_short_notm}}.

  -	I tuoi `nomeutente` e `password` personali per accedere a {{site.data.keyword.mfp_oc_short_notm}}. La `password` è nascosta. Fai clic sull'icona **Mostra password** per visualizzarla.

*	Fai clic su **Avvia console** per aprire {{site.data.keyword.mfp_oc_short_notm}}.


<!--This console runs inside the container.--> Con la console, puoi gestire le tue applicazioni mobili, gli adattatori e i tuoi dispositivi mobili, utilizzare il tuo server come un backend mobile, inviare notifiche di push e altro ancora.

## Ricreazione del server {{site.data.keyword.mobilefirst}}
{: #recreate_mobilefoundation_p2}

*	Fai clic su **Ricrea** per ricreare il server.

* Questa azione arresta il tuo server esistente e elimina i dati. Viene creata una nuova istanza del server con una versione aggiornata, se disponibile. Il completamento di questa azione richiede
alcuni minuti.

**Nota**: tutti i dati dalla tua istanza del server precedente, comprese le informazioni sulle applicazioni e sugli adattatori, sono memorizzati in modo persistente nell'istanza del servizio {{site.data.keyword.dashdbshort_notm}} configurata; questi dati saranno utilizzati per ricreare il tuo server.

##	Impostazione della configurazione avanzata
{: #using_mfs_advanced_p2}

Utilizza **Avvia server con la configurazione avanzata** dalla pagina `Panoramica` per creare il server con le impostazioni avanzate o personalizzate. Puoi inoltre
aggiornare le impostazioni del server per personalizzare la tua configurazione server facendo clic sulla scheda
**Configurazione**. {{site.data.keyword.mobilefoundation_short}} ti dà l'accesso ad alcune impostazioni avanzate.

*	Dalla scheda **Topologia**, puoi selezionare la dimensione del server e il numero di istanze del server di cui hai bisogno. Il server da 1 GB predefinito è sufficiente per lo sviluppo e test semplici.
  - Seleziona la dimensione corretta per il tuo server sulla base delle tue necessità.

  - **Nodi** visualizza il numero di nodi creati.

      - La {{site.data.keyword.mobilefirst}} Server Farm può essere creata configurando il numero di nodi qui.

Per ulteriori dettagli, consulta la [documentazione di {{site.data.keyword.mobilefoundation_long}} ](https://www.ibm.com/support/knowledgecenter/SSHS8R_8.0.0/wl_welcome.html){: new_window}.