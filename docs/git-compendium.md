# Kompendium Git i GitHub

Praktyczny przewodnik: od polecenia słownego do właściwych komend Git.

## 1. Git i GitHub — czym się różnią?

**Git** to system kontroli wersji działający lokalnie. Pozwala zapisywać historię zmian, tworzyć gałęzie, porównywać wersje i scalać pracę.

**GitHub** to serwis przechowujący zdalne repozytoria Git. Umożliwia między innymi współpracę, tworzenie Pull Requestów i przeglądanie historii projektu przez przeglądarkę.

Można korzystać z Gita bez GitHuba, ale GitHub opiera się na repozytoriach Git.

## 2. Najważniejszy model pracy

Podczas pracy z plikami występują trzy podstawowe obszary:

1. **Katalog roboczy** — pliki, które aktualnie edytujesz.
2. **Staging area** — zmiany przygotowane do następnego commita.
3. **Repozytorium lokalne** — historia zapisanych commitów.

Typowy przepływ wygląda następująco:

```text
edycja pliku → git add → git commit
```

Synchronizacja z repozytorium zdalnym odbywa się osobno:

```text
repozytorium lokalne → git push → GitHub
```

## 3. Jak czytać `git status -sb`

Polecenie:

```bash
git status -sb
```

pokazuje skrócony stan repozytorium i bieżącą gałąź.

Przykładowe oznaczenia:

| Status | Znaczenie |
|---|---|
| `??` | Nowy plik, którego Git jeszcze nie śledzi |
| `A ` | Nowy plik dodany do staging area |
| ` M` | Śledzony plik zmieniony w katalogu roboczym |
| `M ` | Zmiana przygotowana w staging area |
| `AM` | Nowy plik jest w staging area, ale później został ponownie zmieniony |
| `UU` | Konflikt: plik został zmieniony po obu stronach |

W zapisie dwukolumnowym:

- pierwsza kolumna opisuje staging area;
- druga kolumna opisuje katalog roboczy.

Dlatego:

```text
AM docs/git-cheatsheet.md
```

oznacza, że nowy plik został dodany przez `git add`, a następnie ponownie zmodyfikowany.

## 4. `git diff` a `git diff --staged`

```bash
git diff
```

pokazuje zmiany w katalogu roboczym, które nie znajdują się jeszcze w staging area.

```bash
git diff --staged
```

pokazuje zmiany przygotowane do następnego commita.

Po wykonaniu `git add` Git zapisuje w staging area konkretną wersję pliku. Dalsza edycja pliku nie aktualizuje jej automatycznie — trzeba ponownie wykonać `git add`.
