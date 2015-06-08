[NOT YET FINISHED]

Tags must be a subset of HTML5
http://www.w3.org/TR/html-markup/elements.html
along with foreigng namespaces such as MathML, SVG and CML (for chemistry)

Premise: Only HTML5 tags that provide content or metadata are kept. Thus &lt;button> is deleted.
Some tags are rare and have unclear semantics and are translated to &lt;div> or &lt;span> 
with `class` attributes. e.g.
```
<area>... </area> 
```
could be translated to:
```
<div @class="html5_area">... </div> 
```


Some tags (e.g. &lt;em> and &lt;i>) are widely used equivalently. Should we consider keeping the distinction
or should we normalize them to a consistent single value?

All tags that change the document (e.g. &lt;script>) should be removed. This also avoids having to parse Javascript.

Tags linking to external resources may be a problem. &lt;a> is required, but what about &lt;link>?

"keep" can have the values:
 * KEEP ; keep as is
 * DIV ; change to &lt;div @class='html5_{tag}'>
 * SPAN ; change to &lt;span @class='html5_{tag}'>
 * DEL ; discard the tag and contents completely
 * TEXT ; discard the tag, keep the text  

| tag | action | Comments
|-----|--------|--------
|a| KEEP |  
|abbr| KEEP | abbreviations are becoming valuable 
     address| KEEP | addresses are valuable 
     area| KEEP | 
     article| DIV |  
     aside| DEL | 
     audio| KEEP |  
     b| KEEP | merge with &lt;strong> ?
     base| KEEP |  
     bdi| DIV | don't think we can support this yet
     bdo| DIV | don't think we can support this yet 
     blockquote| KEEP |  
     body| KEEP |  
     br| KEEP |  
     button| DEL | 
     canvas| KEEP |  
     caption| KEEP |  
     cite| KEEP |  
     code| KEEP |  
     col| KEEP |  
     colgroup| KEEP |  
     command| DEL | 
     datalist| DEL |  
     dd| KEEP |  
     del| DEL |  
     details| DEL |  
     dfn| KEEP | may be quite useful  
     div| KEEP |  
     dl| KEEP |  
     dt| KEEP |  
     em| KEEP | merge with &lt;i> 
     embed| DEL | presumably always interactive?  
     fieldset| DEL | 
     figcaption| KEEP | very valuable  
     figure| KEEP |  
     footer| KEEP | possibly useful?  
     form| DEL |  
     h1| KEEP |  
     h2| KEEP |  
     h3| KEEP |  
     h4| KEEP |  
     h5| KEEP |  
     h6| KEEP |  
     head| KEEP |  
     header| KEEP |  
     hgroup| DIV |  
     hr| KEEP |  
     html| KEEP |  
     i| KEEP | merge with &lt;em> 
     iframe| DEL |  
     img| KEEP |  
     input| DEL |  
     ins| DIV | we cannot support the semantics  
     kbd| DIV |  or maybe &lt;code>
     keygen| DEL |  
     label| DEL |  
     legend| KEEP |  
     li| KEEP |  
     link| DEL |  
     map| KEEP | 
     mark| SPAN | 
     menu| DEL | This is interactive? 
     meta| KEEP |  
     meter| DEL | probably for interactive
     nav| DEL | 
     noscript| DIV |  
     object| DEL | comments?
     ol| KEEP |  
     optgroup| DEL | 
     option| DEL |  
     output| KEEP | merge with &lt;code>
     p| KEEP |  
     param| DEL | depends on &lt;object> 
     pre| KEEP |  
     progress| DEL | 
     q| KEEP | merge with &ltblockquote>
     rp| DIV | 
     rt| DIV | 
     ruby| DIV | 
     s| KEEP | wrong actions can change meaning  
     samp| KEEP | probably move to &lt;code> 
     script| DEL |  
     section| KEEP |  
     select| DEL |  
     small| SPAN |  
     source| KEEP | we probably won't use it
     span| KEEP |  
     strong| KEEP | merge with &lt;b> 
     style| DEL |  
     sub| KEEP |  
     summary| DEL | (child of <details>, DELeted)
     sup| KEEP |  
     table| KEEP |  
     tbody| KEEP |  
     td| KEEP |  
     textarea| DIV |  
     tfoot| KEEP |  
     th| KEEP |  
     thead| KEEP |  
     time| KEEP | very vakuable (also does dates) 
     title| KEEP |  
     tr| KEEP |  
     track| KEEP | probably a no-op for me 
     u| KEEP |  
     ul| KEEP |  
     var| KEEP | merge &lt;code>? 
     video| KEEP |  
     wbr| KEEP | Complicates parsing; basically an empty SPAN? 
