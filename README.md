# IP Kalkulačka (IPv4 & IPv6)

*Autor: PB*  
*Licence: [MIT](#mit-license)*

---

Tento projekt obsahuje jednoduchou IP kalkulačku, která zvládá jak **IPv4**, tak **IPv6** adresy, a interaktivní práci s prefixem (maskou) pomocí `range` (slider) ovladače. Uživatel zadá IP adresu (např. `192.168.1.10` nebo `2001:db8::1`) a prefix (např. `/24`, `/64`), poté aplikace vypočítá:

1. **Adresu sítě (Network Address)**  
2. **Broadcast adresu** (u IPv4; u IPv6 se jedná spíše o horní hranici rozsahu)  
3. **První a poslední adresu**  
4. **Počet adres** v daném rozsahu  
5. **Masku v binární podobě**  

## Jak spustit

1. Stáhněte (zkopírujte) soubor `index.html`.
2. Otevřete jej v prohlížeči (např. Chrome, Firefox, Safari).  
3. Zadejte IP adresu a prefix do příslušných polí a klikněte na **Spočítat**.  
4. Pomocí slideru (podpole s prefixem) můžete interaktivně měnit masku/prefix a okamžitě poté znovu kliknout na **Spočítat**.

## Struktura kódu

- **HTML**:  
  - Obsahuje pole pro zadání IP adresy, prefixu (masky) a tlačítko k výpočtu.  
  - V sekci `<script>` jsou funkce pro validaci IPv4 i IPv6, výpočty (bitové operace pro IPv4 a `BigInt` pro IPv6) a zobrazení výsledků.  
  - Obsahuje též táhlo (`range`), které slouží k „drag & drop“ nastavení prefixu.  
- **CSS**:  
  - Základní styl pro rozložení formuláře a výpis výsledků.  

## Často kladené dotazy (FAQ)

1. **Co dělat, když IP kalkulačka hlásí „Neplatná IPv4/IPv6 adresa“?**  
   - Ujistěte se, že zadáváte platný formát. Pro IPv4 stačí tvar `xxx.xxx.xxx.xxx` (0–255). Pro IPv6 např. `2001:db8::1`.  
2. **Jak poznám, že jde o IPv4 nebo IPv6?**  
   - Skript automaticky rozpozná formát a podle toho vypočítá příslušné informace.  
3. **Proč je broadcast adresa vyplněná i u IPv6?**  
   - Ve standardním IPv6 pojetí „broadcast“ sice neexistuje, nicméně ve skriptu je v rámci konzistence vypočtena horní hranice rozsahu.  
4. **Jak se počítá počet adres?**  
   - U IPv4: `2^(32 - prefix)`.  
   - U IPv6: `2^(128 - prefix)`. (Může to být velmi velké číslo.)

## MIT License

