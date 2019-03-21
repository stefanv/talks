vector_images := $(wildcard *.svg)
build_dir := build
images := $(addprefix $(build_dir)/,$(vector_images:.svg=.png))

.PHONY: default
default: | $(build_dir) $(images)

$(build_dir):
	mkdir -p $(build_dir)

$(images): $(build_dir)/%.png : %.svg
	-inkscape --export-area-drawing --export-png=$@ --export-dpi=300 $<

clean:
	rm $(build_dir)/*
