
# Szczegółowe przypadki użycia

## System sklepu internetowego ViralSquishy

System ViralSquishy jest sklepem internetowym oferującym produkty typu squishy, w tym modele z kategorii owoce, zwierzęta, słodycze oraz zestawy.

Użytkownik może przeglądać ofertę sklepu, wyszukiwać produkty, dodawać je do koszyka oraz składać zamówienia po zalogowaniu na swoje konto.

System umożliwia płatności online poprzez bramkę Stripe, obsługującą m.in. karty płatnicze, BLIK, PayPal oraz Klarna. Dostępne są również dostawy kurierem oraz do Paczkomatu, a także przesyłka za pobraniem.

---

# 1. Wyszukaj produkt

**Aktor główny:** Klient

**Cel:**
Odnalezienie w sklepie internetowym produktu spełniającego określone kryteria, np. nazwy produktu, kategorii lub rodzaju squishy.

## Warunki wstępne

- Klient posiada dostęp do strony internetowej ViralSquishy.
- Sklep internetowy jest dostępny.
- Zalogowanie nie jest wymagane do przeglądania oferty i wyszukiwania produktów.
- Produkty są zapisane w katalogu sklepu.

## Warunki końcowe (sukces)

- System wyświetla listę produktów odpowiadających podanym kryteriom.
- Klient może zobaczyć podstawowe informacje o produkcie:
  - nazwę,
  - cenę,
  - kategorię,
  - krótki opis,
  - dostępność produktu.
- Klient może przejść do szczegółów wybranego produktu.

## Główny przebieg zdarzeń

1. Klient otwiera stronę ViralSquishy.
2. Klient przechodzi do sklepu.
3. Klient wybiera kategorię lub wyszukuje interesujący go produkt.
4. System analizuje podane kryteria.
5. System przeszukuje katalog produktów.
6. System wyświetla pasujące produkty.
7. Klient przegląda wyniki.
8. Klient wybiera konkretny produkt.
9. System wyświetla stronę produktu zawierającą szczegółowe informacje, cenę oraz dostępność.
10. Klient może przejść do dodania produktu do koszyka.

## Przebiegi alternatywne

- **3a. Wybór kategorii** – klient wybiera kategorię, np. „Squishy Owoce”, „Squishy Zwierzęta”, „Squishy Słodycze” lub „Zestawy”. System wyświetla produkty należące do wybranej kategorii.
- **3b. Brak określonego kryterium** – klient przegląda wszystkie dostępne produkty bez stosowania dodatkowych filtrów.
- **5a. Brak wyników** – system informuje klienta, że nie znaleziono produktów spełniających kryteria i umożliwia zmianę wyszukiwania.
- **6a. Produkt niedostępny** – system informuje klienta, że produkt jest aktualnie niedostępny.
- **7a. Klient zmienia kryteria** – klient wraca do listy produktów i wybiera inną kategorię lub wyszukuje inny produkt.

## Przebiegi wyjątkowe

- **E1. Błąd połączenia z serwerem** – system wyświetla komunikat o problemie z załadowaniem produktów i umożliwia ponowienie próby.
- **E2. Błąd systemu katalogowego** – system nie może pobrać danych produktu i wyświetla odpowiedni komunikat.
- **E3. Produkt został usunięty w trakcie przeglądania** – system informuje klienta, że produkt nie jest już dostępny i przekierowuje go do sklepu.

## Powiązania z innymi przypadkami użycia

- **«include» Dodaj produkt do koszyka** – po znalezieniu produktu klient może dodać go do koszyka.
- **«include» Złóż zamówienie** – wyszukanie produktu może prowadzić do jego zakupu.
- **«include» Zarządzaj sklepem** – katalog produktów jest utrzymywany przez administratora.

## Reguły biznesowe

- Każdy produkt musi posiadać nazwę, cenę oraz kategorię.
- Produkt może posiadać określony status dostępności.
- Produkty są organizowane według kategorii dostępnych w sklepie.
- Administrator może wyróżniać wybrane produkty w sklepie.

**Częstotliwość użycia:** Bardzo wysoka – przeglądanie i wyszukiwanie produktów stanowi jeden z podstawowych etapów korzystania ze sklepu.

---

# 2. Dodaj produkt do koszyka

**Aktor główny:** Klient

**Cel:**
Dodanie wybranego produktu do koszyka w celu przygotowania zamówienia.

## Warunki wstępne

- Klient znajduje się na stronie sklepu lub stronie konkretnego produktu.
- Produkt znajduje się w katalogu.
- Produkt jest dostępny w sprzedaży.
- System zna aktualną cenę i dostępność produktu.
- Logowanie nie jest wymagane do dodania produktu do koszyka.

## Warunki końcowe (sukces)

- Produkt zostaje dodany do koszyka.
- System aktualizuje liczbę produktów w koszyku.
- System oblicza aktualną wartość koszyka.
- Klient może przejść do koszyka i kontynuować składanie zamówienia.

## Główny przebieg zdarzeń

1. Klient wyszukuje lub wybiera interesujący go produkt.
2. System wyświetla szczegóły produktu.
3. Klient wybiera liczbę sztuk produktu.
4. Klient wybiera opcję „Dodaj do koszyka”.
5. System sprawdza dostępność wybranej liczby sztuk.
6. System dodaje produkt do koszyka.
7. System aktualizuje wartość koszyka.
8. System informuje klienta o poprawnym dodaniu produktu.
9. Klient może kontynuować zakupy lub przejść do koszyka.
10. W koszyku system wyświetla produkty, ich ilość, ceny oraz łączną wartość zamówienia.

## Przebiegi alternatywne

- **3a. Klient wybiera więcej niż jedną sztukę** – system sprawdza dostępny stan magazynowy i dodaje określoną liczbę produktów.
- **5a. Dostępna jest mniejsza liczba sztuk** – system ogranicza maksymalną liczbę możliwą do dodania do koszyka.
- **9a. Klient kontynuuje zakupy** – produkt pozostaje w koszyku, a klient wraca do katalogu.
- **9b. Klient przechodzi do koszyka** – system otwiera zawartość koszyka i umożliwia rozpoczęcie procesu składania zamówienia.
- **10a. Klient zmienia ilość produktu** – system ponownie oblicza wartość koszyka.

## Przebiegi wyjątkowe

- **E1. Produkt przestał być dostępny** – system nie pozwala dodać produktu i informuje klienta o jego niedostępności.
- **E2. Wybrana liczba sztuk przekracza stan magazynowy** – system informuje klienta o maksymalnej dostępnej liczbie sztuk.
- **E3. Błąd zapisu koszyka** – system informuje klienta o problemie i umożliwia ponowienie operacji.

## Powiązania z innymi przypadkami użycia

- **«include» Wyszukaj produkt** – produkt może zostać znaleziony przed dodaniem go do koszyka.
- **«include» Złóż zamówienie** – zawartość koszyka jest podstawą zamówienia.
- **«include» Zarządzaj sklepem** – administrator zarządza dostępnością produktów znajdujących się w koszyku.

## Reguły biznesowe

- Do koszyka można dodać wyłącznie produkty dostępne w sprzedaży.
- Liczba zamawianych sztuk nie może przekroczyć dostępnego stanu magazynowego.
- Cena produktu obowiązująca przy składaniu zamówienia jest pobierana z aktualnych danych sklepu.
- Koszyk może zawierać wiele różnych produktów.

**Częstotliwość użycia:** Bardzo wysoka – dodanie produktu do koszyka jest podstawowym etapem procesu zakupowego.

---

# 3. Złóż zamówienie

**Aktor główny:** Klient

**Aktor drugorzędny:** System płatności Stripe, firma kurierska/operator Paczkomatów

**Cel:**
Utworzenie zamówienia na wybrane produkty oraz przekazanie danych potrzebnych do jego realizacji i dostawy.

## Warunki wstępne

- Klient posiada aktywne konto w sklepie ViralSquishy.
- Klient jest zalogowany.
- Koszyk zawiera co najmniej jeden produkt.
- Produkty znajdujące się w koszyku są dostępne.
- System jest dostępny.
- Klient posiada dane potrzebne do realizacji zamówienia.

## Warunki końcowe (sukces)

- Zamówienie zostaje zapisane w systemie.
- System nadaje zamówieniu unikalny numer.
- Produkty zostają przypisane do zamówienia.
- Zostaje zapisana wartość zamówienia.
- Zostaje zapisany sposób dostawy.
- Zostają zapisane dane odbiorcy.
- Zamówienie otrzymuje odpowiedni status.
- Klient może przejść do płatności lub wybrać płatność za pobraniem.

## Główny przebieg zdarzeń

1. Klient przechodzi do koszyka.
2. System wyświetla zawartość koszyka.
3. Klient wybiera opcję przejścia do realizacji zamówienia.
4. System sprawdza, czy klient jest zalogowany.
5. Jeśli klient nie jest zalogowany, system prosi o zalogowanie.
6. Klient podaje lub potwierdza dane potrzebne do realizacji zamówienia.
7. Klient wybiera sposób dostawy:
   - kurier,
   - Paczkomat,
   - kurier za pobraniem.
8. System oblicza koszt dostawy.
9. System wyświetla podsumowanie zamówienia.
10. Klient sprawdza poprawność danych.
11. Klient akceptuje zamówienie.
12. System tworzy zamówienie.
13. System nadaje zamówieniu numer.
14. System przekazuje klienta do odpowiedniego procesu płatności lub oznacza zamówienie jako oczekujące na płatność przy odbiorze.
15. Klient otrzymuje potwierdzenie złożenia zamówienia.

## Przebiegi alternatywne

- **6a. Dane klienta są już zapisane na koncie** – system automatycznie uzupełnia formularz.
- **7a. Klient wybiera Paczkomat** – system umożliwia wskazanie odpowiedniego Paczkomatu.
- **7b. Klient wybiera kuriera** – zamówienie zostaje przygotowane do dostawy kurierem.
- **7c. Klient wybiera pobranie** – system zapisuje zamówienie jako płatne przy odbiorze.
- **9a. Klient zmienia dane** – klient może poprawić dane przed ostatecznym zatwierdzeniem.
- **10a. Klient rezygnuje przed zatwierdzeniem** – zamówienie nie zostaje utworzone.

## Przebiegi wyjątkowe

- **E1. Klient nie jest zalogowany** – system blokuje przejście do finalizacji i wymaga zalogowania.
- **E2. Produkt został wyprzedany** – system informuje klienta i nie pozwala na utworzenie zamówienia zawierającego niedostępny produkt.
- **E3. Brak wymaganych danych** – system wskazuje pola wymagające uzupełnienia.
- **E4. Nieprawidłowe dane dostawy** – system odrzuca dane i prosi o ich poprawienie.
- **E5. Błąd systemu podczas tworzenia zamówienia** – system informuje klienta o błędzie i umożliwia ponowienie próby.

## Powiązania z innymi przypadkami użycia

- **«include» Wyszukaj produkt** – klient może rozpocząć zakup od wyszukania produktu.
- **«include» Dodaj produkt do koszyka** – zamówienie jest tworzone na podstawie zawartości koszyka.
- **«include» Opłać zamówienie** – dla płatności przedpłaconych zamówienie wymaga przejścia przez proces płatności.
- **«extend» Zwrot/reklamacja** – po zrealizowaniu zamówienia klient może skorzystać z procedury zwrotu.

## Reguły biznesowe

- Do złożenia zamówienia wymagane jest posiadanie konta i zalogowanie.
- Zamówienie może zostać złożone wyłącznie na dostępne produkty.
- Klient musi podać poprawne dane wymagane do dostawy.
- Dostępne są dostawy kurierem oraz do Paczkomatu.
- Dostępna jest możliwość płatności za pobraniem przy odpowiednim sposobie dostawy.
- Po zatwierdzeniu zamówienia klient nie może samodzielnie anulować zamówienia za pomocą systemu.

**Częstotliwość użycia:** Wysoka – przypadek użycia jest wykonywany przy każdym zakupie zakończonym utworzeniem zamówienia.

---

# 4. Opłać i śledź zamówienie

**Aktor główny:** Klient

**Aktorzy drugorzędni:** Stripe, PayPal, operator płatności, firma kurierska/operator Paczkomatów, Administrator

**Cel:**
Dokonanie płatności za zamówienie oraz umożliwienie systemowi zarejestrowania informacji o płatności i realizacji zamówienia.

## Warunki wstępne

- Klient posiada utworzone zamówienie.
- Zamówienie zawiera co najmniej jeden produkt.
- Klient wybrał sposób dostawy.
- W przypadku płatności online klient ma możliwość dokonania płatności poprzez bramkę Stripe.
- W przypadku pobrania klient wybrał odpowiednią formę dostawy.

## Warunki końcowe (sukces)

- Płatność zostaje poprawnie zarejestrowana lub zamówienie zostaje oznaczone jako płatne przy odbiorze.
- Zamówienie otrzymuje odpowiedni status.
- Administrator może rozpocząć realizację zamówienia.
- Produkty są przygotowywane do wysyłki.
- Po przekazaniu przesyłki przewoźnikowi możliwe jest dalsze przetwarzanie informacji dotyczących dostawy.

## Główny przebieg zdarzeń

1. Klient przechodzi do płatności po złożeniu zamówienia.
2. System przekazuje klienta do bramki płatniczej Stripe.
3. Klient wybiera dostępny sposób płatności.
4. Klient może zapłacić:
   - kartą płatniczą,
   - BLIK,
   - PayPal,
   - Klarna.
5. Stripe przetwarza płatność.
6. System otrzymuje informację o wyniku płatności.
7. W przypadku poprawnej płatności system zmienia status zamówienia.
8. Administrator widzi opłacone zamówienie w panelu administracyjnym.
9. Administrator przygotowuje zamówienie do wysyłki.
10. Zamówienie zostaje przekazane do realizacji dostawy.
11. Klient otrzymuje zamówiony produkt.

## Przebiegi alternatywne

- **3a. Płatność kartą** – klient podaje dane karty, a Stripe przetwarza transakcję.
- **3b. Płatność BLIK** – klient korzysta z kodu BLIK i zatwierdza transakcję.
- **3c. Płatność PayPal** – klient zostaje przekierowany do PayPal w celu autoryzacji płatności.
- **3d. Płatność Klarna** – klient wybiera Klarna i realizuje płatność zgodnie z dostępną metodą.
- **3e. Płatność za pobraniem** – płatność nie jest realizowana online; klient dokonuje zapłaty przy odbiorze przesyłki.
- **9a. Dostawa kurierem** – zamówienie jest przekazywane firmie kurierskiej.
- **9b. Dostawa do Paczkomatu** – zamówienie jest kierowane do wybranego Paczkomatu.

## Przebiegi wyjątkowe

- **E1. Płatność online nie powiodła się** – system informuje klienta o nieudanej płatności i umożliwia ponowienie płatności.
- **E2. Płatność została odrzucona przez operatora** – zamówienie pozostaje nieopłacone.
- **E3. Przerwanie płatności** – klient opuszcza stronę płatności; system nie oznacza zamówienia jako opłaconego.
- **E4. Błąd komunikacji z Stripe** – system nie może potwierdzić płatności i oczekuje na poprawną informację od operatora.
- **E5. Problem z dostawą** – administrator podejmuje działania związane z realizacją przesyłki.
- **E6. Klient chce anulować zamówienie** – system nie udostępnia klientowi samodzielnej funkcji anulowania zamówienia.

## Powiązania z innymi przypadkami użycia

- **«include» Złóż zamówienie** – płatność jest częścią procesu realizacji zamówienia w przypadku płatności z góry.
- **«include» Zarządzaj zamówieniami** – administrator obsługuje zamówienia w panelu administracyjnym.
- **«extend» Zwrot/reklamacja** – po otrzymaniu zamówienia klient może zgłosić zwrot lub reklamację.
- **Powiązanie z Zarządzaj katalogiem** – stan magazynowy produktów jest aktualizowany w związku z realizacją zamówień.

## Reguły biznesowe

- Płatności online są realizowane poprzez bramkę Stripe.
- Dostępne są płatności kartą, BLIK, PayPal oraz Klarna.
- Możliwa jest również płatność za pobraniem.
- Klient nie ma funkcji samodzielnego śledzenia statusu zamówienia na swoim koncie.
- Informacje o realizacji zamówienia są obsługiwane przez system oraz administratora.
- Zamówienie opłacone online może zostać przekazane do realizacji.
- W przypadku pobrania płatność następuje przy odbiorze przesyłki.

**Częstotliwość użycia:** Wysoka – przypadek użycia jest realizowany przy każdym zamówieniu wymagającym płatności lub obsługi dostawy.

---

# 5. Zarządzaj sklepem

**Aktor główny:** Administrator

**Aktor drugorzędny:** Brak

**Cel:**
Zarządzanie ofertą sklepu ViralSquishy, produktami, ich dostępnością, cenami oraz zamówieniami za pomocą panelu administratora.

## Warunki wstępne

- Administrator posiada konto z odpowiednimi uprawnieniami.
- Administrator jest zalogowany do panelu administracyjnego.
- System administracyjny jest dostępny.
- Administrator posiada uprawnienia do zarządzania produktami i zamówieniami.

## Warunki końcowe (sukces)

- Katalog sklepu zawiera aktualne informacje o produktach.
- Administrator może dodawać, edytować i usuwać/ukrywać produkty.
- Ceny produktów są aktualne.
- Stany magazynowe są aktualne.
- Produkty mogą być przypisywane do odpowiednich kategorii.
- Administrator może wyróżniać wybrane produkty w sklepie.
- Administrator może zarządzać zamówieniami.

## Główny przebieg zdarzeń

1. Administrator loguje się do panelu administracyjnego.
2. System weryfikuje dane logowania i uprawnienia administratora.
3. Administrator otwiera panel zarządzania sklepem.
4. Administrator wybiera operację:
   - dodanie produktu,
   - edycja produktu,
   - usunięcie/ukrycie produktu,
   - zmiana ceny,
   - zmiana dostępności,
   - zmiana stanu magazynowego,
   - przypisanie produktu do kategorii,
   - wyróżnienie produktu,
   - obsługa zamówień.
5. W przypadku dodania produktu administrator wprowadza dane produktu.
6. System waliduje wprowadzone dane.
7. Administrator zapisuje produkt.
8. System dodaje produkt do katalogu.
9. W przypadku edycji administrator wyszukuje istniejący produkt.
10. Administrator zmienia wybrane informacje.
11. System zapisuje zmiany.
12. W przypadku zmiany stanu magazynowego system aktualizuje dostępność produktu dla klientów.
13. Administrator może oznaczyć produkt jako wyróżniony.
14. System prezentuje wyróżniony produkt w odpowiednim miejscu sklepu.
15. Administrator może przejść do zarządzania zamówieniami.
16. Administrator przegląda nowe zamówienia.
17. Administrator obsługuje realizację zamówień.
18. System zapisuje wszystkie wykonane operacje.

## Przebiegi alternatywne

- **5a. Dodanie nowego produktu** – administrator podaje m.in. nazwę, opis, cenę, kategorię, zdjęcia oraz stan magazynowy.
- **5b. Dodanie produktu do kategorii** – administrator przypisuje produkt do kategorii, np. Owoce, Zwierzęta, Słodycze lub Zestawy.
- **9a. Edycja produktu** – administrator zmienia dane istniejącego produktu.
- **12a. Zwiększenie stanu magazynowego** – administrator zwiększa liczbę dostępnych sztuk.
- **12b. Zmniejszenie stanu magazynowego** – administrator zmniejsza liczbę dostępnych sztuk, np. po sprzedaży lub stwierdzeniu braku produktu.
- **13a. Wyróżnienie produktu** – administrator oznacza produkt jako wyróżniony, dzięki czemu może pojawić się w sekcji produktów wyróżnionych/bestsellerów.
- **14a. Usunięcie wyróżnienia** – administrator wyłącza wyróżnienie produktu.
- **16a. Obsługa zamówienia** – administrator sprawdza dane zamówienia, płatność, produkty oraz sposób dostawy.
- **17a. Zwrot/reklamacja** – administrator obsługuje zgłoszenie klienta dotyczące zwrotu lub reklamacji.

## Przebiegi wyjątkowe

- **E1. Nieprawidłowe dane logowania** – system odrzuca próbę logowania do panelu administracyjnego.
- **E2. Brak wymaganych danych produktu** – system nie pozwala zapisać produktu i wskazuje brakujące pola.
- **E3. Nieprawidłowa cena** – system odrzuca zapis i wymaga poprawienia ceny.
- **E4. Nieprawidłowy stan magazynowy** – system odrzuca niepoprawną wartość.
- **E5. Próba usunięcia produktu wykorzystywanego w zamówieniu** – system może zablokować fizyczne usunięcie produktu i zamiast tego umożliwić jego ukrycie lub oznaczenie jako niedostępnego.
- **E6. Brak dostępu administratora** – system blokuje dostęp do panelu.
- **E7. Błąd zapisu danych** – system informuje administratora o problemie i umożliwia ponowienie operacji.
- **E8. Brak produktu na magazynie** – system zmienia jego dostępność i nie pozwala klientom złożyć zamówienia na niedostępny produkt.

## Powiązania z innymi przypadkami użycia

- **«include» Wyszukaj produkt** – administrator może wyszukiwać produkty w celu ich edycji.
- **Wpływa na Dodaj produkt do koszyka** – zmiana dostępności produktu wpływa na możliwość dodania go do koszyka.
- **Wpływa na Złóż zamówienie** – aktualny stan magazynowy określa, czy klient może zamówić produkt.
- **«include» Zarządzaj zamówieniami** – panel administratora umożliwia obsługę złożonych zamówień.
- **«extend» Zwrot/reklamacja** – administrator obsługuje zgłoszenia klientów dotyczące zakupionych produktów.

## Reguły biznesowe

- Tylko administrator posiada dostęp do panelu administracyjnego.
- Administrator może dodawać nowe produkty.
- Administrator może edytować istniejące produkty.
- Administrator może zarządzać cenami produktów.
- Administrator może zarządzać stanem magazynowym.
- Administrator może przypisywać produkty do kategorii.
- Administrator może wyróżniać produkty w sklepie.
- Produkt niedostępny nie powinien być możliwy do zamówienia.
- Produkty powiązane z istniejącymi zamówieniami nie powinny być bezpowrotnie usuwane bez odpowiedniej kontroli; bezpieczniejszym rozwiązaniem jest ich ukrycie lub oznaczenie jako niedostępnych.
- Administrator ma możliwość obsługi zamówień oraz zgłoszeń klientów.

**Częstotliwość użycia:** Wysoka – panel administracyjny jest wykorzystywany do bieżącego utrzymywania oferty, stanów magazynowych i obsługi zamówień.

---

# Podsumowanie przypadków użycia

| Nr | Przypadek użycia | Aktor główny | Główny cel |
|---:|---|---|---|
| 1 | Wyszukaj produkt | Klient | Odnalezienie produktu w ofercie sklepu |
| 2 | Dodaj produkt do koszyka | Klient | Przygotowanie wybranego produktu do zakupu |
| 3 | Złóż zamówienie | Klient | Utworzenie zamówienia i wskazanie sposobu dostawy |
| 4 | Opłać i śledź zamówienie | Klient | Dokonanie płatności i realizacja dostawy |
| 5 | Zarządzaj sklepem | Administrator | Zarządzanie produktami, magazynem i zamówieniami |

---

# Główni aktorzy systemu

### Klient

Przegląda ofertę, wyszukuje produkty, dodaje je do koszyka, składa zamówienia, dokonuje płatności oraz może zgłaszać zwroty/reklamacje.

### Administrator

Zarządza katalogiem produktów, cenami, stanami magazynowymi, wyróżnionymi produktami oraz zamówieniami.

### Stripe

Zewnętrzny system obsługujący płatności online, w tym płatności kartą, BLIK, PayPal oraz Klarna.

### Firma kurierska / operator Paczkomatów

Podmiot odpowiedzialny za dostarczenie zamówienia do klienta.

---

# Najważniejsze zależności

Proces zakupowy można przedstawić następująco:

**Wyszukaj produkt → Dodaj produkt do koszyka → Złóż zamówienie → Opłać zamówienie → Realizacja i dostawa**

Administrator natomiast zarządza danymi wykorzystywanymi przez wszystkie powyższe przypadki użycia:

**Zarządzaj sklepem → produkty → ceny → stany magazynowe → zamówienia → realizacja**

System umożliwia również rozpoczęcie procesu **zwrotu/reklamacji** po zakupie. Klient może zgłosić sprawę za pośrednictwem danych kontaktowych sklepu, a następnie administrator obsługuje zgłoszenie.
```
