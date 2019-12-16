# Contributing to helm s3 plugin

## Development

On regular plugin installation, helm triggers post-install hook
that downloads prebuilt versioned release of the plugin binary and installs it.
To disable this behavior, you need to pass `HELM_S3_PLUGIN_NO_INSTALL_HOOK=true`
to the installer:

    $ HELM_S3_PLUGIN_NO_INSTALL_HOOK=true helm plugin install https://github.com/hex-inc/helm-s3.git
    Development mode: not downloading versioned release.
    Installed plugin: s3

Next, you may want to ensure if you have all prerequisites to build
the plugin from source:

    cd ~/.helm/plugins/helm-s3
    make deps build

If you see no messages - build was successful. Try to run some helm commands
that involve the plugin, or jump straight into plugin development.
