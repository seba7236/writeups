# Bankrøvers Bekendelser

"Vi har holdt lidt øje med en bandit vi mistænker for at planlægge et røveri - vi ved bare ikke hvor. Vi fik heldigvis en kendelse til at anholde ham, og ransage hans hjem. Desværre kan vi ikke finde noget, og vi må lade ham gå igen medmindre du kan hjælpe. Der var intet på hans computer, men han havde en virtuel maskine der var krypteret... Det eneste vi fandt var en virtuel hukommelsesfil, et billede af en lasagne og et notat: "slet huskeliste"- er det noget du kan bruge?"


![Screenshot 2024-04-13 213031](https://github.com/seba7236/writeups/assets/46562365/9500ba2c-d2ff-4bda-a996-7f25329056e2)



Hmm, krypteret. Vi skal bruge et password. Beskrivelsen nævnte noget med en huskeliste. Jeg kigger i strings om der er en huskeliste et sted.

![Screenshot 2024-04-13 213152](https://github.com/seba7236/writeups/assets/46562365/4da9ecd6-144c-4919-858d-0ee4124b8e77)

Yes, det er der. Lad os finde Volatility frem, der må være noget spændende.

![Screenshot 2024-04-13 213246](https://github.com/seba7236/writeups/assets/46562365/73b5a991-d8b9-4f36-a1ae-92d7b965b659)


Notepad.exe kører, og det er lidt interessant. Måske blev huskeliste.txt redigeret af notepad da dumpet blev taget?

Lad og scanne efter filen "huskeliste" med filescan, og finde dens adresse i memory, så vi kan dumpe den.


![Screenshot 2024-04-13 213354](https://github.com/seba7236/writeups/assets/46562365/f635eb2b-da3a-47f8-9a2e-2fc233fe5e62)


Nu har vi process ID og addressen i memory. Nu kan vi dumpe filen med dumpfiles.

![Screenshot 2024-04-13 213431](https://github.com/seba7236/writeups/assets/46562365/1a19a9a1-e781-406a-9c87-9d6a4ee1600c)

VI har nu password til rar filen "MinLivretErLasagne06"

![Screenshot 2024-04-13 213455](https://github.com/seba7236/writeups/assets/46562365/bc3b4e35-a496-42e5-9bec-bbcb86af4254)


Flaget er altså "DDC{1_W15H_1_Wa5_a_UN1c0Rn}

