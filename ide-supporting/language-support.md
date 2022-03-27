# Language Support

## 1. Run

**EDQL** script support run request action directly on **Intellij** by click right **Run** icon or use the **Run shortcut**.

### 1.1 Run Single Request

We can run single request by click the request right icon directly or when cursor stay on the request action block use the Run shortcut directly. it will only run current request action and return current request action response.

### 1.2 Run Multiple Requests

If EDQL script has multiple request actions, we can run all request actions when cursor not stay on any request action block and use Run shortcut to run whole requests. For multiple request actions, multiple responses will return.

### 1.3 Live Templates

**EDQL** plugin already defined the common used Live Templates for intelligence, easily and quickly to write the request action or query conditions, so when input the below keyword, the Live Template will automatically expand.

Defined Live Templates:

*   search

    ```
    POST $EXPR$/_search
    {
      "query": {
        "bool": {
          "must": [
          ]
        }
      }
    }
        
    ```
*   term

    ```
    {
      "term": {
        "$EXPR$": "$V$"
      }
    },
        
    ```
*   clusterHealth

    ```
    GET _cluster/health
        
    ```
*   clusterStats

    ```
    GET _cluster/stats
        
    ```
*   catIndices

    ```
    GET _cat/indices?v
        
    ```
*   catHealth

    ```
    GET _cat/health?v
        
    ```
*   catNodes

    ```
    GET _cat/nodes?v
        
    ```
*   aggs

    ```
    "aggs": {
      "$E$": {
        $P$
      }
    }
        
    ```
*   term

    ```
    {
      "term": {
        "$EXPR$": "$V$"
      }
    },
        
    ```
*   terms

    ```
    {
      "terms": {
        "$EXPR$": [$V$]
      }
    }
        
    ```
*   bool

    ```
    "bool": {
      $EXPR$
    }
        
    ```
*   avg

    ```
    "aggregations": {
      "$P1$": {
        "avg": {
          "field": "$EXPR$"
       }
      }
    }
        
    ```
*   count

    ```
    GET $E$/_count
        
    ```
*   from

    ```
    "from": $EXPR$,
        
    ```
*   size

    ```
    "size": $EXPR$,
        
    ```
*   qbm

    ```
    {
      "query": {
        "bool": {
          "must": [
            $EXPR$
          ]
        }
      }
    }
        
    ```
*   qbf

    ```
    {
      "query": {
        "bool": {
          "filter": [
            $EXPR$
          ]
        }
      }
    }
        
    ```
*   script

    ```
    {
      "script": {
         "script": "$EXPR$"
      }
    },
        
    ```
*   range

    ```
    {
      "range": {
       "$EXPR$": {
        "gt": $E$,
        "lt": $A$,
       }
      }
    },
        
    ```
*   wildcard

    ```
    {
      "wildcard": {
        "$EXPR$": {
            "value": "*$K$*",
            "boost": 1.0,
        }
      }
    }
        
    ```
*   regexp

    ```
    {
      "regexp" : {
         "$EXPR$" : {
            "value" : "$V$",
          }
      }
    }
        
    ```
*   profile

    ```
    "profile": true,
        
    ```
*   explain

    ```
    "explain": true,
        
    ```
*   mapping

    ```
    GET $E$/_mapping
        
    ```
*   from

    ```
    "from": $EXPR$,
        
    ```
*   field

    ```
    "field": "$EXPR$"
        
    ```
*   sort

    ```
    "sort": [
      {
        "$EXPR$": {
          "order": "$F1$"
        }
      }
    ]
        
    ```
*   exists

    ```
    "exists": {
      "field": "$EXPR$"
    }
        
    ```
*   createIndex

    ```
    PUT /$EXPR$
    {
      "settings": {
      },
      "mappings": {
        "properties": {
            $A$
        }
      }
    }
        
    ```
*   getNodes

    ```
    GET /_nodes
        
    ```
*   source

    ```
    "_source": ["$EXPR$"],
        
    ```
*   tasks

    ```
    GET /_tasks
        
    ```
*   notEmpty

    ```
    {
      "regexp": {
        "$EXPR$": {
          "value": ".+",
        }
      }
    }
        
    ```
*   mustNot

    ```
    "must_not" : [
      $EXPR$
    ],
        
    ```
*   must

    ```
    "must" : [
      $EXPR$
    ],
        
    ```
*   filter

    ```
    "filter" : [
      $EXPR$
    ],
        
    ```
*   should

    ```
    "should" : [
      $EXPR$
    ],
        
    ```

## 3. Highlight

**Highlight** include two parts for edql, for now it supports:

1. highlight for reservered words
   * HOST
   * Authorization
   * local
   * …
2. highlight for key characters
   * brackets
   * number
   * comment
   * colon
   * …

**TODO**: In next step will try to support semantics hilightling

## 4. Autocomplete

**Autocomplete** include two ways autocomplete for edql:

1.  Keywords autocomplete

    Usally include the reservered words and keywords for edql, example: HOST, Authorization, POST, GET, DELETE, PUT, local etc
2.  Live Templates autocomplete

    Live Templates is defined for autocomplete the query dsl, example: qbm, qbf, size, terms, term, queryString, search etc

**TODO**: autocomplete auto integrate with the current dsl, such as remove extra bracket

## 5. Refactor

**Refactor** is an import way for coding, for now edql supports: rename variable, rename function name

## 6. Format

**Format** support to format **Query DSL** blocks, includes: function, variable, JSON block, array block etc. it’s a simple way to make code is clean