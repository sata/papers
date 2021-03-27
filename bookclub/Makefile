PLANTUML := plantuml
DEFAULT_GOAL: gen-diagrams

.PHONY: plantuml
plantuml:
	@if [ ! $$(command -v plantuml) ]; then \
			sudo apt-get update && sudo apt-get install -y plantuml; \
	fi

.PHONY: gen-diagram
gen-diagrams: plantuml
	@${PLANTUML} -tpng howto_measure_anything.md
