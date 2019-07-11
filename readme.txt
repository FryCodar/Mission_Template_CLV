
Dies ist eine kurze Beschreibung zur Verwendung des Templates.

1.) Erstellt man eine Mission, setzt einen Spieler auf die Karte und setzt dann einen leeren Marker auf die Karte mit dem Namen
    "respawn_west"
    Dieser Marker stellt den Respawn des Spielers dar und sollte mit bedacht gewählt werden!


2.) Dann man alle Dateien und Ordner des Templates und fügt diese in den Missionsordner ein.
    ACHTUNG!!! - aufpassen das man nicht versehentlich Ordner die im Missionsordner den gleichen Namen tragen wie im Template damit überschreibt.

Einstellungen:
---------------
_____________________________________________________________________________________________
Name der Mission eintragen:

In der "description.ext" kann man durch öffnen bei -

onLoadName = "MSOT-Template"; // den Namen der Mission eintragen
author = "MSOT-Fry";  // den Ersteller der Mission
OnLoadMission = "a MSOT Produktion"; // Zusatzinformationen
// loadScreen =  "pic\Titel.paa";  // Pfad zum Bild das beim Laden angezeigt wird

eintragen und anpassen!
_____________________________________________________________________________________________
Einstellungen des Templates vornehmen:


In der "msot_template_settings.sqf" kann
man Feinheiten zu der Mission einstellen, dort sind alle Parameter selbst erklärend und mit Default-Werten versehen,
also wie Sie zur Veröffentlichung der Mission eingestellt werden sollten (DEBUG-MODUS  zbsp sollte nicht angeschalten sein).

_____________________________________________________________________________________________

Missionsspezifische Einstellungen (wärend der Lauftzeit - Missionsparameter):


In dem Ordner "params" befindet sich eine Datei "params.hpp"

Dort kann man bei jeder "class" anhand der

default = ...;

Werte einstellungen vornehmen, wie Sie zu Beginn der Mission voreingestellt sein soll.
