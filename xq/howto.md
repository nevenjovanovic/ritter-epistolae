# Queries and results

## Clausulae (verse endings)

Create databases of three-words, two-words, and single-word clausulae for Ovid and Ritter Vitezović. Use XQuery scripts [ovidfv-clausulae-3.xq](ovidfv-clausulae-3.xq), [ovidfv-clausulae-2.xq](ovidfv-clausulae-2.xq), [ovidfv-clausulae-1.xq](ovidfv-clausulae-1.xq) and [vitezovicfv-clausulae-3.xq](vitezovicfv-clausulae-3.xq), [vitezovicfv-clausulae-2.xq](vitezovicfv-clausulae-2.xq), [vitezovicfv-clausulae-1.xq](vitezovicfv-clausulae-1.xq).

Then, join Ovid's and Ritter Vitezović's clausulae, return matching strings with indices of nodes in the main text database. This is done with the XQuery scripts [vitezovicfv3-ovidfv3-join-notfuzzy.xq](vitezovicfv3-ovidfv3-join-notfuzzy.xq) (for literal matches), [vitezovicfv3-ovidfv3-join.xq](vitezovicfv3-ovidfv3-join.xq) (for fuzzy matches); [vitezovicfv2-ovidfv2-join-notfuzzy.xq](vitezovicfv2-ovidfv2-join-notfuzzy.xq) and [vitezovicfv2-ovidfv2-join-fuzzy.xq](vitezovicfv2-ovidfv2-join-fuzzy.xq); and [vitezovicfv1-ovidfv1-join-notfuzzy.xq](vitezovicfv1-ovidfv1-join-notfuzzy.xq) -- we discovered that, for the single-word clausulae, literal search provides enough interesting information.

Results of queries are written as XML files, but they are basically HTML tables. This makes the results easy to include into an HTML template page. The results are: [vitezovic-ovid-claus3-fuzzy.html](../reports/vitezovic-ovid-claus3-fuzzy.html), [vitezovic-ovid-claus3.html](../reports/vitezovic-ovid-claus3.html); [vitezovic-ovid-claus2-fuzzy.html](../reports/vitezovic-ovid-claus2-fuzzy.html) and [vitezovic-ovid-claus2.html](../reports/vitezovic-ovid-claus2.html); [vitezovic-ovid-claus1.html](../reports/vitezovic-ovid-claus1.html). They can also be accessed on the `croala.ffzg.unizg.hr` server.

## Incipits (first words)

First, create databases of incipits using scripts [vitezovicfv-incipit-1.xq](vitezovicfv-incipit-1.xq), [vitezovicfv-incipit-2.xq](vitezovicfv-incipit-2.xq), [vitezovicfv-incipit-3.xq](vitezovicfv-incipit-3.xq) (the process could be unified by isolating variables).

Then, produce XML / HTML tables (`.xml` files in the [reports](../reports/) directory) listing the phrase (first three or two words, or just the first word) using the [vitezovicfv2inc-ovidfv2inc-join-notfuzzy.xq](vitezovicfv2inc-ovidfv2inc-join-notfuzzy.xq) XQuery, searching for literal (not fuzzy) matches. The script uses a map to process all three pairs of databases (first word, first two words, first three words in Ovid and Ritter Vitezović). It takes about 5.7 minutes to execute.

Finally, insert the tables into a static HTML template (I use Emacs with the `C-x i` command; the process could be further automated), producing result pages [vitezovic-ovid-incipit-3.html](../reports/vitezovic-ovid-incipit-3.html), [vitezovic-ovid-incipit-2.html](../reports/vitezovic-ovid-incipit-2.html), [vitezovic-ovid-incipit-1.html](../reports/vitezovic-ovid-incipit-1.html).
