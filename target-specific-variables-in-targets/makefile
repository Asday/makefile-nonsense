.PHONY = all clean

sources = $(wildcard src/*)

bases = c d

all: $(foreach base,$(bases),all-$(base))

define template =
all-$1: base = $1
all-$1: $(foreach source,$(sources),$$(base)/$(basename $(source:src/%=%)))

.PHONY += all-$1

$1/%: src/%
	echo "$$@" # target
	echo $$(base) # base
	mkdir -p "$$(@D)"

	cp $$< $$@
endef

$(foreach base,$(bases),$(eval $(call template,$(base))))

clean:
	rm -r $(bases)
