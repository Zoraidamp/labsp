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
    
  lab5
  
zad.1 Znajdź w swoim katalogu domowym (bez podkatalogów) wszystkie pliki, które zostały zmodyfikowane w ciągu ostatnich dziesięciu dni i wyświetl ich nazwy.

    find . -maxdepth 1 -type f -mtime -10
    
zad.2 Znajdź wszystkie pliki zwykłe w systemie, które mają w nazwie ciąg znaków „conf” i wyświetl ich nazwy na ekranie.

    find / -name \*config\* -type f 2> /dev/null
    
zad.3 Znajdź w swoim katalogu domowym wszystkie pliki, które nie były używane w ciągu ostatnich 20 dni.

     -path '*/.git/*' -prune -o -print 

lub

    find -mtime -20 | egrep -v '\.git'

lub

    find . -not -iwholename '*/.git/*'


zad.4 Znajdź w katalogu /etc wszystkie niepuste podkatalogi i pliki o nazwach zaczynających się na literę „a”.

    find /etc \( -type f -and -name a* \) -or \( -type d -and ! -empty \) 2> /dev/null

zad.5 Z bieżącego katalogu usuń pliki, których nazwa zaczyna się na literę „x” i zawiera dokładnie trzy znaki.

    rm x??
    
zad.6 Skonstruuj polecenie tworzące katalog, którego nazwą będzie aktualna (w momencie wywołania) systemowa data w formacie rrrr-mm-dd.
    mkdir `date +%Y-%m-%d`