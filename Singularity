Bootstrap: docker
From: pytorch/pytorch:1.4-cuda10.1-cudnn7-devel
%post

    # Update list of available packages, then upgrade them
    apt-get update
    DEBIAN_FRONTEND=noninteractive apt-get -y upgrade
    
    # Utility and support packages
    apt-get install -y screen terminator tmux vim wget 
    apt-get install -y aptitude build-essential cmake g++ gfortran git \
        pkg-config software-properties-common
    apt-get install -y unrar
    apt-get install -y ffmpeg
    apt-get install -y gnuplot-x11
	
	apt-get install -y vim
	apt-get install -y cmake
	pip install --upgrade cmake
	pip install pandas
	pip install scipy
	
	git clone https://github.com/gpufit/Gpufit.git Gpufit
	mkdir Gpufit-build
	cd Gpufit-build
	cmake -DCMAKE_BUILD_TYPE=RELEASE ../Gpufit
	make
    
	# Clean up
    apt-get -y autoremove
    rm -rvf /var/lib/apt/lists/*