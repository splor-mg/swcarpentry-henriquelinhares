# Results
# results.txt : abyss.dat isles.dat last.dat
# 	python testzipf.py abyss.dat isles.dat last.dat > results.txt

#results.txt : abyss.dat isles.dat last.dat
#	python testzipf.py abyss.dat isles.dat last.dat > $@

results.txt : abyss.dat isles.dat last.dat
	python testzipf.py $^ > $@


# Count words.
.PHONY : dats
dats : isles.dat abyss.dat last.dat

#isles.dat : books/isles.txt #target and dependency 
#	python countwords.py books/isles.txt  isles.dat #action, dependency, target

isles.dat : books/isles.txt #target and dependency 
	python countwords.py $< $@  #action, dependency, target

#abyss.dat : books/abyss.txt
#	python countwords.py books/abyss.txt abyss.dat

abyss.dat : books/abyss.txt
	python countwords.py $< $@

last.dat : books/last.txt
	python countwords.py books/last.txt last.dat


.PHONY : clean
clean :
	rm -f *.dat
	rm -f results.txt