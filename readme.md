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

Die Applikation läuft unter:
https://tagebbbuch-halva2251-buejbaamayfce0d6.switzerlandnorth-01.azurewebsites.net

### Passwort von der lokalen `.env` nach Azure übertragen

Die Datei `.env` steht in der `.gitignore` und gelangt darum nie auf
*github* und auch nicht auf Azure. Das Passwort muss deshalb manuell
in Azure hinterlegt werden:

1. Im Azure-Portal den *App Service* öffnen.
2. Unter **Settings** → **Environment variables** den Reiter
   **App settings** auswählen.
3. Auf **+ Add** klicken und folgende Werte eintragen:
   - Name: `PASSWORD`
   - Value: der Wert aus der lokalen `.env`
4. Mit **Apply** speichern und den Neustart der Applikation bestätigen.

Azure stellt diesen Wert der Applikation als Umgebungsvariable zur
Verfügung. `os.getenv("PASSWORD")` in der `app.py` liest ihn dort
genauso aus wie lokal aus der `.env`.