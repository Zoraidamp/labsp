     labs3
7. Za pomocą filtru tr wykonaj modyfikację pliku plik.txt, polegającą na umieszczeniu każdego słowa w osobnej linii.

cat plik.txt | tr "\t" "\n"

8. Zlicz wszystkie pliki znajdujące się w katalogu /etc i jego podkatalogach.
find /find /etc -type f -follow | wc -l


   lab 4
1. Wyświetl listę plików z aktualnego katalogu, zamieniając wszystkie małe litery na duże.

'''sh ls|tr [:lower:] [:upper:]
