.PHONY : dats
dats : isles.dat abyss.dat last.dat

# Count words.
isles.dat : books/isles.txt #target and dependency 
	python countwords.py books/isles.txt isles.dat #action, dependency, target

abyss.dat : books/abyss.txt
	python countwords.py books/abyss.txt abyss.dat

last.dat : books/last.txt
	python countwords.py books/last.txt last.dat

# Results
results.txt : abyss.dat isles.dat last.dat
	python testzipf.py abyss.dat isles.dat last.dat > results.txt

.PHONY : clean
clean :
	rm -f *.dat