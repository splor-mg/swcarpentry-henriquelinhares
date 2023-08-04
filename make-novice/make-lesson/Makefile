LANGUAGE=python
COUNT_SRC=countwords.py
ZIPF_SRC=testzipf.py
TXT_FILES=$(wildcard books/*.txt)
DAT_FILES=$(patsubst books/%.txt, %.dat, $(TXT_FILES))


## variables : Print variables.
.PHONY : variables
variables:
	@echo TXT_FILES: $(TXT_FILES)
	@echo DAT_FILES: $(DAT_FILES)

# Results
## Results.txt : Generate Zipf summary table.

# results.txt : abyss.dat isles.dat last.dat
# 	python testzipf.py abyss.dat isles.dat last.dat > results.txt

#results.txt : abyss.dat isles.dat last.dat
#	python testzipf.py abyss.dat isles.dat last.dat > $@

#results.txt : testzipf.py abyss.dat isles.dat last.dat
#	python  abyss.dat isles.dat last.dat > $@

#results.txt : $(ZIPF_SRC) abyss.dat isles.dat last.dat
#	python $(ZIPF_SRC) $^ > $@

#results.txt : $(ZIPF_SRC) $(DAT_FILES)
#	python  $^ > $@

results.txt : $(ZIPF_SRC) $(DAT_FILES)
	$(LANGUAGE)  $^ > $@

#Count words.

.PHONY : dats
dats : $(DAT_FILES)

## dats : Count words in text files.

%.dat : books/%.txt
	python $(COUNT_SRC) $< $@

#%.dat : books/%.txt
#	python countwords.py $< $@

#isles.dat : books/isles.txt #target and dependency 
#	python countwords.py books/isles.txt  isles.dat #action, dependency, target

#isles.dat : books/isles.txt #target and dependency 
#	python countwords.py $< $@  #action, dependency, target

#abyss.dat : books/abyss.txt
#	python countwords.py books/abyss.txt abyss.dat

#abyss.dat : books/abyss.txt
#	python countwords.py $< $@

#last.dat : books/last.txt
#	python countwords.py books/last.txt last.dat

## clean :  Remove auto-generated files.
.PHONY : clean
clean :
	rm -f *.dat
	rm -f results.txt

#help
. PHONY : help
help : Makefile
	@sed -n 's/^##//p' $<