# Pimcore Documentation

Pimcore documentation generator built on [daux.io](http://daux.io/). Uses Daux as composer dependency instead of demanding
to fork and alter the Daux repo itself. 


## Usage

After running a `composer install` you can build the documentation with the following steps.


1. Prepare rendering with the prepare command. The path is the path to the `doc` directory
   in the Pimcore repository. 
   
    ```
    $ bin/console prepare <path to docs>
    ```
   
2. View in live mode (optional)

    ```
    $ bin/console serve
    ```
    
3. Generate static files

    ```
    $ bin/console generate
    ```
    
Generated files will be written to `build/static`. The `prepare` command is only needed everytime you change documentation
files or files in `config` as it takes care of copying those files to the temporary `build/` dir and renaming `README.md`
to `_index.md`.


## Select the config version to use

There are multiple configuration files in the `config` directory which will be merged with [`default.json`](./config/default.json)
in the prepare command. You can choose which version to use by passing the `--config` option:

    # use the Pimcore 4 config
    $ bin/console prepare --config 4.x.x


## Theme development

Install prerequisites:

* NodeJS
* Yarn
* Install dependencies: `yarn`

Alter files in `themes/pimcore`, run `gulp` to build CSS and JS files and commit generated files back to the repository. 
