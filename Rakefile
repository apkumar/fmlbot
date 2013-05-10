task :fmlscrape, [:start, :end] do |t, args|
	args.with_defaults(:start => 1,:end => 10)
	require 'open-uri'
	fmls = []
	(args.start..args.end).each do |p|
		url = "http://www.fmylife.com/?page=#{p}"
		source = open(url){|f|f.read}
		fmls = fmls + source.scan(/class="fmllink">(.*?)<\/a>/).flatten
	end
	fmls.each do |sentence|
		sentence.strip!
	end
	fmls.delete("FML")
	File.open('fmls.txt','w') do |outs|
		outs.puts fmls
	end
end

task :mligscrape, [:start, :end] do |t, args|
	args.with_defaults(:start => 1, :end => 10)
	require 'open-uri'
	mligs = []
	(args.start..args.end).each do |p|
		url = "http://mylifeisg.com/#{p}"
		source = open(url){|f|f.read}
		mligs = mligs + source.scan(/class=\"sc\">\n(.*)/).flatten
	end
	mligs.each do |sentence|
		sentence.strip!
	end
	File.open('mligs.txt','w') do |outs|
		outs.puts mligs
	end
end

task :mliascrape, [:start, :end] do |t, args|
	args.with_defaults(:start => 1, :end => 10)
	require 'open-uri'
	mlias = []
	(args.start..args.end).each do |p|
		url = "http://mylifeisaverage.com/#{p}"
		source = open(url){|f|f.read}
		mlias = mlias + source.scan(/class=\"sc\">\n(.*)/).flatten
	end
	mlias.each do |sentence|
		sentence.strip!
	end
	File.open('mlias.txt','w') do |outs|
		outs.puts mlias
	end
end