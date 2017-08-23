# Données de Termium

(For English, see below.)

Une collection de jeux de données créés à partir des données ouvertes de TERMIUM Plus<sup>®</sup>. Les fichiers sources peuvent être téléchargés [ici](http://open.canada.ca/data/fr/dataset/94fc74d6-9b9a-4c2e-9c6c-45a5092453aa). Ils sont offerts en vertu de la [licence du gouvernement ouvert - Canada](http://ouvert.canada.ca/fr/licence-du-gouvernement-ouvert-canada).

## Contexte

Dans le cadre d'un projet sur la désambiguïsation sémantique, nous avons créé plusieurs jeux de données à partir des fichiers sources de Termium. 

Pour produire ces jeux de données, nous avons d'abord traité les fichiers sources afin de reproduire les fiches qui sont présentées dans la [version web](http://www.btb.termiumplus.gc.ca/) de Termium. Les fichiers sources sont organisés par domaine, et les fiches qui appartiennent à plus d'un domaine sont représentées par autant d’enregistrements dans les fichiers sources. Pour extraire une fiche des fichiers sources, il faut donc identifier les différents enregistrements correspondant à cette fiche, qui peuvent se trouver dans différents fichiers. Ces enregistrements sont (généralement) identiques à l’exception des champs contenant les domaines. Notre index des fiches de Termium a été produit en fusionnant les enregistrements qui sont identiques à l’exception des champs contenant les domaines, et en accumulant ces domaines.

Nous rendons disponible cet index des fiches de Termium. Les données sont offertes sans garantie, et il est important de noter que des irrégularités dans les fichiers sources engendrent un certain nombre d'écarts entre les fiches dans cet index et celles présentées dans la version web de Termium. Par ailleurs, Termium est mis à jour régulièrement, donc de tels écarts sont inévitables.

Nous offrons également les jeux de données que nous avons produits à partir de cet index, afin d’entraîner et d’évaluer des systèmes de classification de texte et de désambiguïsation sémantique.

## Fichiers

Tous les jeux de données sont des fichiers texte en format TSV (*tab-separated values*), dans lesquels les champs sont séparés par des marques de tabulation. Ces fichiers texte ont été compressés.

`Termium_records.tsv` contient les fiches que nous avons reproduites à partir des fichiers sources de Termium. Chaque ligne contient les termes, domaines, contextes et définitions d’une fiche particulière. Lorsqu’un champ contient plus d’une valeur, la barre verticale (|) est utilisée comme délimiteur. __ATTENTION__ : ce fichier contient plus de 1,3 millions de lignes, donc si on veut l’ouvrir dans un tableur (p. ex. Excel), on doit d’abord le découper en plus petits morceaux.

`Termium_domains.tsv` associe les domaines de Termium à des identificateurs uniques. Ces identificateurs sont utilisés dans les jeux de données décrits ci-dessous.

Les dossiers `Datasets_EN` et `Datasets_FR` contiennent les jeux de données suivants :

- `Terms.tsv`
- `Contexts.tsv`
- `Contexts_single_label.tsv`
- `Definitions.tsv`
- `TSD.tsv`

Les quatre premiers contiennent deux colonnes : la première contient un texte (ou un terme) et la deuxième contient les identificateurs des domaines associés à ce texte dans Termium. Les fichiers nommés `Contexts_single_label.tsv`, dans lesquels un seul domaine est associé à chaque texte, ont été utilisés pour réaliser les expériences décrites dans [1].

Les fichiers nommés `TSD.tsv` contiennent trois colonnes : la première contient un terme, la deuxième contient un contexte qui illustre un des sens du terme, et la troisième contient les identificateurs des domaines associés à ce sens du terme.

Dans les quatre jeux de données, les textes (ou termes) ont été prétraités et annotés. Les tokens sont séparés par des espaces, et chaque token est accompagné de trois annotations séparées par un double tiret bas (__) : les deux premières sont la partie du discours et le lemme, et la dernière indique si le token fait partie d’un des termes décrits dans Termium, au moyen du format IOB (I si le token fait partie d’un terme, O dans le cas contraire, et B si le token correspond au premier mot d’un terme). Le recoupement entre les occurrences de termes a été éliminé au moyen d’une stratégie qui favorise les termes les plus longs.

## Contributeurs et remerciements

Ces jeux de données ont été produits par l’équipe [Parole et Texte](http://crim.ca/fr/equipes/parole-et-texte) du CRIM. Le projet a bénéficié du soutien financier de CANARIE et du ministère de l’Économie, de la Science et de l’Innovation (MESI) du gouvernement du Québec. Ces jeux de données ont été développés dans le cadre du projet [Pacte](http://pacte.crim.ca).

## Références

[1] Bernier-Colborne, G., Barrière, C., Ménard, P. A. “Fine-grained domain classification of text using TERMIUM Plus”. 12th International Conference on Computational Semantics (IWCS) - Workshop on Language, Ontology, Terminology and Knowledge Structures (LOTKS), 2017.

---

# Termium Data

A collection of datasets extracted from the open data of TERMIUM Plus<sup>®</sup>. The source files can be downloaded [here](http://open.canada.ca/data/en/dataset/94fc74d6-9b9a-4c2e-9c6c-45a5092453aa). They are licenced under the [Open Government Licence - Canada](http://open.canada.ca/en/open-government-licence-canada).

## Background

As part of a project on term sense disambiguation, we produced several datasets using the source files of Termium. 

To produce these datasets, we first processed the source files in order to reconstruct the records shown in the [Web version](http://www.btb.termiumplus.gc.ca/) of Termium. The source files are organized by domain, and records that belong to more than one domain are represented by multiple rows in the source files. To extract a record from the source files, we must therefore identify the different rows that correspond to this record, which may reside in different files. These rows will (generally) be identical except for the domain fields. Our index of the records in Termium was produced by merging the rows in the source files that are identical except for the fields containing the domains, and accumulating these domains.

We have made available this index of Termium records. This data is provided as is, and it should be noted that irregularities in the source files produce a number of mismatches between the records in this index and those shown in the Web version of Termium. Such mismatches would be inevitable regardless, because of the fact that Termium is updated regularly.

We have also made available the datasets we produced using this index in order to train and evaluate text classification and term sense disambiguation systems.

## Contents

All datasets are provided as compressed, tab-separated text files. 

`Termium_records.tsv` contains the records we reconstructed from the source files. Each row contains the terms, domains, contexts, and definitions of a record. The pipe symbol (|) is used as a delimiter when a field contains multiple values. __WARNING__: this file contains over 1.3 million rows, so if you need to open it using a spreadsheet (e.g. Excel), split it up into smaller chunks beforehand.

`Termium_domains.tsv` maps the domains in Termium to a unique identifier. These identifiers are used in the datasets described below.

The folders `Datasets_EN` and `Datasets_FR` contain the following datasets:

- `Terms.tsv`
- `Contexts.tsv`
- `Contexts_single_label.tsv`
- `Definitions.tsv`
- `TSD.tsv`

The first four contain two columns: the first contains a text (or term), and the second contains the identifiers of the domains associated with that text in Termium. The files named `Contexts_single_label.tsv`, which contain a single domain label for each text, were used for the experiments described in [1].

The files named `TSD.tsv` contain three columns: the first contains a term, the second contains a context which illustrates one sense of the term, and the third contains the identifiers of the domains associated with that sense of the term.

The texts (or terms) in all four datasets have been preprocessed and annotated. Tokens are separated by spaces, and each token is followed by three annotations, separated by a double underscore: the first two are the part-of-speech and lemma, and the last indicates whether the token is part of a term found in Termium, using the IOB (Inside, Outside, Beginning) format. Overlap between term occurrences was eliminated using a strategy that favours longer terms.

## Credits and acknowledgements

These datasets were produced by the [Speech and Text](http://crim.ca/en/teams/speech-and-text) team at CRIM. The project was supported by CANARIE and the *ministère de l’Économie, de la Science et de l’Innovation* (MESI) of the Government of Québec. The datasets were developed as part of the [Pacte](http://pacte.crim.ca) project.

## References

[1] Bernier-Colborne, G., Barrière, C. and Ménard, P. A. “Fine-grained domain classification of text using TERMIUM Plus”. 12th International Conference on Computational Semantics (IWCS) - Workshop on Language, Ontology, Terminology and Knowledge Structures (LOTKS), 2017
