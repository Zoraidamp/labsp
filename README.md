  labs3
zad.7 Za pomocą filtru tr wykonaj modyfikację pliku plik.txt, polegającą na umieszczeniu każdego słowa w osobnej linii.

    cat plik.txt | tr "\t" "\n"

zad. 8 Zlicz wszystkie pliki znajdujące się w katalogu /etc i jego podkatalogach.

    find /etc/ -type f 2>errors | wc -l
    
zad. 9 Napisać polecenie zliczające ilość znaków z pierwszych trzech linii pliku /etc/passwd.

   

   lab 4
zad.1 Wyświetl listę plików z aktualnego katalogu, zamieniając wszystkie małe litery na duże.

     ls|tr [:lower:] [:upper:]
