# Plython 🐍🇵🇱

**Interpreter polskiego Pythona** - pisz kod w języku polskim i uruchamiaj go jak zwykły Python!

## 📖 Opis

Plython to interpreter, który pozwala na pisanie kodu Pythona używając polskich słów kluczowych. Skrypt automatycznie tłumaczy polskie słowa na ich angielskie odpowiedniki i uruchamia kod za pomocą standardowego interpretera Python.

## 🚀 Instalacja

### Wymagania
- Linux/macOS (Bash)
- Python 3.x
- `sed` (standardowo dostępny w systemach Unix)

### Kroki instalacji

1. **Pobierz skrypt**:
   ```bash
   curl -O https://raw.githubusercontent.com/Shieldowskyy/plython/main/plython
   # lub
   wget https://raw.githubusercontent.com/Shieldowsky/plython/main/plython
   ```

2. **Nadaj uprawnienia wykonywalne**:
   ```bash
   chmod +x plython
   ```

3. **Przenieś do katalogu systemowego** (opcjonalnie):
   ```bash
   sudo mv plython /usr/local/bin/
   ```
   
   Lub dodaj katalog ze skryptem do `PATH`:
   ```bash
   export PATH=$PATH:$(pwd)
   ```

## 💻 Użycie

### Podstawowe użycie
```bash
./plython twój_skrypt.ply
```

### Z argumentami
```bash
./plython twój_skrypt.ply arg1 arg2 arg3
```

### Jeśli zainstalowano globalnie
```bash
plython twój_skrypt.ply
```

## 📝 Składnia

Plython wspiera następujące polskie słowa kluczowe:

| Polski | Python | Przykład użycia |
|--------|---------|-----------------|
| `funkcja` | `def` | `funkcja moja_funkcja():` |
| `klasa` | `class` | `klasa MojaKlasa:` |
| `jeżeli` | `if` | `jeżeli x > 5:` |
| `lubjeżeli` / `albo` | `elif` | `albo x == 3:` |
| `inaczej` | `else` | `inaczej:` |
| `zwróć` | `return` | `zwróć wynik` |
| `Prawda` / `prawda` | `True` | `jeżeli prawda:` |
| `Fałsz` / `fałsz` | `False` | `zmienna = fałsz` |
| `dopóki` | `while` | `dopóki i < 10:` |
| `dla` | `for` | `dla i w przedział(10):` |
| `w` | `in` | `dla element w lista:` |
| `przerwij` | `break` | `przerwij` |
| `kontynuuj` | `continue` | `kontynuuj` |
| `drukuj` | `print` | `drukuj("Witaj!")` |
| `przedział` / `zakres` / `wymiar` | `range` | `przedział(1, 11)` |
| `i` | `and` | `jeżeli x i y:` |
| `lub` | `or` | `jeżeli x lub y:` |
| `nie` | `not` | `nie prawda` |
| `żaden` | `None` | `wynik = żaden` |
| `przejdź` | `pass` | `przejdź` |

## 🎯 Przykłady

### Przykład 1: Witaj świecie
```python
# plik: witaj.ply
drukuj("Witaj świecie!")
```

```bash
plython witaj.ply
```

### Przykład 2: Pętla i warunki
```python
# plik: petla.ply
dla i w przedział(1, 6):
    jeżeli i % 2 == 0:
        drukuj(f"Parzysta liczba: {i}")
    inaczej:
        drukuj(f"Nieparzysta liczba: {i}")
```

### Przykład 3: Funkcja
```python
# plik: funkcja.ply
funkcja oblicz_kwadrat(liczba):
    wynik = liczba * liczba
    zwróć wynik

dla i w przedział(1, 6):
    kwadrat = oblicz_kwadrat(i)
    drukuj(f"Kwadrat z {i} to {kwadrat}")
```

### Przykład 5: Klasa z metodami
```python
# plik: klasa.ply
klasa Kalkulator:
    funkcja __init__(self):
        self.historia = lista()
    
    funkcja dodaj(self, a, b):
        wynik = a + b
        self.historia.append(f"{a} + {b} = {wynik}")
        zwróć wynik
    
    funkcja pokaz_historie(self):
        jeżeli długość(self.historia) == 0:
            drukuj("Brak operacji w historii")
        inaczej:
            dla operacja w self.historia:
                drukuj(operacja)

kalk = Kalkulator()
kalk.dodaj(5, 3)
kalk.dodaj(10, 7)
kalk.pokaz_historie()
```

## 🔧 Jak to działa

1. Skrypt czyta plik `.ply` z polskim kodem
2. Używa `sed` do zamiany polskich słów kluczowych na angielskie
3. Tworzy tymczasowy plik `.py` z przetłumaczonym kodem
4. Wyświetla przetłumaczony kod (dla debugowania)
5. Uruchamia kod za pomocą `python3`
6. Automatycznie usuwa tymczasowy plik

## 📋 Wskazówki

- Używaj rozszerzenia `.ply` dla plików z polskim Pythonem
- Skrypt automatycznie pokazuje przetłumaczony kod przed uruchomieniem
- Wszystkie standardowe biblioteki Pythona działają normalnie
- Możesz mieszać polskie i angielskie słowa kluczowe

## 🐛 Rozwiązywanie problemów

### Błąd: "Plik nie istnieje"
Sprawdź czy ścieżka do pliku jest prawidłowa:
```bash
ls -la twój_skrypt.ply
```

### Błąd: "Permission denied"
Nadaj uprawnienia wykonywalne:
```bash
chmod +x plython
```

### Python nie znaleziony
Zainstaluj Python 3:
```bash
# Ubuntu/Debian
sudo apt install python3

# macOS
brew install python3
```

## 📄 Licencja

MIT License - możesz używać, modyfikować i dystrybuować ten kod zgodnie z warunkami licencji MIT.

## 🤝 Współtworzenie

Wkład w rozwój projektu jest mile widziany! Możesz:
- Zgłaszać błędy (issues)
- Proponować nowe funkcje
- Wysyłać pull requesty
- Poprawiać dokumentację

## 📞 Kontakt

Jeśli masz pytania lub sugestie, śmiało otwórz issue w tym repozytorium.

---

**Przykład kompletnego workflow:**

```bash
# 1. Utwórz plik z polskim kodem
echo 'drukuj("Witaj z Plythona!")' > test.ply

# 2. Uruchom Plython
./plython test.ply

# Wyjście:
# Przetłumaczony kod:
# print("Witaj z Plythona!")
# ----------------------------------------
# Witaj z Plythona!
```

**Happy coding! 🚀🇵🇱**

## WAŻNE!
To narzędzie zostało częściowo napisane z pomocą sztucznej inteligencji i może zawierać błędy! To README zostało tak napisane niemal całkowicie...
