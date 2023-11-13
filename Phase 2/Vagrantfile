Vagrant.configure("2") do |config|
  # Configuration for the 'web' machine
  config.vm.define "web" do |web|
    web.vm.box = "generic/ubuntu2004"
    web.vm.provider "libvirt" do |libvirt|
      libvirt.driver = "kvm"
      libvirt.machine_type = "q35"
    end
  end

  # Configuration for the 'android' machine
  config.vm.define "android" do |android|
    android.vm.box = "generic/ubuntu2004"
    android.vm.provider "libvirt" do |libvirt|
      libvirt.driver = "kvm"
      libvirt.machine_type = "q35"
    end
  end

  # Configuration for the 'api' machine
  config.vm.define "api" do |api|
    api.vm.box = "generic/ubuntu2004"
    api.vm.provider "libvirt" do |libvirt|
      libvirt.driver = "kvm"
      libvirt.machine_type = "q35"
    end
  end
end
