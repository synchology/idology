require 'bundler'
Bundler::GemHelper.install_tasks
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "idology"
    gem.summary = %Q{Ruby interface to the IDology API}
    gem.description = %Q{Ruby interface to the IDology API. Verify people's identities easily!}
    gem.email = "info@collectiveidea.com"
    gem.homepage = "http://github.com/collectiveidea/idology"
    gem.authors = ['Phil Ripperger', 'Daniel Morrison']
    gem.add_development_dependency "rspec"
    gem.add_development_dependency 'fakeweb', '1.2.8'
    gem.add_dependency 'happymapper', '0.3.0'
    gem.add_dependency 'httparty', '0.5.2'
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: sudo gem install jeweler"
end

require 'spec/rake/spectask'
Spec::Rake::SpecTask.new(:spec) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.spec_files = FileList['spec/**/*_spec.rb']
end

Spec::Rake::SpecTask.new(:rcov) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end


task :default => :spec

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  if File.exist?('VERSION')
    version = File.read('VERSION')
  else
    version = ""
  end

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "idology #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
