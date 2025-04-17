# Diagrammi UML delle Classi

- Ogni file SVG rappresenta il diagramma delle classi di una versione del progetto.

# Per una corretta visualizzazione è consigliato NON aprirli direttamente su GitHub, ma seguire questi semplici passaggi:

1. Scarica il file .svg sul tuo dispositivo
   - Clicca su `Download` oppure su `Raw`, poi fai clic destro e scegli "Salva con nome...".

2. Apri il file direttamente con il tuo browser (es. Chrome, Firefox, Edge)  
   - Basta fare doppio clic sul file o trascinarlo in una finestra del browser.

3. Utilizza lo zoom del browser per ingrandire le sezioni che interessano  
    -Se non dovesse zoomare tramite touchpad provare 'CTRL' + '+'  oppure 'CTRL' + '-'  (cmd per macOS).

## Legenda dei caratteri che potrebbero non essere usuali

###  Attributi

| Simbolo Visivo                        | Significato            |
|----------------------------------------|-------------------------|
|  Quadrato vuoto con bordo rosso              | Attributo privato       |
|  Rombo giallo                        | Attributo protetto      |
|  'underscore'nome                                | Attributo statico       |

###  Metodi

| Simbolo Visivo                        | Significato              |
|----------------------------------------|---------------------------|
|  Cerchio verde                       | Metodo pubblico           |
|  Quadrato rosso pieno               | Metodo privato            |
|  'underscore'nomeMetodo()                        | Metodo statico            |
| ' {synchronized}'nomeMetodo()         | Metodo synchronized      |

# Nota UML
Alcuni metodi costruttori delle classi TipoVisita e Visita risultano mal formattati e si riversano negli attributi. Questo è dovuto alla gran quantità di parametri. Di seguito quello che dovrebbero essere

 #### Versione 1
 Classe Visita
  public Visita(titolo: String, descrizione: String, keyPoint: String, dataInizio: MonthDay,
           dataFine: MonthDay, giorniSettimana: Set<DayOfWeek>, oraInizio: LocalTime, durata: Duration, serveBiglietto: 
           boolean, minPartecipanti: int, maxPartecipanti: int)
  public Visita(titolo: String, descrizione: String, keyPoint: String, dataInizio: MonthDay, 
           dataFine: MonthDay, giorniSettimana: Set<DayOfWeek>, oraInizio: LocalTime, durata: Duration, serveBiglietto: 
           boolean, minPartecipanti: int, maxPartecipanti: int, data: LocalDate, stato: StatoVisita)
           
Classe TipoVisita
  public TipoVisita(titolo: String, descrizione: String, puntoRitrovo: String, 
              dataInizio: MonthDay, dataFine: MonthDay, giorniSettimana: Set<DayOfWeek>, oraInizio: LocalTime,
              durata: Duration, serveBiglietto: boolean, minPartecipanti: int, maxPartecipanti: int)
              
 #### Versione 2
 Classe Visita:
   public Visita(titolo: String, descrizione: String, keyPoint: String, dataInizio: MonthDay,
           dataFine: MonthDay, giorniSettimana: Set<DayOfWeek>, oraInizio: LocalTime, durata: Duration, serveBiglietto: 
           boolean, minPartecipanti: int, maxPartecipanti: int)
   public Visita(titolo: String, descrizione: String, keyPoint: String, dataInizio: MonthDay,
           dataFine: MonthDay, giorniSettimana: Set<DayOfWeek>, oraInizio: LocalTime, durata: Duration, serveBiglietto:
           boolean, minPartecipanti: int, maxPartecipanti: int, data: LocalDate, stato: StatoVisita)
   public Visita(tv: TipoVisita, data: LocalDate)
   
 Classe TipoVisita:
   public TipoVisita(titolo: String, descrizione: String, puntoRitrovo: String,
              dataInizio: MonthDay, dataFine: MonthDay, giorniSettimana: Set<DayOfWeek>, oraInizio: LocalTime,
              durata: Duration, serveBiglietto: boolean, minPartecipanti: int, maxPartecipanti: int)
              
 #### Versione 3
 Classe Visita
  public Visita(titolo: String, descrizione: String, keyPoint: String, dataInizio: MonthDay,
           dataFine: MonthDay, giorniSettimana: Set<DayOfWeek>, oraInizio: LocalTime, durata: Duration, serveBiglietto: 
           boolean, minPartecipanti: int, maxPartecipanti: int)
   public Visita(titolo: String, descrizione: String, keyPoint: String, dataInizio: MonthDay, 
           dataFine: MonthDay, giorniSettimana: Set<DayOfWeek>, oraInizio: LocalTime, durata: Duration, serveBiglietto: 
           boolean, minPartecipanti: int, maxPartecipanti: int, data: LocalDate, stato: StatoVisita, nIscritti: int, volontario: Volontario)
   publicVisita(tv: TipoVisita, data: LocalDate, volontario: Volontario)
              
 Classe TipoVisita
   public TipoVisita(titolo: String, descrizione: String, puntoRitrovo: String,
              dataInizio: MonthDay, dataFine: MonthDay, giorniSettimana: Set<DayOfWeek>, oraInizio: LocalTime,
              durata: Duration, serveBiglietto: boolean, minPartecipanti: int, maxPartecipanti: int)
              
 #### Versione 4
 Classe Visita
   public Visita(titolo: String, descrizione: String, keyPoint: String, dataInizio: MonthDay, 
           dataFine: MonthDay, giorniSettimana: Set<DayOfWeek>, oraInizio: LocalTime, durata: Duration, serveBiglietto: 
           boolean, minPartecipanti: int, maxPartecipanti: int)
   public Visita(titolo: String, descrizione: String, keyPoint: String, dataInizio: MonthDay, 
           dataFine: MonthDay, giorniSettimana: Set<DayOfWeek>, oraInizio: LocalTime, durata: Duration, serveBiglietto: 
           boolean, minPartecipanti: int, maxPartecipanti: int, data: LocalDate, stato: StatoVisita, nIscritti: int, volontario: Volontario)
   public Visita(tv: TipoVisita, data: LocalDate, volontario: Volontario)
   
 Classe TipoVisita
   public TipoVisita(titolo: String, descrizione: String, puntoRitrovo: String,
              dataInizio: MonthDay, dataFine: MonthDay, giorniSettimana: Set<DayOfWeek>, oraInizio: LocalTime,
              durata: Duration, serveBiglietto: boolean, minPartecipanti: int, maxPartecipanti: int)
