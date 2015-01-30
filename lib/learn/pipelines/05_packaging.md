## Packaging

The result of a passed build is a deployable package. The package is created at
the end of the build pipeline and contains all the assets and code that are
inside the working directory.

This package can be the input of a deployment pipeline. For advanced use-cases
it can make sense to create a sub-selection to be packaged, this is for instance
applicable to compiled languages whereby the compiled output is the selection
that you want to actually deploy.

Another example is the minification of javascript files which should be made
available for deployment.

You can write the files you want packaged to the `$WERCKER_OUTPUT_DIR`.
This will change the default behavior of packaging the working directory and
will package the files in the `$WERCKER_OUTPUT_DIR`. Here is an example that
builds a [Jekyll](http://jekyllrb.com) website and places the static html
output in the `$WERCKER_OUTPUT_DIR`.

``` yaml
build:
    - bundle-install
    - script:
        name: generate static site
        code: |-
          bundle exec jekyll build --trace --destination "$WERCKER_OUTPUT_DIR"
```

The static html files will be copied into the `$WERCKER_OUTPUT_DIR` folder
readying them for the deployment pipeline.


[&lsaquo; Using env vars](/learn/pipelines/04_using-env-vars.html "nav previous pipelines")
[Steps &rsaquo;](/learn/steps/01_introduction.html "nav next steps")