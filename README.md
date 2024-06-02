In order for any of this to work, install Squib! https://squib.readthedocs.io/en/v0.18.0/install.html or in summary:

1) install Ruby with devkit
2) execute `gem install squib` from an admin powershell prompt (takes forever)
3) execute `gem install game_icons` from an admin powershell prompt
4) execute `bundle update` from an admin powershell prompt (in case the libraries in the gemfile.lock file are old)
5) execute `bundle install` from an admin powershell prompt (installs all of the stuff in the Genfile.lock file)

guide doesn't spell this out, but after installing ruby (which does take forever) you should have a ruby command-line option in your start applications. that's where all the commands function

And then when you want to make the cards: ruby C:<wherever you cloned this repo>\generate-cards.rb

# Squib Workflow looks like this
I suggest starting with the Character Cards directory, which has a most thoroughly documented .rb and .yml files. 
it also contains a GenerateCards.ps1 script for processing multiple .csv files, making asset generation even easier

- add/edit cards into the .csv for the directory you're working in (character cards, equipment cards, etc.)
- edit layout.yml to define new elements/edit where elements  as needed
- edit the .rb file to 1) pull in the data from the csv, 2) define what elements exist (background, rectangles, etc.), 3) where what data goes (ie: `text str: data['topAbilityName'], layout: 'title1'`)
- call `ruby` on the rb file
- review card pngs/pdfs saved to the output folder (note the save_sheet options which 'sprue's the contents into a printable format
