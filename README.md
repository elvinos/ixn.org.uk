# Install Instructions for IXN Project

1. Go to https://github.com/roots/trellis
2. Install trellis/ bedrock following the steps
    1. Requirements
    2. Make sure all dependencies have been installed before moving on:
    3. Virtualbox >= 4.3.10
    4. Vagrant >= 1.8.5
    5. sudo pip install ansible==2.4.0.0
    6. Installation
    7. The recommended directory structure for a Trellis project looks like:
3. example.com/      # → Root folder for the project
├── trellis/      # → Your clone of this repository
└── site/         # → A Bedrock-based WordPress site
    └── web/
        ├── app/  # → WordPress content directory (themes, plugins, etc.)
        └── wp/   # → WordPress core (don't touch!)
    1. See a complete working example in the roots-example-project.com repo.
    2. Create a new project directory: $ mkdir example.com && cd example.com
    3. Clone Trellis: $ git clone --depth=1 git@github.com:roots/trellis.git && rm -rf trellis/.git
    4. Clone Bedrock: $ git clone --depth=1 git@github.com:roots/bedrock.git site && rm -rf site/.git
    5. Local development setup
    6. Configure your WordPress sites in group_vars/development/wordpress_sites.yml and in group_vars/development/vault.yml
    7. Run vagrant up
4. Install Theme
    1. # @ app/themes/ or wp-content/themes/
5. $ composer create-project roots/sage your-theme-name dev-master
    1. Composer
    2. Node.js >= 6.9.x
    3. Yarn
    4. Theme development
    5. Run yarn from the theme directory to install dependencies
    6. Update resources/assets/config.json settings:
        * devUrl should reflect your local development hostname
        * publicPath should reflect your WordPress folder structure (/wp-content/themes/sage for non-Bedrock installs)
    7. Build commands
    8. yarn run start — Compile assets when file changes are made, start Browsersync session
    9. yarn run build — Compile and optimize the files in your assets directory
    10. yarn run build:production — Compile assets for production
