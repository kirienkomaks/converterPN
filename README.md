# Converter PNML/PNH 


Konwerter Petri Net fromats


# Install

Jeśli na urządzeniu nie są zainstalowane odpowidnie narzędzia orza biblioteki niżej podana lista komend do instalacji: 
  - Do instalacji pip3 wymagane jest ściądanie pliku kongihuracji get-pip.py https://bootstrap.pypa.io/get-pip.py. W aktualnej wersji projrktu ten plik znajduje się w folderze głównym root
  - Znajdując się w folderze zawierającym get-pip.py: 
```sh
$ py get-pip.py
```
  - Instalacja poszególnych bibliotek
```sh
$ pip3 install numpy==1.19.3 (instalacja poprzednie wersji numpy, najnowsza na obecny moment ma konflikty parametrów)
$ pip3 install pntools
$ pip3 install graphviz
```

# Uruchamianie 

  - Uruchomić konverter PNH -> PNML można podając jako drufi argument liczbę 0 oraz ścieżkę do pliku wejściowego(kilka przykładów znajdują się w folderze /pnh). Plik w formie generated_nazwa_sieci.pnml zostanie zapisany w folderze /pnml
```sh
python converter.py 0 pnh\agerwala1.pnh
```
  - Uruchomić konverter PNML -> PNH można podając jako drugi argument liczbę 1 oraz ścieżkę do pliku wejściowego. Plik w formie generated_nazwa_sieci.pnh zostanie zapisany w folderze /generated_pnh np.:
```sh
python converter.py 1 pnml\generated_agerwala1.pnml
```
  - UI do tworzenia nowej sieci (plik wyjściowy to pnml/generated_ui.pnml): 
```sh
python ui.py
```

Konwertery PNH->PNML oraz PNML->PNH działają całkiem automatycznie, jednak UI wymaga wpisania informacji o sieci: 
- Miejsca (Numer wygenerowany automatycznie na podstawie obecnych danych bazy) - podanie oznaczenia startowego
- Przejścia - podanie nazw miejsc wejściowych oraz wyjściowych dla każdego prześcia 

Tworzenie sieci:
- Add Place
- Add Transition

Modyfikacja wprowadzonych danych sieci:
- Update Place
- Update Transition

Usuwanie elementów sieci:
- Delete Place
- Delete Transition

Po wpisaniu i sprawdzeniu poprawności konstrukcji sieć zostanie zbudowana przyciskiem Create PN Graph w formacie *.pnml w pliku pnml/generated_ui.pnml

