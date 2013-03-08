desc "Install snap-copy-paste"
task :install do
  system "chmod a+x snap-copy-paste"
  system "chmod a+x imagesnap"
  puts "installing to /usr/bin"
  system "sudo cp snap-copy-paste /usr/bin/"
  system "sudo cp imagesnap /usr/bin/"

  config = File.expand_path("~/.snaprc")
  if File.exists?(config)
    puts "config file already exists, skipping"
  else
    puts "creating config file at #{ config }, make sure to change the default values"
    File.open(config, 'w') do |f|
      f.puts %[# this is YAML]
      f.puts %[REMOTE_IMAGE_HOST: "mywebhost"]
      f.puts %[REMOTE_IMAGE_PATH: "~/example.com/images/snaps/"]
      f.puts %[REMOTE_IMAGE_URI:  "http://example.com/images/snaps/"]
    end
  end
end
