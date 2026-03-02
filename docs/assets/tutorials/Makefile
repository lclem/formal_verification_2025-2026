BUILD := build
SOURCES := $(filter-out common.tex,$(wildcard *.tex))
$(info SOURCES:$(SOURCES))

TUTORIALS := $(patsubst %.tex,$(BUILD)/%.pdf,$(SOURCES))

all: $(TUTORIALS)

$(BUILD):
	mkdir -p $(BUILD)

$(BUILD)/%.pdf: %.tex common.tex $(BUILD)
	@echo + Making $@ from $<
	pdflatex -output-directory=$(BUILD) "$(patsubst $(BUILD)/%.pdf,%.tex,$@)"

$(TUTORIALS) : $(BUILD)/%.pdf : %.tex

clean:
	rm -fr $(BUILD)