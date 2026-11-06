# TSI-Predikt-Motor

TSI Predikt Motor łączy odczyty OBD‑II z dźwiękiem pracy silnika. Pozwala porównać przebiegi i ustalić, czy do dalszej analizy potrzebne jest powtórne nagranie lub próbka odniesienia.

## Bezpłatne demo

Pobierz repozytorium jako ZIP, rozpakuj je i otwórz [demo/index.html](demo/index.html) w przeglądarce. Demo działa bez konta i bez instalacji. Możesz wybrać scenariusz, zawęzić przedział wykresu i dodać przykładowe nagranie lub referencję.

- **Bieg jałowy** pokazuje stabilny przebieg obrotów.
- **Zmiana obrotów i dźwięku** pokazuje zdarzenie widoczne w obu kanałach.
- **Sprawdzenie pasma łożyska** pokazuje, kiedy potrzebne są dodatkowy pomiar i referencja.

Demo korzysta z danych syntetycznych.

## Alfa warsztatowa

Osobne wydanie dla Windows x64 zawiera lokalny dashboard do własnych pomiarów.

- **Czujniki OBD‑II** · import CSV, wykres wybranego kanału oraz zapis odczytów i raportu JSON. Obsługiwane odczyty to m.in. obroty, prędkość, temperatura płynu, przepustnica, pedał przyspieszenia, obciążenie, ciśnienie dolotu, MAF i NOx.
- **Dźwięk silnika** · import WAV, szczyty widma i przebiegi energii. Z opcjonalnym plikiem znaczników można porównać energię w sektorach cyklu 720°.
- **Rozrząd** · pomiar fazy CKP–CMP z wybranych krawędzi oscyloskopu, porównanie ze sprawnym wzorcem i osobny raport z każdej wizyty.
- **Cechy akustyczne łożysk** · dostępne w narzędziu wiersza poleceń.

Alfa służy do prób warsztatowych. Skuteczność diagnoz na różnych samochodach i działanie na żywo wymagają walidacji. [Opis wydania na TSI HUB](https://tsihub.pl/predikt-motor.html)
