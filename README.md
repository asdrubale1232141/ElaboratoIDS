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

### Versione 1
```java

class Visita {
    public Visita(String titolo, String descrizione, String keyPoint, MonthDay dataInizio,
                  MonthDay dataFine, Set<DayOfWeek> giorniSettimana, LocalTime oraInizio,
                  Duration durata, boolean serveBiglietto, int minPartecipanti, int maxPartecipanti);

    public Visita(String titolo, String descrizione, String keyPoint, MonthDay dataInizio,
                  MonthDay dataFine, Set<DayOfWeek> giorniSettimana, LocalTime oraInizio,
                  Duration durata, boolean serveBiglietto, int minPartecipanti, int maxPartecipanti,
                  LocalDate data, StatoVisita stato);
}

class TipoVisita {
    public TipoVisita(String titolo, String descrizione, String puntoRitrovo,
                      MonthDay dataInizio, MonthDay dataFine, Set<DayOfWeek> giorniSettimana,
                      LocalTime oraInizio, Duration durata, boolean serveBiglietto,
                      int minPartecipanti, int maxPartecipanti);
}
```
### Versione 2
```java
class Visita {
    public Visita(String titolo, String descrizione, String keyPoint, MonthDay dataInizio,
                  MonthDay dataFine, Set<DayOfWeek> giorniSettimana, LocalTime oraInizio,
                  Duration durata, boolean serveBiglietto, int minPartecipanti, int maxPartecipanti);

    public Visita(String titolo, String descrizione, String keyPoint, MonthDay dataInizio,
                  MonthDay dataFine, Set<DayOfWeek> giorniSettimana, LocalTime oraInizio,
                  Duration durata, boolean serveBiglietto, int minPartecipanti, int maxPartecipanti,
                  LocalDate data, StatoVisita stato);

    public Visita(TipoVisita tv, LocalDate data);
}

class TipoVisita {
    public TipoVisita(String titolo, String descrizione, String puntoRitrovo,
                      MonthDay dataInizio, MonthDay dataFine, Set<DayOfWeek> giorniSettimana,
                      LocalTime oraInizio, Duration durata, boolean serveBiglietto,
                      int minPartecipanti, int maxPartecipanti);
}
```
### Versione 3
```java
class Visita {
    public Visita(String titolo, String descrizione, String keyPoint, MonthDay dataInizio,
                  MonthDay dataFine, Set<DayOfWeek> giorniSettimana, LocalTime oraInizio,
                  Duration durata, boolean serveBiglietto, int minPartecipanti, int maxPartecipanti);

    public Visita(String titolo, String descrizione, String keyPoint, MonthDay dataInizio,
                  MonthDay dataFine, Set<DayOfWeek> giorniSettimana, LocalTime oraInizio,
                  Duration durata, boolean serveBiglietto, int minPartecipanti, int maxPartecipanti,
                  LocalDate data, StatoVisita stato, int nIscritti, Volontario volontario);

    public Visita(TipoVisita tv, LocalDate data, Volontario volontario);
}

class TipoVisita {
    public TipoVisita(String titolo, String descrizione, String puntoRitrovo,
                      MonthDay dataInizio, MonthDay dataFine, Set<DayOfWeek> giorniSettimana,
                      LocalTime oraInizio, Duration durata, boolean serveBiglietto,
                      int minPartecipanti, int maxPartecipanti);
}
```
### Versione 4

```java
class Visita {
    public Visita(String titolo, String descrizione, String keyPoint, MonthDay dataInizio,
                  MonthDay dataFine, Set<DayOfWeek> giorniSettimana, LocalTime oraInizio,
                  Duration durata, boolean serveBiglietto, int minPartecipanti, int maxPartecipanti);

    public Visita(String titolo, String descrizione, String keyPoint, MonthDay dataInizio,
                  MonthDay dataFine, Set<DayOfWeek> giorniSettimana, LocalTime oraInizio,
                  Duration durata, boolean serveBiglietto, int minPartecipanti, int maxPartecipanti,
                  LocalDate data, StatoVisita stato, int nIscritti, Volontario volontario);

    public Visita(TipoVisita tv, LocalDate data, Volontario volontario);
}

class TipoVisita {
    public TipoVisita(String titolo, String descrizione, String puntoRitrovo,
                      MonthDay dataInizio, MonthDay dataFine, Set<DayOfWeek> giorniSettimana,
                      LocalTime oraInizio, Duration durata, boolean serveBiglietto,
                      int minPartecipanti, int maxPartecipanti);
}

```
