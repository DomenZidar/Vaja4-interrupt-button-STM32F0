Glede na vašo razvojno ploščico in razširitveno vezje s tipkami, izberite ustrezen digitalni vhod kot interrupt (GPIO_EXT…) in izhod za zeleno LED. Zapišite izbrana pina:
PA0, PC9 zelena, PC8 modra

Znotraj te funkcije zapišite ukaz za vklop/izklop zelene LED
HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_9);

Znotraj iste funkcije dodajte še zakasnitev, ki je potrebna, ko uporabimo mehanska tipkala/stikala: for(uint32_t i=0; i<10000; i++); Koliko znaša (v mili sekundah) zapisana zakasnitev?
500ms

V user code begin 3 - zanka while(1) - zapišite ukaz za utripanje modre LED.
HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_8);

V to zanko dodajte ukaz za zakasnitev z funkcijo Delay iz knjižnice HAL, in sicer pol sekunde.
HAL_Delay(500);

Opazujte delovanje (utripanje modre LED). Kaj se zgodi, ko pritisnemo na modro tipko na STM32F0?
Modra LED nadaljuje nemoteno z utripanjem.

Ali pritisk na modro tipko vpliva na utripanje modre LED in zakaj?
Modra led utripa, ker je v loopu "while", zaradi tega je ne moti tipka za prižig zelene led diode.

Komentar:
V programu cubemx ni delovala funkcija GENERATE CODE, zato nisem mogel generirati kode na mikroprocesor
