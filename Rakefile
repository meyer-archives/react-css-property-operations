require 'json'

desc 'Upgrade react-dom to the latest version'
task :default do
  system 'yarn upgrade'

  # get version number from react-dom
  reactDomPackageJson = IO.read('node_modules/react-dom/package.json')
  versionNumber = JSON.parse(reactDomPackageJson)['version']

  # update local version number
  File.open('./package.json', File::RDWR|File::CREAT, 0644) do |f|
    begin
      pkg = JSON.parse(f.read)
    rescue
      abort 'Unable to read package.json :('
    end

    pkg['version'] = versionNumber

    # write modified package.json
    f.rewind
    f.puts JSON.pretty_generate(pkg)
    f.flush
    f.truncate(f.pos)
  end

  # rebuild with webpack
  rm './lib/CSSPropertyOperations.js'
  system 'npm run webpack'
end
