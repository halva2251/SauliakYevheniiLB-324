# LB 324

## Aufgabe 2

Dieses Projekt verwendet `pre-commit`, um den Code automatisch zu
formatieren und zu testen.

- Bei jedem **commit** wird der Code mit *black* automatisch formatiert.
- Bei jedem **push** werden die Testfälle mit *pytest* ausgeführt. Der
  *push* wird abgebrochen, falls ein Test fehlschlägt.

Damit diese Automatisierungen ausgeführt werden, muss jeder Programmierer
einmalig folgende Befehle im Wurzelverzeichnis des Projekts ausführen:

    pip install pre-commit
    pre-commit install
    pre-commit install -t pre-push

Der zweite Befehl registriert den *commit*-Haken, der dritte den
*push*-Haken. Ohne den dritten Befehl werden die Tests beim *push*
nicht ausgeführt.

## Aufgabe 4
Erklären Sie hier, wie Sie das Passwort aus Ihrer lokalen `.env` auf Azure übertragen.