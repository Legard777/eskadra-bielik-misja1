# Eskadra Bielika Misja1 -- Biała Podlaska

## Instrukcja certyfikacji

Poniższa instrukcja pozwala na szybkie pobranie informacji o usługach Cloud Run wymaganych do certyfikacji.

### Komenda

Skopiuj i wykonaj poniższą komendę w terminalu (Cloud Shell):

> [!IMPORTANT]
> Wynik komendy skopiuj do schowka i wklej do formularza certyfikacji.
>
> Zobacz wideo, które pokazuje jak to należy zrobić

<video src="LINK" controls="controls" style="max-width: 730px;"></video>
![name](link)

```bash
echo -e "\n=== START KOPIOWANIA TEKSTU ===" && \
echo -e "\n=== INFORMACJE O PROJEKCIE I USŁUGACH ===" && \
echo "Projekt: $(gcloud config get-value project)" && \
gcloud run services list \
  --filter="metadata.name:ollama-bielik-v3 OR metadata.name:adk-agents" \
  --format="table(metadata.name,status.url,metadata.creationTimestamp,status.lastTransitionTime,metadata.labels)" && \
echo -e "\n=== STOP KOPIOWANIA TEKSTU ==="
```

### Opis działania i wyniku

Powyższa komenda wykonuje następujące czynności:
**Wyświetlenie informacji (`gcloud run services list`)**:
*   Filtruje usługi Cloud Run, ograniczając wynik tylko do usług o nazwach `ollama-bielik-v3` oraz `adk-agents`.
*   Prezentuje dane w formie tabeli zawierającej:
    *   **SERVICE**: Nazwa usługi.
    *   **URL**: Adres URL usługi.
    *   **CREATION**: Data utworzenia usługi.
    *   **LAST DEPLOYED**: Data ostatniej modyfikacji (wdrożenia).
    *   **LABELS**: Etykiety przypisane do usługi.
*   Dodatkowo wyświetla nazwę projektu na początku sekcji informacyjnej.
