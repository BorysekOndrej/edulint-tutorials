## Thonny

Thonny je vývojové prostředí určené pro výuku programování a je vhodné pro začátečníky i mírně pokročilé. Thonny automaticky nainstaluje i interpret jazyka Python (nyní ve verzi 3.10.11).

### Instalace a první spuštění

#### Windows

Prvně si stáhněte instalační soubor. Ten můžete najít na [oficiálním webu Thonny](https://thonny.org/). Na něm stačí myší najet na _Windows_ a vybrat doporučenou (_recommended_) variantu.

![Stažení instalačního souboru pro Windows](thonny-website-arrows.png)

Po dokončení stažení nejspíš najdete instalační soubor mezi _staženými soubory_. Spusťte ho a projděte instalátorem. Pokud si s ním nevíte rady, spusťte ho a můžete ho projít například těmito kroky:

- Stiskněte tlačítko _Install for me only (recommended)_
- Stiskněte tlačítko _Next_ (první obrazovka instalátoru je pouze informační)
- Stiskněte tlačítko _Next_ (přijmete tím licenční podmínky)
- Stiskněte tlačítko _Next_ (instalační cestu není třeba měnit)
- Stiskněte tlačítko _Next_ (pozici v Start menu není třeba měnit)
- Zaškrtněte _Create desktop icon_, pak stiskněte tlačítko _Next_
- Stiskněte tlačítko _Install_ (sumarizační stránka je opět jen informační)
- Stiskněte tlačítko _Finish_ (informační stránka o úspěšné instalaci)

Následně můžete Thonny spustit např. ikonkou na ploše nebo z nabídky start vyhledáním `Thonny`. Při prvním spuštění se Thonny zeptá na dvě nastavení:

- Language: doporučujeme nechat na angličtině, čeština je zatím jen v beta verzi (i.e. ještě není úplná)
- Initial Settings: nechte na Standard.

Co pak? Zkuste si v Thonny napsat nějaký kód (nebo zkopírovat do něj následující) a soubor uložit. Poté ho můžete spustit pomocí tlačítka s bílou šipkou v zeleném kolečku nebo pomocí klávesy F5.

```python
for i in range(5):
    print(i)
```

#### Linux

Instalaci lze udělat buď obvyklým způsobem z distribučních balíčků (např. `sudo apt install thonny`), nebo do již existujícího Pythonu pomocí `python3 -m pip install --user thonny`.

Pokud po instalaci nefunguje příkaz `thonny`, můžete zkusit `~/.local/bin/thonny`. Pokud zafunguje, odporučujeme buď adresář přidat do environmentální proměnné `PATH` nebo přidat do `.bashrc` následující řádek `alias thonny="~/.local/bin/thonny"`. Po změně `.bashrc` je nutné otevřít nový terminál, aby se změny aplikovali.

#### macOS

Stáhněte si instalační program z [oficiální stránky](https://thonny.org/) a nainstalujte ho obvyklým způsobem.

## EduLint

**EduLint** je nástroj, který detekuje různé druhy programátorských chyb, od nevhodných programovacích konstrukcí přes porušení stylistických konvencí. K řadě chyb je také schopen ukázat, proč je daný problém vhodné řešit a případně i na ukázkových kódech ukázat, jak ho lze vyřešit.

Pokud si chcete EduLint spustit sami, můžete to udělat jedním ze tří způsobů:

- pomocí [webového rozhraní](https://edulint.com),
- nainstalovat si ho jako Python balíček pomocí pip,
- nainstalovat si ho do Thonny.

V tomto návodu popíšeme instalaci do Thonny.

### Thonny-EduLint

Spusťte Thonny a proveďte v něm následující tři kroky:

1. *Tools* → *Manage plug-ins...* → vyhledejte *thonny-edulint* → vyberte *thonny-edulint* ze seznamu výsledků → stiskněte tlačítko *Install*

2. *Tools* → *Manage packages...* → vyhledejte *edulint* → vyberte *edulint* ze seznamu výsledků → stiskněte tlačítko *Install*

3. Zavřete a znovu otevřete Thonny

<img src="thonny_edulint_install.png" width="700">

Po novém otevření Thonny byste měli nově vidět ikonku koštěte v hlavní liště. Že vše funguje si můžete vyzkoušet tak, že v Thonny otevřete libovolný Python soubor a analýzu spustíte buď kliknutím na ikonku koštěte, nebo klávesovou zkratkou F9.

EduLint lze spustit pouze na uložený soubor. Pokud tedy vytváříte úplně nový soubor, nezapomeňte ho uložit, než spustíte analýzu. Pokud otvíráte již existující soubor, EduLint vždy soubor před analýzou automaticky uloží na disk.

<img src="thonny_running.png" width="700">

A jak případně později upgradovat EduLint na novější verzi? Postup je stejný jako při instalaci, pouze se Vám místo tlačítka Install zobrazí tlačítko <Upgrade>.


