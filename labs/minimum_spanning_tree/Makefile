MAIN = minimum_spanning_tree
LAB = $(MAIN)_lab
KEY = $(LAB)_key
DATA = data/*
IMAGES = images/*

all: lab

lab: $(KEY).ipynb $(DATA) $(IMAGES)
	python3 ../distribute.py --key $(KEY).ipynb
	zip -r $(LAB).zip $(LAB).ipynb $(DATA) $(IMAGES)

jhub-labs: lab ../../../jhub-labs
	rm -rf ../../../jhub-labs/$(MAIN)
	mkdir ../../../jhub-labs/$(MAIN)
	unzip $(LAB).zip -d ../../../jhub-labs/$(MAIN)

clean:
	rm -rf {*.zip,$(LAB).ipynb}

.PHONY: clean all

