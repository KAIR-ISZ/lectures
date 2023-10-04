# Wprowadzenie do programowania w języku 

**Czas ćwiczenia:** 90 minut

**Cel:** Zapoznanie studentów z podstawami języka programowania R i pomoc w zbudowaniu podstawowego zrozumienia kluczowych pojęć.


## Wprowadzenie:

Język R to otwarty język programowania i środowisko do analizy danych. Jego zalety to bogata biblioteka pakietów, umożliwiająca zaawansowaną analizę statystyczną i wizualizację danych. R jest bezpłatny, co obniża koszty projektów. Dodatkowo, posiada silne wsparcie społeczności oraz akademickie i jest dostępny na różne platformy, co czyni go popularnym narzędziem w dziedzinie analizy danych.

## Podstawowe pojęcia

W języku R, operatory przypisania `'<-'` i `'='` służą do przypisywania wartości do zmiennych, ale różnią się w kontekście ich użycia:

1. **Operator przypisania `'='`**: Ten operator jest często używany w innych językach programowania. Przypisuje on wartość po prawej stronie do zmiennej po lewej stronie. Możesz go używać do przypisywania wartości pojedynczych zmiennych lub wektorów. Przykład:

```R
x = 5
```

2. **Operator przypisania `'<-'`**: Ten operator jest charakterystyczny dla języka R. Działa on również jak operator `'='`, przypisując wartość po prawej stronie do zmiennej po lewej stronie. Jest bardziej zalecany w środowisku R, ponieważ jest bardziej konsekwentny z konwencją używaną w R. Przykład:

```R
y <- 10
```

Oba operatory przypisania mogą być stosowane zamiennie w większości przypadków, ale `<-` jest bardziej powszechnie używane i zalecane w środowisku R ze względu na konsekwencję z innymi konstrukcjami języka.


W języku R istnieje kilka podstawowych typów danych:

1. **Liczby całkowite (integer)**: Reprezentują liczby całkowite. Przykład:

```R
liczba_cal = 42
```

2. **Liczby zmiennoprzecinkowe (numeric)**: Reprezentują liczby zmiennoprzecinkowe. Przykład:

```R
liczba_zmien = 3.14
```

3. **Tekst (character)**: Reprezentuje ciągi znaków. Przykład:

```R
tekst = "To jest przykład"
```

4. **Logiczne (logical)**: Reprezentuje wartości logiczne `TRUE` lub `FALSE`. Przykład:

```R
logiczna_wart = TRUE
```

5. **Czynniki (factor)**: Reprezentuje zmienne jakościowe. Przykład:

```R
czynnik = factor("Kategoria A")
```

Te podstawowe typy danych pozwalają na przechowywanie i manipulację różnymi rodzajami informacji w języku R.

## Wektory


Wektory są fundamentalnymi strukturami danych w języku R i służą do przechowywania sekwencji wartości. Wektory w R mogą zawierać elementy tego samego typu danych, co oznacza, że można tworzyć wektory liczb całkowitych, zmiennoprzecinkowych, znaków itp. Poniżej opisane są podstawowe operacje dotyczące tworzenia i manipulowania wektorami:

**Tworzenie wektorów:**

1. **Funkcja `c()`:** Najczęściej używana do tworzenia wektorów. Można jej użyć do łączenia elementów w jeden wektor. Przykłady:

```R
liczby <- c(1, 2, 3, 4, 5) # Wektor liczb całkowitych
teksty <- c("jabłko", "banan", "gruszka") # Wektor tekstów
```

2. **Funkcja `seq()`:** Służy do generowania sekwencji liczb. Przykład:

```R
sekwencja <- seq(1, 10, by = 2) # Generuje sekwencję 1, 3, 5, 7, 9
```

3. **Funkcja `rep()`:** Używana do powtarzania wartości w wektorze. Przykład:

```R
powtorzenia <- rep(0, times = 5) # Powiela 0 pięć razy: 0, 0, 0, 0, 0
```

**Manipulowanie wektorami:**

1. **Indeksowanie:** Elementy wektora można uzyskać za pomocą indeksów. Indeksy w R zaczynają się od 1. Przykład:

```R
liczby[3] # Zwraca trzeci element z wektora 'liczby'.
```

2. **Podstawianie wartości:** Można zmieniać wartości w wektorze, przypisując im nowe wartości. Przykład:

```R
liczby[2] <- 10 # Zamienia drugi element 'liczby' na 10.
```

3. **Łączenie wektorów:** Wektory można łączyć za pomocą operatora `c()`. Przykład:

```R
nowy_wektor <- c(liczby, 6, 7, 8) # Łączy 'liczby' z nowymi wartościami.
```

4. **Filtrowanie i subsetting:** Używając warunków logicznych, można wybierać elementy spełniające określone kryteria. Przykład:

```R
liczby[liczby > 3] # Zwraca elementy 'liczby' większe od 3.
```

Wektory są kluczowymi elementami w analizie danych w R, a znajomość sposobów tworzenia i manipulowania nimi jest niezbędna do skutecznej pracy z danymi w tym języku.



**Ćwiczenie 1: Tworzenie wektorów:**

Utwórz wektor następujących wartości: `5, 10, 15, 20, 25`

Wykonaj następujące operacje:
- Wybierz wartości większe niż 15
- Policz średnią z wektora
- Policz sumę pierwszych trzech elementów


## Struktury sterujące

### Warunek `if`
W języku R, instrukcja warunkowa `if` służy do wykonywania określonego bloku kodu tylko wtedy, gdy określony warunek jest spełniony (prawdziwy). Instrukcja `if` ma następującą ogólną składnię:

```R
if (warunek) {
  # Kod do wykonania, gdy warunek jest prawdziwy
}
```

- `warunek` to wyrażenie logiczne, które może przyjąć wartość `TRUE` lub `FALSE`.
- Blok kodu wewnątrz nawiasów klamrowych `{}` zostanie wykonany tylko wtedy, gdy `warunek` jest spełniony (czyli ma wartość `TRUE`).

Przykład:

```R
x <- 5

if (x > 3) {
  cat("x jest większe niż 3.\n")
}
```

W powyższym przykładzie, jeśli zmienna `x` jest większa niż 3, to komunikat "x jest większe niż 3." zostanie wyświetlony.

Można także używać instrukcji `if` w połączeniu z instrukcjami `else` i `else if`, aby obsłużyć różne scenariusze warunkowe. Na przykład:

```R
x <- 5

if (x > 10) {
  cat("x jest większe niż 10.\n")
} else if (x > 5) {
  cat("x jest większe niż 5, ale nie większe niż 10.\n")
} else {
  cat("x nie jest większe niż 5.\n")
}
```

W tym przypadku zostanie wykonany odpowiedni blok kodu w zależności od wartości `x`. Instrukcja `else` obsługuje przypadki, gdy żaden z wcześniejszych warunków nie jest spełniony.




### Pętla ```for```

Pętla `for` w języku R służy do iteracji (powtarzania) przez sekwencję wartości, na przykład sekwencję liczb, elementy wektora lub inne obiekty. W każdym przebiegu pętli, zmienna iteracyjna przyjmuje jedną z wartości z sekwencji, a określony blok kodu jest wykonany. Ogólna składnia pętli `for` w R wygląda następująco:

```R
for (zmienna_iteracyjna in sekwencja) {
  # Blok kodu do wykonania w każdym przebiegu
}
```

- `zmienna_iteracyjna` to zmienna, która przechowuje aktualną wartość z sekwencji w danym przebiegu pętli.
- `sekwencja` to obiekt, przez który pętla będzie iterować, na przykład wektor liczb, lista, czy wynik funkcji generującej sekwencję.

Przykład pętli `for` iterującej przez wektor liczb i wyświetlającej ich kwadraty:

```R
liczby <- c(1, 2, 3, 4, 5)

for (liczba in liczby) {
  kwadrat <- liczba^2
  cat("Kwadrat", liczba, "to", kwadrat, "\n")
}
```

W wyniku tego kodu zostaną wyświetlone kwadraty liczb od 1 do 5.


**Ćwiczenie 2: Instrukcje warunkowe:**
Masz listę wyników egzaminów. Napisz kod R, aby sprawdzić, czy każdy wynik jest pozytywny (większy lub równy 60), czy negatywny (mniejszy niż 60). Wypisz odpowiednio „Zaliczony” lub „Niezaliczony”.

```R
# Lista wynikow egzaminu
wyniki <- c(75, 48, 90, 60, 30)
```

## Data Frame

DataFrame to podstawowa struktura danych w języku R, służąca do przechowywania i zarządzania danymi w formie tabelarycznej, gdzie dane są zorganizowane w kolumny i wiersze. Każda kolumna może zawierać różne typy danych (liczby, tekst, itp.), ale wszystkie kolumny w ramce danych muszą mieć taką samą liczbę wierszy.

Tworzenie data frame w R można zrobić na kilka sposobów:

1. **Funkcja `data.frame()`:** Najczęściej używana metoda. Przykład:

```R
# Tworzenie data frame z trzema kolumnami
df <- data.frame(
  Imię = c("Anna", "Jan", "Karolina"),
  Wiek = c(25, 30, 28),
  Płeć = c("Kobieta", "Mężczyzna", "Kobieta")
)
```

2. **Konwersja innych struktur danych:** Istnieją inne struktury danych w R, takie jak wektory, które można przekształcić w data frame. Przykład:

```R
# Tworzenie wektorów
imiona <- c("Anna", "Jan", "Karolina")
wiek <- c(25, 30, 28)
plec <- c("Kobieta", "Mężczyzna", "Kobieta")

# Konwersja na data frame
df <- data.frame(Imię = imiona, Wiek = wiek, Płeć = plec)
```

3. **Importowanie danych z pliku:** Można wczytać dane z plików zewnętrznych, takich jak CSV lub Excel, tworząc data frame. Na przykład:

```R
# Importowanie danych z pliku CSV
df <- read.csv("nazwa_pliku.csv")
```

Data frame'y są często używane w analizie danych, ponieważ pozwalają na łatwą manipulację, filtrowanie, agregację i wizualizację danych w formie tabelarycznej. Dzięki nim możliwe jest przetwarzanie i badanie różnych aspektów danych w R.


**Ćwiczenie 3: Tworzenie i manipulacja data frameami**

Wykorzystując zbiór danych:

| Imię  | Wiek  | Punkty |
| :---: | :---: | :----: |
|  Jan  |  25   |   85   |
|  Ola  |  30   |   92   |
|  Ela  |  28   |   78   |


Utwórz data frame z danych w tej tabeli
- dodaj kolumnę "Ocena" wyliczaną zgodnie ze skalą AGH
- wyfiltruj dane do osób z wiekiem poniżej 30 lat. 



## Wizualizacja danych

### Biblioteki

Ładowanie i instalowanie bibliotek (pakietów) w języku R jest kluczowym procesem, ponieważ pozwala ono na korzystanie z dodatkowych funkcji i narzędzi dostępnych w tych bibliotekach. Oto kroki do ładowania i instalowania bibliotek w R:

**Instalowanie bibliotek:**

1. **Instalacja z CRAN (Comprehensive R Archive Network):**
   Aby zainstalować bibliotekę z CRAN, można użyć funkcji `install.packages()`. Na przykład, aby zainstalować pakiet `ggplot2`, wpisz:

   ```R
   install.packages("ggplot2")
   ```

   R pobierze i zainstaluje pakiet oraz jego zależności.

2. **Instalacja z innych źródeł:**
   Niektóre pakiety mogą być dostępne z innych źródeł niż CRAN, takie jak GitHub. Wtedy można użyć funkcji `devtools::install_github()`. Przykład:

   ```R
   install.packages("devtools")
   library(devtools)
   install_github("nazwa_uzytkownika/nazwa_repozytorium")
   ```

**Ładowanie bibliotek:**

Po zainstalowaniu biblioteki, aby ją użyć w bieżącej sesji R, należy ją załadować za pomocą funkcji `library()` lub `require()`. Przykład:

```R
library(ggplot2)
```

lub

```R
require(ggplot2)
```

R załaduje bibliotekę i umożliwi korzystanie z jej funkcji i obiektów w bieżącej sesji. Jeśli biblioteka jest już załadowana, ponowne jej załadowanie nie spowoduje błędów.

Warto również pamiętać, że niektóre pakiety mogą wymagać wcześniejszej instalacji innych zależności. R będzie informować o tym podczas instalacji i wskaże, jakie pakiety należy jeszcze zainstalować.

Za pomocą tych prostych kroków można instalować i ładować różne biblioteki w R, co pozwala na korzystanie z różnorodnych funkcji i rozszerza możliwości analizy danych oraz tworzenia wizualizacji.

### Wprowadzenie do `ggplot2`

**Wprowadzenie do pakietu ggplot2 w R**

Pakiet ggplot2 jest jednym z najpotężniejszych narzędzi do tworzenia wizualizacji danych w języku R. Opracowany przez Hadley Wickhama, ggplot2 bazuje na koncepcji "Grammar of Graphics" i pozwala na tworzenie wyjątkowych i estetycznych wykresów w prosty sposób.

**Korzyści z korzystania z ggplot2:**

1. **Zrozumienie składni:** ggplot2 opiera się na zrozumiałej składni opisującej wykresy, co ułatwia tworzenie nawet zaawansowanych wizualizacji.

2. **Dostosowywanie wykresów:** ggplot2 umożliwia dokładne dostosowanie wykresów, w tym zmianę kolorów, etykiet, skal, itp.

3. **Wizualna spójność:** Wykresy tworzone za pomocą ggplot2 są estetycznie przyjemne i mają spójny wygląd.

**Tworzenie wykresów słupkowych w ggplot2:**

Wykresy słupkowe są używane do prezentowania danych kategorialnych w formie kolumn lub słupków. W ggplot2 można je tworzyć za pomocą funkcji `geom_bar()`. Oto przykład tworzenia prostego wykresu słupkowego z użyciem ggplot2:



```R
# Instalacja i ładowanie ggplot2 (jeśli jeszcze nie jest zainstalowane)
# install.packages("ggplot2")
library(ggplot2)

# Przykładowe dane
dane <- data.frame(
  Kategoria = c("A", "B", "C", "D"),
  Wartość = c(30, 45, 20, 55)
)

# Tworzenie wykresu słupkowego
wykres_slupkowy <- ggplot(dane, aes(x = Kategoria, y = Wartość)) +
  geom_bar(stat = "identity", fill = "skyblue") +
  labs(title = "Wykres Słupkowy",
       x = "Kategoria",
       y = "Wartość")

# Wyświetlenie wykresu
print(wykres_slupkowy)
```


Ten kod tworzy wykres słupkowy, gdzie na osi X są wyświetlane kategorie, a na osi Y wartości. `geom_bar()` jest używany do stworzenia słupków, a `fill` określa kolor wypełnienia słupków.

To tylko krótka próbka możliwości pakietu ggplot2 w tworzeniu wykresów słupkowych. Pakiet ten oferuje wiele opcji dostosowywania, pozwalając na tworzenie wykresów dostosowanych do specyficznych potrzeb analizy danych.


**Ćwiczenie 4: Wizualizacja danych**


Wykorzystując dane o średnim wyniku z zaliczenia:

|       Przedmiot       | Średnia | Rocznik |
| :-------------------: | :-----: | :-----: |
| Analiza i Bazy Danych |   71    |  2022   |
|   Metody numeryczne   |   67    |  2022   |
|  Eksploracja danych   |   89    |  2022   |

Przygotuj wykres słupkowy dla rocznika 2022. Wykres ma mieć tytuł i odpowiednio opisane osie. 

## Zadanie domowe

**Zadanie domowe: Powtórka**

Załóżmy, że masz dane dotyczące wyników testu dwóch grup studentów (Grupa A i Grupa B) w dwóch przedmiotach (Matematyka i Historia). Twoim zadaniem jest stworzenie wykresu słupkowego, który przedstawi średnie wyniki testów z Matematyki dla obu grup. Jednakże, jeśli średni wynik Grupy A w Matematyce jest niższy niż 70, to wynik tej grupy nie powinien być uwzględniony w wykresie i powinien wyświetlony odpowiedni komunikat.


**Dodatkowe wskazówki:**

- Przetestuj swój kod dla następujących zbiorów danych:

```R
# Test 1 Wyniki testów Matematyki dla Grupy A i Grupy B
wyniki_grupa_A <- c(60, 65, 75, 68, 62)
wyniki_grupa_B <- c(78, 80, 85, 92, 88)

# Test 2 Wyniki testów Matematyki dla Grupy A i Grupy B
wyniki_grupa_A <- c(80, 65, 75, 68, 72)
wyniki_grupa_B <- c(78, 80, 85, 92, 88)
```

- Możesz użyć funkcji `mean()` do obliczenia średniej.
- Do stworzenia wykresu słupkowego użyj pakietu ggplot2 i funkcji `geom_bar()`. Możesz dostosować wygląd wykresu, dodając tytuł i etykiety osi.

