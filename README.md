# AXI RPA

AXI RPA Power Automate oplossing.

## Stromen
1. Installeren Flows en Parameters
2. HTTP - Opslaan Parameters
3. HTTP - Start Flow

### 1. Installeren Flows en Parameters
Deze flow kan direct gestart worden en installeert de stamgegevens die vereist zijn voor het uitvoeren van stromen gedistribueerd door AXI.

### 2. HTTP - Opslaan Parameters
Maak parameters aan op basis van een HTTP POST verzoek.
De combinatie van flow en parameter moeten voorkomen in de volgende tabel van Flows en Parameters.

#### HTTP Body:
```
{
    "Parameters": [
        {
            "Name": "<Naam van parameter>",
            "Value": "<Waarde van parameter>"
        },
        ...
    ],
    "Config": {
        "Flowname": "<Naam van Flow>",
        "Username": "<Gebruikersnaam>",
        "Endpoint": "<URL van endpoint>"
    }
}
```

### 3. HTTP - Start
Start een flow voor een bepaalde gebruiker.
De aangevraagde Flow dient voor te komen in de tabel van Flows en Parameters.
Voor elke combinatie van parameter en gebruiker dient een waarde te zijn opgeslagen. Gebruik hiervoor stroom 2: "HTTP - Opslaan Parameters".

#### HTTP Body:
```
{
    "Config": {
        "Flowname": "<Naam van Flow>",
        "Username": "<Gebruikersnaam>",
        "Endpoint": "<URL van endpoint>"
    }
}
```

## Flows en Parameters
Alle combinaties van Flows en Parameters.

|Flow|Parameter|
|----|---------|
|Betaalopdracht|Dagboek|
|Betaalopdracht|Betaaldatum|
|Betaalopdracht|SEPABetaling|
|Betaalopdracht|OpnameSEPATransactieNietInEuro|
|Betaalopdracht|Valuta|
|Betaalopdracht|KlantOfLeverancier|
|Betaalopdracht|AlleBetaalgroepen|
|Betaalopdracht|EnkelBetaalgroep|
|Betaalopdracht|AlleKlantenOfLeveranciersGroepen|
|Betaalopdracht|EnkelKlantenOfLeveranciersgroep|
|Betaalopdracht|AlleKlantenOfLeveranciers|
|Betaalopdracht|EnkelKlantOfLeverancier|
|Betaalopdracht|Goedgekeurd|
|Betaalopdracht|Betaalverbod|
|Betaalopdracht|VanafDocumentdatum|
|Betaalopdracht|TotEnMetDocumentdatum|
|Betaalopdracht|VanafVervaldatum|
|Betaalopdracht|TotEnMetVervaldatum|
|Betaalopdracht|UitsluitenCreditsaldo|
|Betaalopdracht|EnkelDocumentenOpTijdVoorKorting|
|Betaalopdracht|AlleDagboeken|
|Betaalopdracht|EnkelTransactiesUitDagboek|