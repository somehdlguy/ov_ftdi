PYTHONPATH := ../migen:../mibuild
export PYTHONPATH
OVCTL := ../../host/ovctl
BUILD := build
BITFILE := $(BUILD)/ov3.bit

all: $(BITFILE)

$(BITFILE): *.py
	python3 top.py --build-dir $(BUILD) --build-name ov3

clean:
	rm -rf $(BUILD)/*

run: $(OVCTL) $(BITFILE)
	$(OVCTL) -C -b $(BITFILE)

sim_sdram:
	python3 sdram.py