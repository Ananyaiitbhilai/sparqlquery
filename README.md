# sparqlquery

select ?link ?pred ?pred_inv where {
    <http://dbpedia.org/resource/Berlin_Wall> <http://dbpedia.org/ontology/wikiPageWikiLink> ?link .
    optional {
        <http://dbpedia.org/resource/Berlin_Wall> ?pred ?link
        filter(?pred != <http://dbpedia.org/ontology/wikiPageWikiLink>)
    }
    optional {
        ?link ?pred_inv <http://dbpedia.org/resource/Berlin_Wall>
        filter(?pred_inv != <http://dbpedia.org/ontology/wikiPageWikiLink>)
    }
} order by ?link
