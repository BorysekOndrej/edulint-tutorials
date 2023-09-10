
## EduLint

«EduLint» je nástroj, který detekuje různé druhy programátorských chyb, od nevhodných programovacích konstrukcí přes porušení stylistických konvencí po některé časté problémy s kvalitou kódu. K řadě nedostatků je také schopen objasnit, proč je daný problém vhodné řešit, a na ukázkových kódech ilustrovat, jak ho lze vyřešit.

Sami můžete EduLint používat jedním ze tří způsobů: nainstalovat si ho do Thonny (doporučeno), skrz $$html <a href="https://edulint.com">webového rozhraní<a> nebo nainstalovat si ho jako Python balíček pomocí pip.

V tomto návodu popíšeme instalaci do Thonny.

### Thonny-EduLint

Spusťte Thonny a proveďte v něm následující tři kroky:

1. ‹Tools› → ‹Manage plug-ins...› → vyhledejte ‹thonny-edulint› → vyberte ‹thonny-edulint› ze seznamu výsledků → stiskněte tlačítko ‹Install›

2. ‹Tools› → ‹Manage packages...› → vyhledejte ‹edulint› → vyberte ‹edulint› ze seznamu výsledků → stiskněte tlačítko ‹Install›

3. Zavřete a znovu otevřete Thonny

$$html <img src="thonny_edulint_install.png" width="700">

Po novém otevření Thonny byste měli nově vidět ikonku koštěte v hlavní liště. Že vše funguje si můžete vyzkoušet tak, že v Thonny otevřete libovolný Python soubor a analýzu spustíte buď kliknutím na ikonku koštěte, nebo klávesovou zkratkou F9.

EduLint lze spustit pouze na uloženém souboru. Pokud tedy vytváříte úplně nový soubor, nezapomeňte ho uložit, než spustíte analýzu. Pokud otvíráte již existující soubor, EduLint vždy soubor před analýzou automaticky uloží na disk.

$$html <img src="thonny_running.png" width="700">

A jak případně později upgradovat EduLint na novější verzi? Postup je stejný jako při instalaci, pouze se Vám místo tlačítka Install zobrazí tlačítko ‹Upgrade›.

### Použití v IB111

IB111 vyžaduje pro EduLint vlastní konfiguraci, dodávanou spolu s kostrami příkladu v souboru ib111.toml. To, že používáte správnou konfiguraci, poznáte tak, že po kontrole souboru se v EduLint tabu píše "used configuration: ib111.toml". Pokud tab neobsahuje žádný text začínající "used configuration", spusťte nejdřív kontrolu kódu. Pokud tab obsahuje například text "used configuration: default", pak správnou konfiguraci nepoužíváte. Pokud nepoužíváte správnou konfiguraci, zkontrolujte, že soubor ib111.toml je obsažený ve stejném adresáři, jako soubor, který právě kontrolujete. Případně můžete do zdrojového kódu vložit řádek "edulint: config=c:\cesta\ke\stazenemu\ib111.toml" (s cestou, na které máte soubor ib111.toml uložený ve svém počítači).

EduLint reportuje dva typy problémů: error a warning. Všechny problémy typu error je nutné vyřešit před úspěšným odevzdáním. Problémy typu warning můžou sloužit ke zlepšení stylu nebo odhalení chyby, ale jejich zapracování není vyžadované. Reportování problémů typu warning je možné vypnout vložením řádku "# edulint: set-groups=" do zdrojového kódu. Jejich vypnutí ovšem nedoporučujeme.

