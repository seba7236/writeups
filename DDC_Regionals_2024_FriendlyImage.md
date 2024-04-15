# Friendly Image

"Da du for nylig har lært det grundlæggende inden for undersøgelse af diskbilleder, bad du en mere erfaren ven om at give dig en øvelsesopgave. De leverede en billedfil uden yderligere ledetråde og fortalte dig, at et flag er skjult et sted i den. Find flaget for at løse puslespillet!"

## Solve

Vi har fået udleveret en .E01 fil (Encase Forensic format). Jeg åbner det i Autopsy

![Screenshot 2024-04-15 085536](https://github.com/seba7236/writeups/assets/46562365/201ed944-743c-44fa-86b2-af2e9081b46c)


Der ligger en "Instructions.txt" og en slettet "Instructions2.txt"

### Instructions.txt
"Your task is very simple. The flag is contained within the three remaining files in alphabeticla order. 
The flag starts with "DDC{" then the first five characters of the first file. Then the last three characters
of the second file. Followed by ..."

### Instructions2.txt
"...the extension of the third file reverted back from hexadecimal. Im sure you can do it!"

Udover Instructions-filerne, er der 3 filer der skiller sig ud fra de normale filer man kan forvente at se i et NTFS filsystem.


### ini.txt
Det er den første fil, i alfabetisk rækkefølge. Derfor skal vi tage de første 5 karakterer fra filens indhold: "keep_"
### This is not a pipe.bmp
Det er den anden fil, i alfabetisk rækkefølge. Vi skal så tage de sidste 3 karakterer fra filens indhold: "on_"
### zebra.77696E6E696E67
Det er den sidste fil, i alfabetisk rækkefølge. Vi skal decode filens extension fra hex: "winning"

Resultatet bliver: "keep_on_winning", eller "DDC{keep_on_winning}"
