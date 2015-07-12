# section tagset

Categories from Kafkas et. al. , see http://europepmc.org/ftp/oa/SectionTagger/ 

Note that Markdown does not support pipes (|) in tables and this has been replaced by character 124 (&#124, see source). <pre>regex</pre> represents the range of regexes which covers most journals - it can be extended. <pre>xpath</pre> represents some Xpath expressions to search.

| human tag | id | comments  | regex | xpath |
| --------- | -- | --------- | ----- | ----- |
| Conclusion & Future Work | epmc:CONCL |	<pre>(conclusion&#124;key message&#124;future&#124;summary&#124;recommendation&#124; implications for clinical practice&#124;concluding remark)</pre> |
| Case Report	| epmc:CASE | <pre>(case study report&#124;case report&#124;case presentation&#124;case description&#124;case summary&#124;case history&#124; (\d)+\. case&#124;^ case (\d)+$&#124;^case$&#124;^cases$)</pre> |
| Supplementary Data	| epmc:SUPPL | 1.Check a given title for <pre>(supplementary&#124;supporting information&#124;supplemental&#124;web extra material)</pre> 2. Check if the content of the <footnote> matches with (supplementary) |
| Keyword	| epmc:KEYWORD |(keyword&#124;key word&#124;key term&#124;index&#124;ocis code&#124;mesh&#124;accession&#124;search term)	|
| Abbreviation	| epmc:ABBR | 1.Extract content of the <glossary> element from a given xml document 2.(abbreviation&#124;glossary) |
| Introduction & Background	| epmc:INTRO |(introduction&#124;background&#124;related literature&#124;literature review&#124; objective&#124; purpose of this study&#124;study (purpose&#124;aim&#124;aims))&#124; (\d)+. (purpose&#124;aims&#124;aim)&#124;(aims&#124;aim&#124;purpose) of the study) &#124; (the&#124;drug&#124;systematic&#124;book) review&#124;review of literature&#124;related work&#124; recent advance)&#124;(^aim$&#124;^aims$&#124;^purpose$&#124;^purposes$&#124;^purpose/aim$&#124; ^purpose of study$&#124;^review$&#124;^reviews$&#124;^minireview$) |
| Materials & Methods	| epmc:METHODS | (method&#124;material&#124;experimental procedure&#124;implementation&#124; methodology&#124;treatment&#124;statistical analysis&#124;(\d)+. Experimental&#124; experimental (section&#124;evaluation&#124;design&#124;approach&#124;protocol&#124;setting&#124;set up&#124;investigation&#124;detail&#124;part&#124;pespective&#124;tool)&#124;study protocol&#124; construction and content&#124;experiment (\d)+&#124;analysis&#124;utility&#124;design&#124; (\d)+\. Theory&#124;theory and&#124;theory of)&#124; (^experiments$&#124;^experimental$&#124;^the study$&#124;^(\d)+. the study$&#124; ^protocol$&#124;^protocols$&#124;^theory$) AND NOT (supplement) |
| Results	| epmc:RESULTS | (result&#124;finding&#124;diagnosis) |
| Discussion	| epmc:DISCUSS | (discussion&#124;management of&#124;(\d)+. management&#124;safety and tolerability&#124;limitations&#124;perspective&#124;commentary&#124;(\d)+. comment&#124;^management$&#124;^comment$&#124;^comments$) |
| Acknowledgement&Funding	| epmc:ACK_FUND | 1.Extract content of the <ack> element from a given xml document 2.Check if the content of the <footnote>  matched with (financial disclosure&#124;support&#124;fund&#124;grant&#124;thank) 3.(funding&#124;acknowledgment&#124;acknowledgement&#124;acknowledgement&#124;acknowlegement&#124;open access&#124;financial support&#124;grant&#124;author note) |
| Author Contribution | epmc:AUTH_CONT |	1.(author&#124; authors'&#124; author's) contribution 2.Check if the content of the <footnote> element matched with (fn-type=”con”) |
| Competing Interest	| epmc:COMP_INT| 1. (competing interest&#124;(conflict&#124;conflicts) of interest&#124;disclosure&#124;declaration) 2. Check if the content of the <footnote> element matched with (fn-type=”conflict”) | 
| References	| epmc:REF  | Extract content of the <ref-list> element from a given xml document |
| Appendix	| empc:APPENDIX | (appendix&#124;appendices) |
| Tables	| epmc:TABLE| Extract content of all <table-wrap> elements from a given xml document |
| Figures	| epmc:FIG  | Extract content of all <fig> elements from a given xml document |




