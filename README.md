# Willkommen bei Versuche!

**Servus**


# Roulette 🎰

Roulette ist ein sehr bekanntes **Casino-Spiel** in dem man viel Geld gewinnen, aber auch verlieren kann. Man setzt auf eine Farbe und es besteht eine **50/50 Chance** zu gewinnen und seinen Einsatz doppelt zurück zu bekommen.
Es gibt jedoch einen Trick, der -leider- **verboten** ist:
Man setzt einen **bestimmten Betrag** auf eine Farbe (Bsp.: Rot, 50€). Gewinnt man jetzt bekommt man den Einsatzbetrag doppelt zurück (100€) und man setzt auf die andere Farbe und wieder den Anfangseinsatz (Schwarz, 50€). Verliert man nun, setzt man auf die selbe Farbe den **Doppelten Anfangseinsatz**(100€). Gewinnt man nun wieder hat man 50€ verloren, aber 100€ gewonnen, also macht man **sicher** Gewinn.
**Ausser** man hat **extremes** Pech und verliert so oft hintereinander, dass man kein Geld mehr hat.
Da ich mich schon seit langem dafür interessiere wie gut dieser Trick wirklich ist, hab ichs einfach mal mit einem simplen **Code** nachsimuliert (Code findest du oben)

## Anfangsguthaben 1000€, Einsatz 50€

Hier bin ich auf ein Problem gestoßen:
ich bekomme immer das selbe Ergebnis. Falls du weisst wo der Fehler liegt schreib mir Bitte.
```sh
public class Main<counter> {  
    public static void main(String[] args) {  
        Random zufall = new Random();  
 int farbe;  
 int counter = 0;  
 int guess = 0;  
 int guthaben = 1000;  
 int einsatz = 50;  
 int mostm = 1000;  
 while ((guthaben > 0) && (guthaben < 1000000)) {  
            farbe = zufall.nextInt(1);  
  counter = counter + 1;  
  
  guthaben = guthaben - einsatz;  
 if (farbe == guess) {  
                guthaben = guthaben + 2 * einsatz;  
  einsatz = 50;  
  guess = zufall.nextInt(1);  
 if (guthaben > mostm) {  
                    mostm = guthaben;  
  }  
  
            }  
             else if ((farbe == 1) && (guess == 0)) {  
                einsatz = einsatz * 2;  
  } else if ((farbe == 0) && (guess == 1)) {  
                einsatz = einsatz * 2;}  
  
  
            System.out.println("Guthaben: "+guthaben);  
  }  
        System.out.println("-----------------------");  
  System.out.println("Simulation ended");  
  System.out.println("-----------------------");  
  System.out.println("Spieldauer: "+counter+" Runden");  
  System.out.println("Meistes Geld: "+mostm+" €");  
  }  
}
```
Danke!!

