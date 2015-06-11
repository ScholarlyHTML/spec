# tables

Colons can be used to align columns.

| human tag       | id           | purpose  |
| ------------- |-------------| -----|
| Conclusion & Future Work | epmc:CONCL |	(conclusion@@key message@@future@@summary@@recommendation@@ implications for clinical practice@@concluding remark) |
| Case Report	| epmc:CASE | <pre>(case study report@@case report@@case presentation@@case description@@case summary@@case history@@ (\d)+\. case@@^ case (\d)+$@@^case$@@^cases$)</pre> |
| Supplementary Data	| epmc:SUPPL | 1.Check a given title for <pre>(supplementary@@supporting information@@supplemental@@web extra material)</pre> 2. Check if the content of the <footnote> matches with (supplementary) |
| Keyword	| xx |(keyword@@key word@@key term@@index@@ocis code@@mesh@@accession@@search term)	|
| Abbreviation	| epmc:ABBR | 1.Extract content of the <glossary> element from a given xml document 2.(abbreviation@@glossary) |
| Introduction & Background	| epmc:INTRO |(introduction@@background@@related literature@@literature review@@ objective@@ purpose of this study@@study (purpose@@aim@@aims))@@ (\d)+. (purpose@@aims@@aim)@@(aims@@aim@@purpose) of the study) @@ (the@@drug@@systematic@@book) review@@review of literature@@related work@@ recent advance)@@(^aim$@@^aims$@@^purpose$@@^purposes$@@^purpose/aim$@@ ^purpose of study$@@^review$@@^reviews$@@^minireview$) |
| Materials & Methods	| epmc:METHODS | (method@@material@@experimental procedure@@implementation@@ methodology@@treatment@@statistical analysis@@(\d)+. Experimental@@ experimental (section@@evaluation@@design@@approach@@protocol@@setting@@set up@@investigation@@detail@@part@@pespective@@tool)@@study protocol@@ construction and content@@experiment (\d)+@@analysis@@utility@@design@@ (\d)+\. Theory@@theory and@@theory of)@@ (^experiments$@@^experimental$@@^the study$@@^(\d)+. the study$@@ ^protocol$@@^protocols$@@^theory$) AND NOT (supplement) |
| Results	| epmc:RESULTS | (result@@finding@@diagnosis) |
| Discussion	| epmc:DISCUSS | (discussion@@management of@@(\d)+. management@@safety and tolerability@@limitations@@perspective@@commentary@@(\d)+. comment@@^management$@@^comment$@@^comments$) |
| Acknowledgement&Funding	| epmc:ACK_FUND | 1.Extract content of the <ack> element from a given xml document 2.Check if the content of the <footnote>  matched with (financial disclosure@@support@@fund@@grant@@thank) 3.(funding@@acknowledgment@@acknowledgement@@acknowledgement@@acknowlegement@@open access@@financial support@@grant@@author note) |
| Author Contribution | epmc:AUTH_CONT |	1.(author@@ authors'@@ author's) contribution 2.Check if the content of the <footnote> element matched with (fn-type=”con”) |
| Competing Interest	| epmc:COMP_INT| 1. (competing interest@@(conflict@@conflicts) of interest@@disclosure@@declaration) 2. Check if the content of the <footnote> element matched with (fn-type=”conflict”) | 
| References	| xx | Extract content of the <ref-list> element from a given xml document |
| Appendix	| xx | (appendix@@appendices) |
| Tables	| xx | Extract content of all <table-wrap> elements from a given xml document |
| Figures	| xx | Extract content of all <fig> elements from a given xml document |




