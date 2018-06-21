# julia_singularity

1) Run:
`sudo singularity --debug build test.simg Singularity |& tee sing-build.output`
to build the image

2) Go into the image:
`singularity shell test.simg`

3) View the results:
`cat /usr/local/data/results.txt`
