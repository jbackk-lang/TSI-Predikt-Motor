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

## Możliwości do rozwinięcia i sprawdzenia

- **Analizator na mikrokontrolerze.** Profil badawczy FordA ma 97 wartości, czyli 388 bajtów w zapisie `float32`. To same parametry profilu. Na prototypie z STM32H743 trzeba przenieść obliczanie cech do firmware’u i zmierzyć pamięć zajętą przez bufory i analizę widma, czas przetwarzania oraz zgodność wyników z wersją Python. [STM32H743](https://www.st.com/en/microcontrollers-microprocessors/stm32h743-753.html)
- **Predikt Motor jako samodzielne urządzenie.** Kandydatem do prototypu z dashboardem, raportami i zapisem pomiarów jest Raspberry Pi Compute Module 5 z 2 GB RAM i 16 GB eMMC. Do przygotowania jest wydanie Linux ARM64. Trzeba sprawdzić działanie z interfejsem OBD‑II i mikrofonem oraz zmierzyć zużycie pamięci i czas analizy. [Compute Module 5](https://www.raspberrypi.com/documentation/computers/compute-module.html)
- **Seria sygnałowa TSI.** Motor, Solar PV i Grid Monitor mogą używać wspólnego formatu profilu i kodu do liczenia cech. Każdy moduł potrzebuje własnych wejść, danych treningowych i progów. W każdym teście trzeba mierzyć wykryte zdarzenia i fałszywe alarmy na danych odłożonych od treningu.

Na oficjalnym teście FordA profil wykrył **618 z 639** przebiegów z oznaczonym objawem i zgłosił **29 alarmów w 681** przebiegach bez niego. Zbiór nie identyfikuje w raporcie konkretnej usterki. Wynik służy do porównań metod analizy sygnału. [Opis zbioru FordA](https://www.timeseriesclassification.com/description.php?Dataset=FordA)
