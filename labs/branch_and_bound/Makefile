MAIN = branch_and_bound
LAB = $(MAIN)_lab
KEY = $(LAB)_key
DEMO = $(MAIN)_demo
DATA = data/*
LAB_IMAGES = images-lab/*
DEMO_IMAGES = images-demo/*

all: lab demo bin-packing

lab: $(KEY).ipynb $(DATA) $(LAB_IMAGES)
	python3 ../distribute.py --key $(KEY).ipynb
	zip -r $(LAB).zip $(LAB).ipynb $(DATA) $(LAB_IMAGES)

jhub-labs: lab ../../../jhub-labs
	rm -rf ../../../jhub-labs/$(MAIN)
	mkdir ../../../jhub-labs/$(MAIN)
	unzip $(LAB).zip -d ../../../jhub-labs/$(MAIN)

demo: $(DEMO).ipynb $(DEMO_IMAGES)
	zip -r $(DEMO).zip $(DEMO).ipynb $(DEMO_IMAGES)

bin-packing: bin_packing_demo.ipynb data-bin_packing
	zip -r bin_packing_demo.zip bin_packing_demo.ipynb data-bin_packing

clean:
	rm -rf {*.zip,$(LAB).ipynb}

.PHONY: clean all

