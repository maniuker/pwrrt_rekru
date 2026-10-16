# Mikrokontroler STM32G473CET3 – projekt:
Do konfiguracji mikrokontrolera oprócz STM32CubeIDE użyłem STM32CubeMX, które znacząco ułatwiło pracę:

a)	Taktowanie ustawiłem w CubeMX w sekcji Clock Configuration zgodnie z poleceniem, jednak przeskalowałem je koniec końców na 80Mhz (HCLK)

b)	Timer wybrałem zwykły TIM6, który skonfigurowałem z preskalerem 7999(+1) i okresem licznika 999(+1). Wyjściowo dało to 100 ms, po których za każdym razem zmienia się stan pinu z diodą LED, a więc mruga ona z częstotliwością 5 Hz. Dzieje się to jako przerwanie, co odciąża pętle ‘while’

c)	Watchdoga ustawiłem z preskalerem 8 oraz wartościami okna 127, aby maksymalny czas na odświeżenie wyniósł 26,2 ms bez konkretnego okienka czasowego

d)	Moduł FDCAN1 ustawiłem zgodnie z poleceniem na odpowiednich PINach w trybie zwykłego CANa. Wyliczyłem parametry czasowe, aby Baud-Rate wyniósł 1 Mbit/s. Trudno jest mi jednak zrozumieć do końca działanie interfejsu CAN.
