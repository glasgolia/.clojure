# .clojure


## Running Tests 

See [test-runner] (https://github.com/cognitect-labs/test-runner)

`clj -A:test`
```
  -d, --dir DIRNAME            Name of the directory containing tests. Defaults to "test".
  -n, --namespace SYMBOL       Symbol indicating a specific namespace to test.
  -r, --namespace-regex REGEX  Regex for namespaces to test. Defaults to #".*-test$"
                               (i.e, only namespaces ending in '-test' are evaluated)
  -v, --var SYMBOL             Symbol indicating the fully qualified name of a specific test.
  -i, --include KEYWORD        Run only tests that have this metadata keyword.
  -e, --exclude KEYWORD        Exclude tests with this metadata keyword.
  -H, --test-help              Display this help message
```

### Tag tests
```
(deftest ^:integration test-live-system
     (is (= 200 (:status (http/get "http://example.com")))))
```

Run Only tagged:
`clj -A:test -i :integration`

Run not-tagged:
`clj -A:test -e :integration`

## Upgrade versions
See [depot](https://github.com/Olical/depot)

Upgrade versions of **maven** and **git sha** dependencies

### Show the list of outdated 
`clojure -Aoutdated`  

### Update an edn file
`clojure -Aoutdated --update` or `clojure -Aoutdated --update <\path\to\edn\file`

### Update version for outdated itself:
`clojure -Aoutdated -a outdated`


## Rebel - a better repl
See [git rebel readline](https://github.com/bhauman/rebel-readline)

`clojre -A:rebel`


## clj-new - Creating new projects


## depstar - Deploy your artifacts - uberjar

[see] (https://github.com/seancorfield/depstar)


### Create  uberjar
`clojure -A:depstar -m hf.depstar.jar`

of alias: `clj -A:uberjar`

### Create