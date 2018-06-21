# julia_singularity

Run:
`sudo singularity --debug build test.simg Singularity |& tee sing-build.output`
to build the image

Go into the image:
`singularity shell test.simg`

View the results:
`cat /usr/local/data/results.txt`
