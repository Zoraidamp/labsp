  labs 3
  
zad.7 Za pomocą filtru tr wykonaj modyfikację pliku plik.txt, polegającą na umieszczeniu każdego słowa w osobnej linii.

    cat plik.txt | tr "\t" "\n"

zad.8 Zlicz wszystkie pliki znajdujące się w katalogu /etc i jego podkatalogach.

    find /etc/ -type f 2>errors | wc -l
    
zad.9 Napisać polecenie zliczające ilość znaków z pierwszych trzech linii pliku /etc/passwd.

    cat /etc/passwd |head -n 3 | wc -m

  lab 4
  
zad.1 Wyświetl listę plików z aktualnego katalogu, zamieniając wszystkie małe litery na duże.

     ls|tr [:lower:] [:upper:]
     
zad.2 Wyświetl listę praw dostępu do plików w aktualnym katalogu, ich rozmiar i nazwę.

    ls -l | cut -b 1-10,28-33,48-
    
zad.3 Wyświetl listę plików w aktualnym katalogu, posortowaną według rozmiaru pliku.
    
    ls --sort=size -l
    
zad.4 Wyświetl zawartość pliku /etc/passwd posortowaną według numerów UID w kolejności od największego do najmniejszego.

    sort -t: -k3 -nr /etc/passwd
