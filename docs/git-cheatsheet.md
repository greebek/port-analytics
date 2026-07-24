# Ściąga Git

Najczęściej używane komendy i procedury Git.

## Gdy nie wiesz, w jakim jesteś stanie

```bash
git status -sb
git branch -vv
git log --oneline --decorate --graph --all -10
```

## Podstawowy cykl zmiany

```bash
git status -sb
git diff
git add nazwa-pliku
git diff --staged
git commit -m "Krótki opis zmiany"
git push
```

## Praca na nowej gałęzi

```bash
git switch main
git pull --ff-only
git switch -c feature/nazwa-zmiany
```

Po wykonaniu zmian:

```bash
git add nazwa-pliku
git commit -m "Opis zmiany"
git push -u origin feature/nazwa-zmiany
```

## Po scaleniu Pull Requesta

```bash
git switch main
git pull --ff-only
git branch -d feature/nazwa-zmiany
git fetch --prune
```

## Gdy wynik polecenia otworzy się w `less`

Niektóre polecenia, np. `git log`, `git diff` i `git show`, mogą otworzyć wynik w przeglądarce tekstu `less`.

| Klawisz | Działanie |
|---|---|
| `q` | Wyjście do terminala |
| `Spacja` | Następna strona |
| `b` | Poprzednia strona |
| `↑` / `↓` | Przewijanie po jednej linii |
| `/tekst` | Wyszukanie tekstu |
| `n` | Następny znaleziony wynik |
| `Shift+n` | Poprzedni znaleziony wynik |

Klawisza `q` nie zatwierdzamy Enterem.

Jeżeli polecenie nadal działa, zamiast tylko wyświetlać wynik, można je przerwać:

```text
Ctrl+C
```
