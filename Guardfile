require 'erb'
require 'asciidoctor'
require 'asciidoctor/cli'
require 'tilt/asciidoc'

guard :shell do
    watch (/slides\.adoc$/) { |m| Asciidoctor::Cli::Invoker.new(%W(-T asciidoctor-backends/slim -a data-uri -a linkcss! #{m[0]})).invoke! }
end

guard 'livereload' do
    watch(%r{.+\.(css|js|html?|php|inc|theme)$})
end
