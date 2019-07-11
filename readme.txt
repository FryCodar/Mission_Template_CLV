
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

Werte Einstellungen vornehmen, wie Sie zu Beginn der Mission voreingestellt sein soll.

zum Beispiel:

class play_faction
{
  title = "Gegen welche Fraktion willst du spielen:";
  texts[] = {"CSAT","CSAT Pazifik","FIA Red","AAF","FIA Green","Syndicat"};
  values[] = {1,2,3,4,5,6};
  default = 1; // mit diesem Wert können die Voreinstellungen der Mission geändert werden
};

hierbei muss man wissen, das "texts[]" die gleiche Anzahl von Einträgen wie "values[]" hat, die durch ein Komma getrennt sind!
 Dabei steht der erste Wert von "texts[]" für den erste Wert in "values[]"

 => "CSAT" = 1, "CSAT Pazifik" = 2, "FIA Red" = 3 usw.


Noch ein Beispiel:

class mission_difficulty
{
  title = "Schwierigkeitsgrad:";
  texts[] = {"Easy","Normal","Hard","Ultra"};
  values[] = {0,2,3,4};
  default = 2;
};

=> "Easy" = 0, "Normal" = 2, "Hard"= 3, "Ultra" = 4

Also wenn man in der Lobby die Parameter einstellt, so wird immer der dazugehörige Wert aus "Values[]" an das Script weitergegeben
______________________________________________________________________________________________


Kleine Template Features( in die Init des Objekts einfügen):

Schnelles Reisen -

this addAction ['<t color=''#f000ff00''>Schnelles Reisen</t>',{createDialog "MSOT_TRAVEL_TABLE";},(1),8,false,true,"","_this == player"];


Arsenalbox -

this addAction ['<t color=''#f000ff00''>Open Arsenal</t>',{[] spawn MSOT_arsenal_fnc_initArsenal},[],1.5,true,true,"","true",5];


Briefing Text -

Bitte in der "briefing.sqf" den gewünschten Text zwischen den "" einfügen, dieser wird nach Start der Mission automatisch geladen
