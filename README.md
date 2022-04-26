# Neopixel Led Strip

Il controllo della strip led RGB è molto complessa e il produttore offre una libreria di gestione che contiene tutto il codice di controllo necessario.


![This is an image](https://github.com/davidedifilippo/strip_neopixel/blob/main/striscia_led_1.png)

## Inclusione libreria di gestione

Bisogna includere la libreria di gestione del costruttore

    #include <Adafruit_NeoPixel.h>

## Creazione di un oggetto di tipo Adafruit_NeoPixel



    Adafruit_NeoPixel strip = Adafruit_NeoPixel(24, DATA_PIN_OUT, NEO_GRB + NEO_KHZ800);

La chiamata a destra dell'uguale crea un oggetto in memoria per il controllo di un anello di led da 24 elementi.
Bisogna comunicare al costruttore dell'oggetto quale piedino viene utilizzato per inviare indirizzi dei led e i dati da memorizzare per i 3 colori RGB di ogni led.

    const int DATA_PIN_OUT = 6;

Viene infine scelto l'ordine di invio dei Byte dei colori (verde, rosso, blu) e la frequenza di invio dei bit in uscita dal piedino 6 alla striscia. 

## Fase di setup 

Si inizializza la striscia e si scegli la luminosità dei led

    strip.begin();
    strip.setBrightness(255);

dove 255 è la massima luminosità. I cambiamenti hanno effetto solo se si effettua la chiamata:

    strip.show(); 
  
Fase di Loop  
  

    uint32_t c = strip.Color(0, 0, 255); //si crea un numero a 32 bit contenente i 3 Byte del colore rrrrrrrrrrggggggggggbbbbbbbbbb
    strip.setPixelColor(0, c);
    strip.show();
 
 Se si volesse accendere il secondo led della striscia
  
    delay(wait);
    c = strip.Color(0, 0, 255);
    strip.setPixelColor(0, c);
    strip.show();




