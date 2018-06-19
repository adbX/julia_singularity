Bootstrap: debootstrap
OSVersion: xenial
MirrorURL: http://us.archive.ubuntu.com/ubuntu/

%runscript
    echo "This is what happens when you run the container..."


%post
    echo "Hello from inside the container"
    sed -i 's/$/ universe/' /etc/apt/sources.list
    apt-get update
    apt-get -y install vim cmake python python-pip wget
    apt-get clean

    pip install matplotlib
    wget -q -nc --no-check-certificate https://julialang-s3.julialang.org/bin/linux/x64/0.6/julia-0.6.3-linux-x86_64.tar.gz
    mkdir -p julia
    tar -zxf julia-0.6.3-linux-x86_64.tar.gz -C julia --strip-components 1
    cd ../
    mv julia /usr/local/
	echo 'export PATH="/usr/local/julia/bin:$PATH"' >> /etc/profile
	export JULIA_PKGDIR='/usr/local/julia/local/share/julia/site/'
	export PATH="/usr/local/julia/bin:$PATH"
    julia -e 'Pkg.init()'
%files
    ../docker-julia /usr/local/
#%environment
#	JULIA_LOAD_CACHE_PATH=/usr/local/julia/etc/julia/juliarc.jl
#	JULIA_PKGDIR=/usr/local/julia/local/share/julia/site/
#	PATH=$PATH:/usr/local/julia/bin
#   export JULIA_LOAD_CACHE_PATH PATH JULIA_PKGDIR
