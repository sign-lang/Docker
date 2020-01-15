DOCKERFILES := $(filter-out Dockerfiles,$(shell find Dockerfiles))


# $(1) The path to the dockerfile
# $(2) The name of the dockerfile
define DockerTemplate =
all: $(2)

.PHONY: $(2)
$(2):
	@echo Building $(2)...
	@if [ ! -z "$$(DEBUG)" ]; then \
		docker build -f $(1)$(2) -t signlang/build:$(2) ../..; \
	else \
		docker build -f $(1)$(2) -t signlang/build:$(2) ../.. &>/dev/null; \
	fi
	@if [ ! -z "$$(PUSH)" ]; then \
		docker push signlang/build:$(2); \
	fi
endef


.PHONY: none
none:
	@echo Please specify a dockerfile

.PHONY: all
all:
	@


$(foreach _file, $(DOCKERFILES), \
	$(eval $(call DockerTemplate,$(dir $(_file)),$(notdir $(_file)))))
