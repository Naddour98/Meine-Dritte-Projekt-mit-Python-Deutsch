# Meine-Vierte-Projekt-mit-Python-Deutsch
Vorhersage von Nutzerbindung für die Navigations-App Waze anhand historischer Aktivitätsdaten. Umfasst EDA, Feature-Engineering und den Vergleich verschiedener Machine-Learning-Modelle inklusive Hyperparameter-Tuning. Auf Deutsch.


## Nutzung des Codes
Um den Code auszuführen und eigene Analysen durchzuführen, gehe wie folgt vor:
1. Repository klonen
2. Virtuelle Umgebung erstellen und aktivieren
3. Abhängigkeiten installieren **pip install -r requirements.txt**
4. Notebook starten: **jupyter notebook main_file.ipynb**


## Überblick über das Geschäftsszenario
Waze ist eine Navigations-App, die ihren Nutzern Echtzeitinformationen zu Verkehr, Unfällen und Routenalternativen bietet. Die Plattform lebt von einer aktiven Community, die kontinuierlich Daten zu Verkehrsbedingungen beiträgt. Für das Unternehmen ist es entscheidend, die Nutzerbindung zu verstehen, da regelmäßige Nutzung direkt mit der Genauigkeit der Verkehrsdaten und damit mit dem Mehrwert für alle Nutzer zusammenhängt.

In diesem Szenario wird ein Datensatz betrachtet, der Informationen zu monatlicher Aktivität (z. B. Anzahl der Fahrten oder gefahrene Kilometer) sowie kumulativen Kennzahlen seit der Registrierung enthält. Ziel ist es, Muster zu identifizieren, die auf eine Abwanderung (Churn) oder fortgesetzte Nutzung hinweisen, um gezielte Maßnahmen für Nutzerbindung und Marketing entwickeln zu können.


## Arbeitsplan
1. Planung
- Identifizieren von Variablen
- Importieren der erforderlichen Pakete und Module
- Untersuchen der Daten

2. Analyse
- Datenbereinigung
- Durchführen von EDA
    - Grafiken und Figuren erstellen
    - Erste Einblicke gewinnen
- Hypothesentests durchführen

3. Konstruktion
- Feature-Engineering
- Logistische Regressionen-Modelle
- Random-Forest-Modelle
- XGBoost-Modelle
- Refactoring und Eliminierung von Faktoren
- Hyperparameter-Tuning

4. Abschluss


## Datenverständnis
Die verwendeten Daten stammen aus einem fiktiven Projekt zur Analyse von Nutzerdaten der Navigations-App Waze und basieren auf synthetisch erzeugten Aktivitätsinformationen. Der Datensatz umfasst mehrere zehntausend Nutzerdatensätze und enthält Variablen wie Anzahl der Fahrten, gefahrene Kilometer, Aktivitätstage sowie kumulierte Kennzahlen seit der Registrierung.

Die abhängige Variable ist ein binärer Klassifikator (label), der angibt, ob ein Nutzer aktiv geblieben ist oder abgewandert ist (Churn).

Diese Datenstruktur ermöglicht sowohl explorative Analysen als auch den Aufbau von Klassifikationsmodellen (z. B. logistische Regression, Random Forest, XGBoost), um Muster zu erkennen, die auf Nutzerbindung oder Abwanderung hinweisen.


## Variablen definieren / Datenwörterbuch

| Variable                   | Beschreibung                                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------------------------- |
| ID                         | Eindeutige ID für jeden Nutzer im Datensatz                                                                |
| label                      | Zielvariable: Gibt an, ob der Nutzer im Beobachtungsmonat aktiv geblieben ist oder abgewandert ist (Churn) |
| sessions                   | Anzahl der App-Sitzungen des Nutzers während des Beobachtungsmonats                                        |
| drives                     | Anzahl der Fahrten (≥ 1 km) während des Beobachtungsmonats                                                 |
| total_sessions             | Gesamte Anzahl aller App-Sitzungen seit der Registrierung bis zum Ende des Beobachtungsmonats              |
| n_days_after_onboarding    | Anzahl der Tage seit der Registrierung (Onboarding) des Nutzers bis zum Ende des Beobachtungsmonats        |
| total_navigations_fav1     | Gesamte Anzahl der Navigationsvorgänge zu Favorit 1 seit der Registrierung                                 |
| total_navigations_fav2     | Gesamte Anzahl der Navigationsvorgänge zu Favorit 2 seit der Registrierung                                 |
| driven_km_drives           | Insgesamt gefahrene Kilometer während des Beobachtungsmonats                                               |
| duration_minutes_drives    | Gesamtdauer der Fahrten in Minuten während des Beobachtungsmonats                                          |
| activity_days              | Anzahl der Tage, an denen der Nutzer die App im Beobachtungsmonat genutzt hat                              |
| driving_days               | Anzahl der Tage, an denen der Nutzer im Beobachtungsmonat Fahrten durchgeführt hat                         |
| device                     | Gerätetyp, auf dem die App genutzt wird (z. B. Android oder iOS)      


## Fazit
Die erstellten Modelle liefern zwar erste Einblicke in Faktoren, die mit Nutzerabwanderung zusammenhängen, erreichen jedoch keine ausreichende Genauigkeit, um sie in einem Unternehmenskontext einzusetzen.

Nächste Schritte:
- Merkmals-Skalierung und erneute Modellierung mit logistischer Regression bei reduzierter Iterationszahl.
- Erweiterung des Datensatzes um nutzerspezifische Informationen auf Fahrerebene (z. B. Fahrzeiten, geografische Standorte).
- Aufnahme detaillierterer Interaktionsdaten, um ein besseres Verständnis des Nutzerverhaltens innerhalb der App zu gewinnen.
