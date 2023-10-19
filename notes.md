# build kvm
make -C . M=arch/x86/kvm

# install kvm globally
sudo make -C . M=arch/x86/kvm modules_install

# remove now-outdated kvm module(s) assuming this is done on intel kvm (vmx)
sudo modprobe --remove kvm_intel kvm

# reinsert
sudo modprobe kvm
sudo modprobe kvm_intel

