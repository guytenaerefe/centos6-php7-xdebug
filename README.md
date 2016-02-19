## Dockerfile

This repository contains a Dockerfile (in development) for CentOS 6 using PHP7.0.3

Run the machines (-d for background):
    
    docker-compose up -d
    
For local debugging in Vim using Vdebug add this to your `.vimrc`:

    command Docker let g:vdebug_options['server'] = $DOCKERIP

Add the following to for example your `.bashr` after the web machine is up.
    
    # Get dockerip for use in vim
    function envdockerip() {
        export DOCKERIP=$(ip addr ls docker0 | awk '/inet / {print $2}' | cut -d"/" -f1)
        echo 'Set docker ip as $DOCKERIP:' $DOCKERIP
     }

Happy remote debugging.
