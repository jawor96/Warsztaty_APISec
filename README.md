# Wstęp do Noname Advanced API Security for IBM

![](./images/banner.png) 

**Ostatnia aktualizacja:** Październik 2025

**Czas trwania:** 20 - 30 minut

## Dostęp do środowiska 

W tym laboratorium wykorzystamy środowisko DEMO dostępne pod linikiem: [TUTAJ](https://se-demo.nonamesec.com/login)

Login i hasło podadzą prowadzący podczas warsztatów.

## Wprowadzenie

Interfejsy API zyskują coraz większy zakres, skalę i znaczenie w miarę, jak organizacje stają się coraz bardziej oparte na chmurze i cyfrowych usługach. API znajdują się w samym sercu aplikacji i usług — są wbudowane w środowiska chmurowe, od usług wykorzystywanych przez deweloperów po obciążenia przenoszone przez inżynierów — a często stanowią też samodzielne źródło przychodów, umożliwiając firmom rozwój biznesu i budowanie ekosystemu deweloperów.

Choć wiele firm korzysta już z narzędzi obsługujących API, takich jak bramy API (API Gateways) czy zapory aplikacyjne (Web Application Firewalls), które zapewniają pewien poziom ochrony, powinny one być uzupełnione dedykowanymi rozwiązaniami bezpieczeństwa API. Takie rozwiązania są zaprojektowane specjalnie po to, by zapewniać pełną widoczność, ochronę w czasie rzeczywistym oraz ciągłe testowanie — niezbędne do obrony przed współczesnymi atakami na API.
I właśnie tutaj pomóc może Noname Advanced API Security for IBM.

## Wyzwanie

Zabezpieczenie interfejsów API stanowi ogromne wyzwanie. Organizacje często posiadają dziesiątki tysięcy API rozmieszczonych w różnych środowiskach, korzystających z różnych bram (gateways), zapór aplikacyjnych (WAF), load balancerów i innych komponentów. Utrudnia to zrozumienie, w jaki sposób API są kierowane, konfigurowane i wykorzystywane, co w praktyce uniemożliwia dokładną ocenę ryzyka, jakie stwarzają.

Sytuację dodatkowo komplikuje fakt, że nowe i istniejące API są szybko tworzone i wdrażane do środowisk produkcyjnych, co prowadzi do powstania dynamicznego i złożonego ekosystemu. Wszystkie te zagrożenia bezpieczeństwa są dziś łatwiejsze do wykorzystania niż kiedykolwiek wcześniej.

API zostały zaprojektowane tak, by były łatwe do tworzenia, zrozumienia i użycia — niestety, właśnie to sprawia, że są one tak podatne na ataki. Co więcej, większość podatności API dotyczy błędów w logice biznesowej, przez co trudno jest odróżnić „prawidłowe” od „złośliwego” zachowania API. W efekcie API stanowią bardzo rozległą i niezwykle atrakcyjną powierzchnię ataku.

## Przegląd rozwiązania Akamai API Security

Kompleksowe bezpieczeństwo API obejmuje cały cykl życia interfejsu API. Oznacza to ochronę w czterech kluczowych obszarach:

- Odkrywanie (Discovery)
- Zarządzanie postawą bezpieczeństwa (Posture Management)
- Ochrona w czasie działania (Runtime Protection)
- Aktywne testowanie (Active Testing) – ten element nie jest częścią tego laboratorium.

Zaczniemy od odkrywania i zarządzania postawą bezpieczeństwa, aby pomóc Ci zrozumieć, jakie API posiadasz w swoim środowisku, co one robią, kto z nich korzysta, jakie dane są wymieniane, a także by zidentyfikować typowe błędne konfiguracje, które mogą występować.

### Odkrywanie (Discovery) i Zarządzanie postawą bezpieczeństwa (Posture Management)

Te moduły pozwalają ograniczyć ryzyko związane z API, uzyskać pełną inwentaryzację interfejsów oraz naprawić podatności zanim zostaną wykorzystane.

Organizacje muszą rozumieć, jakie dane API wysyła lub odbiera, kto jest jego właścicielem, kiedy były ostatnio aktualizowane, czy jest nadal używane oraz czy jest poprawnie skonfigurowane.

> Uwaga: Posture Management może również wspierać firmy w zakresie raportowania regulacyjnego. Na przykład, wiele organizacji musi raportować, jakie dane i API są wykorzystywane w ich środowisku — dotyczy to m.in. niektórych banków.

### Ochrona w Czasie Działania (Runtime Protection)

Ten moduł koncentruje się na analizie transakcji API w czasie rzeczywistym lub z niewielkim opóźnieniem, tak aby nie zakłócać przepływu danych. Celem jest zbudowanie modelu bazowego zachowania API – czyli zrozumienia, co jest dla niego zachowaniem normalnym.
Gdy API zaczyna zachowywać się w sposób odbiegający od tej normy, system może wygenerować alert lub zgłosić incydent. 

>Warto zauważyć, że API Gateways i WAF-y chronią jedynie przed znanymi wzorcami ataków (np. na podstawie polityk lub dopasowań regex). Nie pomagają one jednak w przypadku błędów logicznych lub nieprawidłowej konfiguracji API.

### Aktywne Testowanie (Active Testing)

Ostatni moduł bezpieczeństwa API koncentruje się na testowaniu. Moduł testów w rozwiązaniu Akamai nosi nazwę Active Testing. To narzędzie pozwala testować API przed ich wdrożeniem do środowiska produkcyjnego lub przed publikacją nowej wersji. Celem jest automatyczne przeprowadzanie testów penetracyjnych API w trakcie ich rozwoju, identyfikowanie i naprawianie błędów oraz zapobieganie wprowadzaniu podatności do środowiska produkcyjnego. Dzięki temu masz pewność, że nowe wdrożenia nie wprowadzą dodatkowych zagrożeń dla bezpieczeństwa.

## Laboratorium

Przejdźmy teraz przez ćwiczenie laboratoryjne, aby zobaczyć, w jaki sposób Akamai API Security skutecznie identyfikuje i ogranicza ryzyka związane z bezpieczeństwem API.

### Panel Inwentaryzacji (Inventory Dashboard)

Zaczniemy od panelu przeglądowego inwentaryzacji API w rozwiązaniu Akamai API Security.
Panel ten prezentuje wszystkie interfejsy API w Twoim środowisku oraz rodzaje wrażliwych danych, z którymi te API mają kontakt. Dashboard jest dynamiczny – automatycznie wykrywa nowe API pojawiające się w ruchu sieciowym oraz rejestruje pełną historię zmian dotyczących istniejących API.

1. Zaloguj się do platformy, korzystając z podanego linku, loginu i hasła.

![](./images/APISec_01.png) 

> Jeśli pojawi się komunikat o warunkach wykorzystania środowiska kliknij `Accept`.

2. Kliknij zakładkę **Inventory**.

![](./images/APISec_02.png)

Jak widać, Akamai API Security wykonuje dużą pracy, gromadząc i kategoryzując cały ekosystem API na ekranie Statystyk (Stats).

Wykres Datatype Classification przedstawia podsumowanie liczby interfejsów API, które przetwarzają różne typy danych: *dane osobowe* (np. płeć, adres e-mail, numer identyfikacyjny pojazdu itp.), *dane płatnicze* (np. numery kart), *dane uwierzytelniające* (np. hasła), *dane zabronione* (np. niezaszyfrowane hasła), oraz *inne dane wrażliwe*.

Na tej stronie można również znaleźć inne przydatne informacje, takie jak typy API (API Type), metody uwierzytelniania (API Auth) oraz klasyfikacja API (API Classification).

![](./images/APISec_03.png)

3. Kliknij na zakładkę `APIs` w sekcji **Inventory**

![](./images/APISec_03.png)


Na początku widzisz ogólny spis API. Ten przegląd dostarcza szczegółowych informacji o każdym interfejsie API — takich jak host, ścieżka, metoda, informacja o tym, czy jest uwierzytelniony, czy jest dostępny publicznie (internet-facing) itp. Akamai API Security automatycznie rozpoznaje typ każdego API.

Tutaj widzimy bardziej szczegółowy widok wszystkich API wykrytych przez Akamai API Security. System klasyfikuje API jako unikalne połączenie Host + Metoda + Ścieżka, co pozwala dokładnie zidentyfikować każdy interfejs. Dodatkowo w tym widoku prezentowane są problemy i typy danych powiązane z poszczególnymi API.

Widok można filtrować, aby wyświetlać tylko określone typy API — dzięki temu łatwiej jest zrozumieć powierzchnię potencjalnych zagrożeń.
Na przykład: pokażmy tylko te API, dla których nie wykryto żadnego mechanizmu uwierzytelniania.

Aby to zrobić, przejdź do sekcji Filters po prawej stronie, znajdź filtr Auth, odznacz (Select ALL), a następnie zaznacz Not Detected.

Teraz widzimy, które z Twoich API nie mają żadnego rodzaju uwierzytelniania.
Przyjrzyjmy się teraz bliżej jednemu z nich, aby zobaczyć, jakie szczegółowe informacje możemy uzyskać z tych danych.
W pasku wyszukiwania wpisz: posts/recent.