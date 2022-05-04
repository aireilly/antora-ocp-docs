# antora-ocp-docs

Based on https://github.com/stackrox/docs-tools/

1. Run the transformation script:

   ```bash
   ./ocp-transform.sh -d build -b enterprise-4.10
   ```
1. Make a new directory and copy the generated files:

   ```bash
   cd ~
   mkdir -p antora-ocp-test
   cp -r <path-to-dir>/build/ antora-ocp-test/
   ```
1. Git init:

   ```bash
   cd antora-ocp-test
   git init
   git add .
   git commit -am 'Docs init'
   ```
1. Install Antora:
   ```bash
   npm i -g @antora/cli@2.3 @antora/site-generator-default@2.3
   ```

1. Run the Antora build:

   ```bash
   npx antora --fetch playbook.yml
   ```

1. Install the http-server package globally using npm:

   ```bash
   npm i -g http-server
   ```

1. Serve the site locally:

   ```bash
   http-server build/site -c-1
   ```

To do:
1. ~~Use the `patch-files` script to patch xrefs in the generated files.~~
1. ~~Use the `generate-nav` script to generate the navigation.~~
1. ~~Add `product-title` and `product-version` variables in the common attributes file.~~
1. ~~Use an Antora playbook yml with the default UI bundle to generate the site.~~
1. Check build warnings and errors.
1. Add indexing and search capabilities.
