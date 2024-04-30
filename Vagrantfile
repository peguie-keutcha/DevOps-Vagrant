Vagrant.configure("2") do |config|
  config.vm.define "SRV-AN" do |srv_an|
    srv_an.vm.box = "almalinux/8"
    srv_an.vm.network "public_network", bridge: ["Intel(R) Wi-Fi 6 AX201 160MHz"]
    srv_an.vm.provider "virtualbox" do |v|
      v.name = "SRV-AN"
      v.memory = 1024
      v.cpus = 1
    end
  end

  config.vm.define "CLIx" do |clx|
    clx.vm.box = "almalinux/8"
    clx.vm.network "public_network", bridge: ["Intel(R) Wi-Fi 6 AX201 160MHz"]
    clx.vm.provider "virtualbox" do |v|
      v.name = "CLIx"
      v.memory = 1024
      v.cpus = 2
    end
  end

  config.vm.define "CLIy" do |cly|
    cly.vm.box = "almalinux/8"
    cly.vm.network "public_network", bridge: ["Intel(R) Wi-Fi 6 AX201 160MHz"]
    cly.vm.provider "virtualbox" do |v|
      v.name = "CLIy"
      v.memory = 1024
      v.cpus = 1
    end
  end  
end