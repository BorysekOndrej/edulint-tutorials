## Linter EduLint

EduLint je linter poskytující zpětnou vazbu začínajícím programátorům na kvalitu
kódu. Upozorňuje studenty na porušení některých pravidel z PEP8, na některé zdroje
chyb a na časté problémy s kvalitou kódu. EduLint využívá a rozšiřuje flake8 a Pylint.

EduLint je k dispozici jako pip balíček, skrz webové rozhraní na
‹https://edulint.com/› a jako plugin do IDE Thonny (balíček `thonny-edulint`).

Ve webovém rozhraní a jako plugin k reportovaným problémům zobrazí i vysvětlení,
proč je daný kód v nepořádku, a příklady, jak kód opravit.

### Konfigurace

EduLint nabízí řadu různých konfigurací. V rámci IB111 se bude používat konfigurace
speciálně pro tento předmět. To, že se má použít daná konfigurace, se detekuje na
základě přítomnosti řádku "from ib111 import week_NN". Zároveň je potřeba, aby
adresář, který obsahuje kontrolovaný soubor, obsahoval i soubor "ib111.toml".
Ve webové verzi je o toto postaráno.

Konfigurace IB111 definuje dvě skupiny problémů s kvalitou kódu: defekty typu error,
které je nutné opravit pro zisk bodů, a defekty typu warning, které slouží pro
zkrášlení kódu, nebo mohou upozornit na případnou chybu, ale není nutné kvůli nim
kód upravovat.

### Spuštění EduLintu

V IB111 je zisk bodů za jakýkoli příklad podmíněný tím, že EduLint pro kód
nereportuje žádný defekt typu error. Studenti dostanou základní výstup z EduLintu do
poznámkového bloku k danému příkladu, více informací si mohou zobrazit, když si
EduLint spustí sami. To můžou provést třemi způsoby (vypsané v pořadí dle
preferovanosti):

#### Thonny plugin

EduLint existuje jako plugin přímo do IDE Thonny (pro žádné jiné IDE v současnosti
plugin neexistuje). Na fakultních počítačích je tento plugin nainstalovaný spolu s
Thonny. Pro studenty existuje návod k jeho instalaci a použití (v ISu Studijní
materiály -> Učební materiály -> text -> ib111.help.html -> Sekce Inštalácia SW ->
Podsekce EduLint). Tento návod ideálně ukažte na nultém cvičení.

#### Webová verze

K EduLintu existuje jednoduché webové rozhraní na ‹https://edulint.com/›.
Do tohoto rozhraní lze nahrát soubor a zkontrolovat ho pomocí tlačítka Check.
I tento web ideálně ukažte na nultém cvičení.

#### Balíček

EduLint je možné nainstalovat skrze pip (jméno balíčku je `edulint`). Spustit ho pak
lze příkazem `python3 -m edulint FILES-OR-DIRS`. Pokud je příkazu předán adresář,
rekurzivně ho prohledá a zkontroluje všechny `.py` soubory v něm obsažené.

Při spuštění skrz příkazovou řádku EduLint nezobrazuje vysvětlení problému ani příklady,
jak ho opravit, je tedy nejméně preferovanou variantou pro studenty.

### Problémy

Pokud při instalaci nebo spuštění vy nebo vaši studenti narazíte na problém, který
nedovedete sami vyřešit, obraťte se na Aničku Řechtáčkovou
(anna.rechtackova@mail.muni.cz, nebo přes Discord). Studenty můžete odkázat na
vlákno na diskuzním fóru určené ke komunikaci ohledně EduLintu, nebo na konzultace
ve středy od 14 v PC hale, které Anička vede.

### Spuštění EduLintu pro kontrolu kódu

Při kontrole samotné je vhodné spouštět EduLint způsobem, který zajistí, že změny
v konfiguraci, které by student sám provedl, se na spuštění neprojeví. Toto lze
provést příkazem

```
python3 -m edulint -o config=ib111.toml -o ignore-infile-config-for=all -o set-groups= FILES-OR-DIRS
```

- Možnost `-o config=ib111.toml` zajistí, že se použije vyžadovaná konfigurace.
  Je možné použít i jinou relativní nebo absolutní cestu k souboru ib111.toml.
- Možnost `-o ignore-infile-config-for=all` zajistí, že pokud student provede
  změny v konfiguraci (například vypne všechny kontroly), tyto změny se neprojeví.
  Zároveň pokud student použije komentáře, které vypínají některé kontroly
  (například `# noqa` pro Flake8), tyto komentáře způsobí, že EduLint emituje
  defekt, který na toto upozorňuje.
- Možnost `-o set-groups=` způsobí, že se vypíšou jenom defekty typu error (ne
  defekty typu warning). Pokud se tato možnost vypustí, bude EduLint reportovat
  i defekty typu warning.
- Pokud je příkazu předán adresář, rekurzivně ho prohledá a zkontroluje všechny
  `.py` soubory v něm obsažené.
