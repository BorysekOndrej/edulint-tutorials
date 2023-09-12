EduLint je linter poskytující zpětnou vazbu začínajícím programátorům na kvalitu kódu. Upozorňuje studenty na porušení některých pravidel z PEP8, na některé zdroje chyb a na časté problémy s kvalitou kódu.

EduLint je k dispozici jako pip balíček, skrz webové rozhraní na [edulint.com](https://edulint.com/) a jako plugin do IDE Thonny (balíček `thonny-edulint`).

EduLint nabízí řadu různých konfigurací. V rámci IB113 budeme používat konfiguraci pro CS0. Aby EduLint zkontroloval soubor pomocí této konfigurace, je třeba, aby studentův soubor obsahoval řádek "# edulint: config=cs0". Buďto je možné studenty upozornit, aby tento řádek přidali, nebo lépe ho přidat rovnou do kostry.

EduLint je možné nainstalovat skrze pip (jméno balíčku je `edulint`). Spustit ho pak lze příkazem

```
python3 -m edulint -o config=cs0 -o ignore-infile-config-for=all FILES-OR-DIRS
```

- Možnost `-o config=cs0` zajistí, že se použije vyžadovaná konfigurace CS0.
- Možnost `-o ignore-infile-config-for=all` zajistí, že pokud student provede změny v konfiguraci (například vypne všechny kontroly), tyto změny se neprojeví. Zároveň pokud student použije komentáře, které vypínají některé kontroly (například `# noqa` pro Flake8), tyto komentáře způsobí, že EduLint emituje defekt, který na toto upozorňuje.
- Pokud je příkazu předán adresář, rekurzivně ho prohledá a zkontroluje všechny `.py` soubory v něm obsažené.

Je možné rozšířit sadu detekovaných defektů zapnutím rozšiřující skupiny defektů, z příkazové řádky pomocí možnosti `-o set-groups=enhancement`, nebo přidáním řádku `# edulint: set-groups=enhancement` do kontrolovaného souboru. Tímto způsobem si studenti můžou říct o více zpětné vazby, nebo o pokročilejší.

S dotazy kontaktujte Aničku Řechtáčkovou (anna.rechtackova@mail.muni.cz).
