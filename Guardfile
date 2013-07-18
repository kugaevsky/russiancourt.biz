# A sample Guardfile
# More info at https://github.com/guard/guard#readme

# -= Guard notifications =-

# notification :growl
# notification :libnotify, :timeout => 5, :transient => true, :append => false, :urgency => :critical
# notification :notifu, :time => 5, :nosound => true, :xp => true

# -= Guarded paths =-

PATHS = { :in => 'source', :out => 'html' }

# -= Guard preprocessors =-

group :templates do
  guard 'slim', :input_root => PATHS[:in], :output_root => PATHS[:out] do
    watch(%r'^.+\.slim$')
  end
end

group :javascripts do
  guard 'coffeescript', :input => "#{PATHS[:in]}/javascripts", :output => "#{PATHS[:out]}/javascripts"
end

group :stylesheets do
  guard 'sass', :input => "#{PATHS[:in]}/stylesheets", :output => "#{PATHS[:out]}/stylesheets"
end

# -= Livereload =-
group :reload do
  guard 'livereload' do
    watch(%r{#{PATHS[:out]}/.+\.html$})
    watch(%r{#{PATHS[:out]}/stylesheets/.+\.css$})
    watch(%r{#{PATHS[:out]}/javascripts/.+\.js$})
  end
end
