require 'puppetlabs_spec_helper/rake_tasks'
require 'puppet-lint/tasks/puppet-lint'

#PuppetLint.configuration.fail_on_warnings
#PuppetLint.configuration.send('relative')
#PuppetLint.configuration.send('disable_80chars')
#PuppetLint.configuration.send('disable_class_inherits_from_params_class')
#PuppetLint.configuration.send('disable_documentation')
#PuppetLint.configuration.send('disable_single_quote_string_with_variables')
#PuppetLint.configuration.ignore_paths = ["spec/**/*.pp", "pkg/**/*.pp"]


exclude_paths = ["spec/**/*", "pkg/**/*", "vendor/**/*", "bundle/**/*" ]

Rake::Task[:lint].clear
PuppetLint::RakeTask.new :lint do |config|
  config.disable_checks = %w(80chars class_parameter_defaults class_inherits_from_params_class autoloader_layout documentation)
  config.log_format = "%{path}:%{linenumber}:%{check}:%{KIND}:%{message}"
  config.fail_on_warnings = true
  config.ignore_paths = exclude_paths
end

PuppetSyntax.exclude_paths = exclude_paths
