# UniversalCEFR: Enabling Open Multilingual Research on Language Proficiency Assessment

UniversalCEFR is a largescale, multilingual, multidimensional dataset comprising of texts annotated according to the [CEFR (Common European Framework of Reference)](https://www.coe.int/en/web/common-european-framework-reference-languages/level-descriptions). The collection comprises of a total of **505,807 CEFR-labeled texts** annotated according to the in **13 languages** in 4 script (Latin, Arabic, Devanagari, and Cyrillic).

 - English (en)
 - Spanish (es)
 - German (de)
 - Dutch (nl)
 - Czech (cs)
 - Italian (it)
 - French (fr)
 - Estonian (et)
 - Portuguese (pt)
 - Arabic (ar)
 - Hindi (hi)
 - Russian (ru)
 - Welsh (cy)

To enable open research in both automated readability and language
proficiency assessment, UniversalCEFR comprises curated from educational and learner-oriented resources, standardized into a unified data format to support consistent processing, analysis, and modeling across tasks and languages.

## UniversalCEFR Data Format / Schema
To ensure interoperability, transformation, and machine readability, adopted **standardised JSON format** for each CEFR-labeled text. These fields include the source dataset, language, granularity (document, paragraph, sentence, discourse), production category (learner or reference), and license.

| **Field**         | **Description**                                                                                                                                                                                                                                                                                       |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `title`           | The unique title of the text retrieved from its original corpus (`NA` if there are no titles such as CEFR-assessed sentences or paragraphs).                                                                                                                                                         |
| `lang`            | The source language of the text in ISO 638-1 format (e.g., `en` for English).                                                                                                                                                                                                                         |
| `source_name`     | The source dataset name where the text is collected as indicated from their source dataset, paper, and/or documentation (e.g., `cambridge-exams` from Xia et al., 2016).                                                                                                                             |
| `format`          | The format of the text in terms of level of granularity as indicated from their source dataset, paper, and/or documentation. The recognized formats are the following: [`document-level`, `paragraph-level`, `discourse-level`, `sentence-level`].                                                   |
| `category`        | The classification of the text in terms of who created the material. The recognized categories are `reference` for texts created by experts, teachers, and language learning professionals and `learner` for texts written by language learners and students.                                         |
| `cefr_level`      | The CEFR level associated with the text. The six recognized CEFR levels are the following: [`A1`, `A2`, `B1`, `B2`, `C1`, `C2`]. A small fraction (<1%) of text in UniversalCEFR contains unlabelled text, texts with plus signs (e.g., `A1+`), and texts with no level indicator (e.g., `A`, `B`). |
| `license`         | The licensing information associated with the text (e.g., `CC-BY-NC-SA` or `Unknown` if not stated).                                                                                                                                                                                                                         |
| `text`            | The actual content of the text itself.  


## The UniversalCEFR Data Directory

The current compilation for UniversalCEFR is composed of **26 CEFR-labeled publicly-accessible corpora** which can be used for non-commercial research and derivations can be created as long as it follows the same license.

We provide an informative data directory covering language proficiency-based information including the `language`, `format`, `category`, `annotation method`, `distinct L1 learners`, `inter-annotator agreeement`, and `license information` about the compiled datasets that may be useful for the utility of UniversalCEFR.

| Corpus Name      | Lang (ISO 638-1)   | Format                                               | Category       | Size    | Annotation Method   | Expert Annotators   | Distinct L1                                                                                                        | Inter-Annotator Agreement     | CEFR Coverage   | License                                                       | Resource                                                                           |
|:-----------------|:------------------------|:-----------------------------------------------------|:---------------|:--------|:--------------------|:--------------------|:-------------------------------------------------------------------------------------------------------------------|:------------------------------|:----------------|:--------------------------------------------------------------|:-----------------------------------------------------------------------------------|
| cambridge-exams  | en                      | document-level                                       | reference      | 331     | n/a                 | n/a                 | n/a                                                                                                                | n/a                           | A1-C2           | CC BY-NC-SA 4.0                                               | [Xia et al. (2016)](https://aclanthology.org/W16-0502/)                                                         |
| elg-cefr-en      | en                      | document-level                                       | reference      | 712     | manual              | 3                   | n/a                                                                                                                | n/a                           | A1-C2, plus     | CC BY-NC-SA 4.0                                               | [Breukker (2022)](https://library.oapen.org/bitstream/handle/20.500.12657/59316/1/978-3-031-17258-8.pdf#page=297)                                                          |
| cefr-sp          | en                      | sentence-level                                       | reference      | 17,000  | manual              | 2                   | n/a                                                                                                                | r = 0.75, 0.73                | A1-C2           | CC BY-NC-SA 4.0                                               | [Arase et al. (2022)](https://aclanthology.org/2022.emnlp-main.416/)                                                     |
| elg-cefr-de      | de                      | document-level                                       | reference      | 509     | manual              | 3                   | n/a                                                                                                                | n/a                           | A1-C2           | CC BY-NC-SA 4.0                                               | [Breukker (2022)](https://library.oapen.org/bitstream/handle/20.500.12657/59316/1/978-3-031-17258-8.pdf#page=297)                                                          |
| elg-cefr-nl      | nl                      | document-level                                       | reference      | 3,596   | manual              | 3                   | n/a                                                                                                                | n/a                           | A1-C2, plus     | CC BY-NC-SA 4.0                                               | [Breukker (2022)](https://library.oapen.org/bitstream/handle/20.500.12657/59316/1/978-3-031-17258-8.pdf#page=297)                                                          |
| icle500          | en                      | document-level                                       | learner        | 500     | manual              | 28                  | ur, pa, bg, zh, cs, nl, fi, fr, de, el, hu, it, ja, ko, lt, mk, no, fa, pl, pt, ru, sr, es, sv, tn, tr | Rasch kappa = -0.02           | A1-C2, plus     | CC0 1.0                                                       | [Thwaites et al. (2024)](https://academic.oup.com/applij/advance-article-abstract/doi/10.1093/applin/amae048/7719043)                                                  |
| cefr-asag        | en                      | paragraph-level                                      | learner        | 299     | manual              | 3                   | fr                                                                                                                 | Krippendorf alpha = 0.81      | A1-C2           | CC BY-NC-SA 4.0                                               | [Tack et al. (2017)](https://aclanthology.org/W17-5018/)                                                      |
| merlin-cs        | cs                      | paragraph-level                                      | learner        | 441     | manual              | multiple            | hu, de, fr, ru, pl, en, sk, es                                                                                  | n/a                           | A2-B2           | CC BY-SA 4.0                                                  | [Boyd et al. (2014)](https://aclanthology.org/L14-1488/)                                                     |
| merlin-it        | it                      | paragraph-level                                      | learner        | 813     | manual              | multiple            | hu, de, fr, ru, pl, ,  en, sk, es                                                                                  | n/a                           | A1-B1           | CC BY-SA 4.0                                                  | [Boyd et al. (2014)](https://aclanthology.org/L14-1488/)                                                     |
| merlin-de        | de                      | paragraph-level                                      | learner        | 1,033   | manual              | multiple            | hu, de, fr, ru, pl, ,  en, sk, es                                                                                  | n/a                           | A1-C1           | CC BY-SA 4.0                                                  | [Boyd et al. (2014)](https://aclanthology.org/L14-1488/)                                                     |
| hablacultura     | es                      | paragraph-level                                      | reference      | 710     | manual              | multiple            | n/a                                                                                                                | n/a                           | A2-C1           | CC BY NC 4.0                                                  | [Vasquez-Rodrigues et al. (2022)](https://aclanthology.org/2022.tsar-1.18/)                                     |
| kwiziq-es        | es                      | document-level                                       | reference      | 206     | manual              | multiple            | n/a                                                                                                                | n/a                           | A1-C1           | CC BY NC 4.0                                                  | [Vasquez-Rodrigues et al. (2022)](https://aclanthology.org/2022.tsar-1.18/)                                     |
| kwiziq-fr        | fr                      | document-level                                       | reference      | 344     | manual              | multiple            | n/a                                                                                                                | n/a                           | A1-C1           | CC BY NC 4.0                                                  | Original                                                                          |
| caes             | es                      | document-level                                       | learner        | 30,935  | computer-assisted   | multiple            | pt, zh, ar, fr, ru                                                                                                 | n/a                           | A1-C1           | CC BY NC 4.0                                                  | [Vasquez-Rodrigues et al. (2022)](https://aclanthology.org/2022.tsar-1.18/)                                     |
| deplain-web-doc  | de                      | document-level                                       | reference      | 394     | manual              | 2                   | n/a                                                                                                                | Cohen kappa = 0.85            | A1,A2,B2,C2     | CC-BY-SA-3, ,  CC-BY-4, ,  CC-BY-NC-ND-4, ,  save\_use\_share | [Stodden et al. (2023)](https://aclanthology.org/2023.acl-long.908/)                                                 |
| deplain-apa-doc  | de                      | document-level                                       | reference      | 483     | manual              | 2                   | n/a                                                                                                                | Cohen kappa = 0.85            | A2-B1           | CC-BY-SA-3, ,  CC-BY-4, ,  CC-BY-NC-ND-4, ,  save\_use\_share | [Stodden et al. (2023)](https://aclanthology.org/2023.acl-long.908/)                                                |
| deplain-apa-sent | de                      | sentence-level                                       | reference      | 483     | manual              | 2                   | n/a                                                                                                                | n/a                           | A2-B2           | By request                                                    | [Stodden et al. (2023)](https://aclanthology.org/2023.acl-long.908/)                                                 |
| elle             | et                      | paragraph-level, ,  document-level                   | learner        | 1,697   | manual              | 2                   | n/a                                                                                                                | n/a                           | A2-C1           | CC BY 4.0                                                     | [Vajjala and Rama (2018)](https://aclanthology.org/W18-0515/)                                             |
| efcamdat-cleaned | en                      | sentence-level,,  paragraph-level                    | learner        | 406,062 | manual              | n/a                 | br, zh, tw, ru, sa, mx, de, it, fr, jp, tr                                                                      | n/a                           | A1-C1           | Cambridge                                                     | [Geertzen et al. (2013)](https://www.lingref.com/cpp/slrf/2012/paper3100.pdf) ,  [Shatz (2020)](https://www.jbe-platform.com/content/journals/10.1075/ijlcr.20009.sha) ,  [Huang et al. (2020)](https://www.lingref.com/cpp/slrf/2012/paper3100.pdf) |
| beast2019                       | en                                                   | sentence-level | learner | 3,600               | manual              | multiple                                                                                                           | n/a                           | n/a             | A1-C2                                                         | CC BY SA NC 4.0  |   [Bryant et al. (2019)](https://doi.org/10.18653/v1/W19-4406)                                                                |
| peapl2           | pt                      | paragraph-level                                      | learner        | 481     | manual              | n/a                 | zh, en, es, de, ru, fr, ja, it, nl, ar, pl, ko, ro, sv                                                  | n/a                           | A1-C2           | CC BY SA NC 4.0                                               | [Martins et al. (2019)](http://teitok2.iltec.pt/peapl2/#http://teitok.iltec.pt/peapl2/)                                                         |
| cople2           | pt                      | paragraph-level                                      | learner        | 942     | manual              | n/a                 | zh, en, es, de, ru, fr, ja, it, nl, ar, pl, ko, ro, sv                                                  | n/a                           | A1-C1           | CC BY SA NC 4.0                                               | [Mendes et al. (2016)](https://aclanthology.org/L16-1511/)                                                   |
| zaebuc           | ar                      | paragraph-level                                      | learner        | 214     | manual              | 3                   | en                                                                                                                 | Unnamed kappa = 0.99          | A2-C1           | CC BY SA NC 4.0                                               | [Habash and Palfreyman (2022)](https://aclanthology.org/2022.lrec-1.9/)                                             |
| readme           | ar, en, fr, hi, ru   | sentence-level                                       | reference      | 9,757   | computer-assisted   | 2                   | n/a                                                                                                                | Krippendorf kappa = 0.67,0.78 | A1-C2           | CC BY SA NC 4.0                                               | [Naous et al. (2024)](https://doi.org/10.18653/v1/2024.emnlp-main.682)                                                    |
| apa-lha          | de                      | document-level                                       | reference      | 3,130   | n/a                 | n/a                 | n/a                                                                                                                | n/a                           | A2-B1           | Public                                                        | [Spring et al. (2021)](https://aclanthology.org/2021.ranlp-1.150/)                                                |
| learn-welsh      | cy                      | document-level, ,  sentence-level,,  discourse-level | reference      | 1,372   | manual              | n/a                 | n/a                                                                                                                | n/a                           | A1-A2           | Public                                                        | Original                                                                         |

## Accessing UniversalCEFR 

If you're interested in a specific individual or group of datasets from UniversalCEFR, you may access their transformed, standardised version through the UniversalCEFR Huggingface Org: https://huggingface.co/UniversalCEFR

If you use any of the datasets indexed in UniversalCEFR, **please cite the original dataset papers** they are associated with. You can find them in the data directory above.

Note that there are a few datasets in UniversalCEFR---`EFCAMDAT`, `APA-LHA`, and `DEPlain`---that are not directly available from the UniversalCEFR Huggingface Org as they require users to agree with their Terms of Use before using them for non-commercial research. Once you've done this, you can use the preprocessing Python scripts in `universal-cefr-experiments` repository to transform the raw version to UniversalCEFR version.

## Join the UniversalCEFR Initiative

### Initiators and Collaborators
An initiative started as a collaboration between the researchers around the world who are interested in **1) building a more open and accessible language proficiency assessment data resources** that are also **2) standardised for maximized machine readability**.

 1. Joseph Marvin Imperial (University of Bath, UK and National University Philippines)
 2. Abdullah Barayan (Cardiff University, UK)
 3. Regina Stodden (Bielefeld University, Germany)
 4. Rodrigo Wilkens (University of Exeter, UK)
 5. Ricardo Muñoz Sánchez (University of Gothenburg, Sweden)
 6. Lingyun Gao (UCLouvain, Belgium)
 7. Melissa Torgbi (University of Bath, UK)
 8. Dawn Knight (Cardiff University, UK)
 9.  Gail Forey (University of Bath, UK)
 10. Reka R. Jablonkai (University of Bath, UK)
 11. Ekaterina Kochmar (MBZUAI, UAE)
 12. Robert Reynolds (Brigham Young University, USA)
 13. Eugénio Ribeiro (INESC-ID Lisboa and Instituto Universitário de Lisboa , Portugal)
 14. Horacio Saggion (Universitat Pompeu Fabra, Spain)
 15. Elena Volodina (University of Gothenburg, Sweden)
 16. Sowmya Vajjala (National Research Council, Canada)
 17. Thomas François (UCLouvain, Belgium)
 18. Fernando Alva-Manchego (Cardiff University, UK)
 19. Harish Tayyar Madabushi (University of Bath, UK)

### How to Join?
We want to grow this community of researchers, language experts, and educators to further advance openly accessible CEFR/language proficiency assessment datasets for all. 

If you're interested in this direction and/or have open dataset/s you want to add to UniversalCEFR for better exposure and utility to researchers, please fill up this **[form](https://forms.office.com/e/hjd7ew0M8C)**. 

When we index your dataset to UniversalCEFR, we will cite you and the paper/project from which the dataset came across the UniversalCEFR platforms. 

### Contact
For questions, concerns, clarifications, and issues, please contact [Joseph Marvin Imperial](https://www.josephimperial.com/) (jmri20@bath.ac.uk).

## Reference
Please use the following information when citing UniversalCEFR:

To be updated.




> Written with [StackEdit](https://stackedit.io/).
