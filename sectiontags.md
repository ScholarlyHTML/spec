# section tagset

Categories from Kafkas et. al. , see http://europepmc.org/ftp/oa/SectionTagger/ 

Note that Markdown does not support pipes (|) in tables and this has been replaced by character 124 ( &#124;, see source). <pre>regex</pre> represents the range of regexes which covers most journals - it can be extended. <pre>xpath</pre> represents some XPath expressions to search.


| human tag       | id          | regex    | xpath     | comments |
| --------------- | ----------- | -------- | --------- | -------- |
| Conclusion & Future Work | epmc:CONCL |	<pre>(conclusion&#124;key message&#124;future&#124;summary&#124;recommendation&#124;implications for clinical practice&#124;concluding remark)</pre> |  | |
| Case Report	| epmc:CASE | <pre>(case study report&#124;case report&#124;case presentation&#124;case description&#124;case summary&#124;case history&#124; (\d)+\. case&#124;^ case (\d)+$&#124;^case$&#124;^cases$)</pre> |  |  |
| Supplementary Data	| epmc:SUPPL | <pre>(supplementary&#124;supporting information&#124;supplemental&#124;web extra material)</pre> | <pre>//footnote[contains.,'supplementary']</pre> | |
| Keyword	| epmc:KEYWORD |<pre>(keyword&#124;key word&#124;key term&#124;index&#124;ocis code&#124;mesh&#124;accession&#124;search term)</pre>	|  |  |
| Abbreviation	| epmc:ABBR |  <pre>(abbreviation&#124;glossary)</pre> | <pre>//glossary</pre> | | |
| Introduction & Background	| epmc:INTRO |<pre>(introduction&#124;background&#124;related literature&#124;literature review&#124; objective&#124; purpose of this study&#124;study (purpose&#124;aim&#124;aims))&#124; (\d)+. (purpose&#124;aims&#124;aim)&#124;(aims&#124;aim&#124;purpose) of the study) &#124; (the&#124;drug&#124;systematic&#124;book) review&#124;review of literature&#124;related work&#124; recent advance)&#124;(^aim$&#124;^aims$&#124;^purpose$&#124;^purposes$&#124;^purpose/aim$&#124; ^purpose of study$&#124;^review$&#124;^reviews$&#124;^minireview$)</pre> | | |
| Materials & Methods	| epmc:METHODS | <pre>(method&#124;material&#124;experimental procedure&#124;implementation&#124; methodology&#124;treatment&#124;statistical analysis&#124;(\d)+. Experimental&#124; experimental (section&#124;evaluation&#124;design&#124;approach&#124;protocol&#124;setting&#124;set up&#124;investigation&#124;detail&#124;part&#124;pespective&#124;tool)&#124;study protocol&#124; construction and content&#124;experiment (\d)+&#124;analysis&#124;utility&#124;design&#124; (\d)+\. Theory&#124;theory and&#124;theory of)&#124; (^experiments$&#124;^experimental$&#124;^the study$&#124;^(\d)+. the study$&#124; ^protocol$&#124;^protocols$&#124;^theory$) AND NOT (supplement) </pre>| | |
| Results	| epmc:RESULTS | <pre>(result&#124;finding&#124;diagnosis)</pre> | | |
| Discussion	| epmc:DISCUSS | <pre>(discussion&#124;management of&#124;(\d)+. management&#124;safety and tolerability&#124;limitations&#124;perspective&#124;commentary&#124;(\d)+. comment&#124;^management$&#124;^comment$&#124;^comments$)</pre> | | |
| Acknowledgement&Funding	| epmc:ACK_FUND |  <pre>(funding&#124;acknowledgment&#124;acknowledgement&#124;acknowledgement&#124;acknowlegement&#124;open access&#124;financial support&#124;grant&#124;author note) </pre> | <pre>//ack&#124;//footnote[contains(."financial disclosure" or contains(.,"support") or contains(.,"fund") or contains(.,"grant") or contains(.,"thank")]</pre> | |
| Author Contribution | epmc:AUTH_CONT |	<pre>(author&#124; authors'&#124; author's) contribution</pre> | <pre>//footnote[@fn-type='con']</pre> | |
| Competing Interest	| epmc:COMP_INT|  <pre>(competing interest&#124;(conflict&#124;conflicts) of interest&#124;disclosure&#124;declaration)</pre> | <pre>//footnote[@fn-type='conflict']</pre> | |
| References	| epmc:REF  | <pre>(References&#124;Bibliography&#124;Citation)</pre> | <pre>//ref-list</pre> | |
| Appendix	| empc:APPENDIX | <pre>(appendix&#124;appendices)</pre> | | |
| Tables	| epmc:TABLE| <pre>(Tab(le)?)</pre>| <pre>//table-wrap</pre> | | 
| Figures	| epmc:FIG  | <pre>(Fig(ure)?| <pre>//fig</pre> | |




