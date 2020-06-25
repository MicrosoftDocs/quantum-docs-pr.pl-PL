# <a name="articles"></a>Artykuły

W tym katalogu można znaleźć artykuły dokumentacji zestawu Quantum Development Kit. Ten katalog zawiera:

- **Katalogi artykułów**: zawiera artykuły dla każdej sekcji dokumentacji. W tych katalogach można znaleźć następującą zawartość:
  
  - Każdy katalog zawiera plik służący `toc.yml` do wyświetlania zawartości katalogu w głównym spisie treści (TOC).
  - Artykuły o promocji, które zawierają dokumentację. Te artykuły powinny postępować zgodnie z wytycznymi [przewodnika współautora Microsoft docs](https://docs.microsoft.com/en-us/contribute/).
  - Podkatalog artykułów. Te katalogi podrzędne powinny również zawierać własny `toc.yml` plik.

> :p encil: Chociaż istnieje możliwość odwołująca się `*.md` plików bezpośrednio w pliku nadrzędnym `TOC.yml` , aby zachować zamówione elementy, odwołują się do nich tylko z `toc.yml` bieżącego katalogu.

- **Główny `TOC.yml` plik spisu treści (TOC)**: w tym pliku znajdują się sekcje spisu treści witryny internetowej wraz z odwołaniem do głównego `toc.yml` pliku katalogu każdej sekcji.
- **`index.yml`** YAML z konfiguracją strony docelowej dokumentacji.
- **`\media`**: Katalog do przechowywania wszystkich obrazów używanych w dokumentacji programu. Zawiera `\media\src` podkatalog do przechowywania plików źródłowych obrazów.
- **Pliki licencji**: pliki zawierające licencje prawne
- **Pliki techniczne**: pliki zawierające makra i metadane.

## <a name="guidelines"></a>Wytyczne

Niektóre ogólne wytyczne dotyczące organizacji tego katalogu dla współautorów:

- Każdy katalog lub podkatalog powinien zawierać własny `toc.yml` plik, w którym są określone te same artykuły na poziomie lub `toc.yml` pliki jego katalogów podrzędnych.
- Organizacja katalogów repozytorium powinna być jak najbliżej organizacji spisu treści witryny sieci Web dokumentacji.
- Wszystkie obrazy powinny być przechowywane w `articles\media` folderze artykułów.
- Tytuły artykułów, nazwy w spisie treści i *UID* metadanych powinny znajdować się jak najbliżej siebie i przedstawiać wyraźnie nagłówek H1 dokumentu z promocji.

## <a name="adding-images"></a>Dodawanie obrazów

Aby obrazy były prawidłowo renderowane w trybie ciemnym, należy unikać przezroczy.
- W przypadku `*.jpg` plików, które nie są potrzebne, ponieważ format pliku nie obsługuje przezroczystych elementów.
- W przypadku `*.png` plików należy dodać białe tło lub zmienić wartość kanału alfa na 100. Najprostszym sposobem wykonania tej czynności w systemie Windows jest otwarcie pliku w programie Paint i zapisanie go, zastępując oryginalny plik.
- `*.svg`W przypadku plików należy dodać biały prostokąt do najniższej warstwy. Można to zrobić za pomocą Inkscape:
  - Otwórz plik `*.svg`.
  - Wybierz narzędzie do tworzenia i rysowania białych prostokątów na początku oryginalnego rysunku.
  - Wybierz narzędzie "Wybierz i Przekształć obiekty", klikając w ciemnej strzałkę lub naciskając klawisz F1.
  - Po wybraniu prostokąta kliknij element paska narzędzi "dolny wybór do dołu (koniec)".
  - Dostosuj prostokąt przy użyciu myszy lub klawiszy strzałek.
