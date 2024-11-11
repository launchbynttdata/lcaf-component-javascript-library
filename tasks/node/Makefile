SOURCE_FOLDER="source"
DIST_FOLDER="dist/packages"

.PHONY: install
install::
	@echo "Running install target"
	@npm --prefix $(SOURCE_FOLDER) config set legacy-peer-deps true 
	@npm --prefix $(SOURCE_FOLDER) install

.PHONY: test
test:: install
	@echo "Running test target"
	@npm --prefix $(SOURCE_FOLDER) run test 

.PHONY: build
build:: install
	@echo "Running build target"
	@npm --prefix $(SOURCE_FOLDER) run build 

.PHONY: publish
publish::
	@echo "Running publish target"
	@for packageDir in $(DIST_FOLDER)/*; do \
  		if [ -f "$$packageDir/package.json" ]; then \
			npm publish "$$packageDir"; \
  		fi; \
	done

.PHONY: version
version::
	@echo "Running version target"
	@npm --prefix $(SOURCE_FOLDER) version $(TAG)

.PHONY: login
login::
	@echo "Running login target"
	@echo "//$(PACKAGE_REGISTRY)/:_authToken=$(TOKEN)" > .npmrc && echo "@$(PACKAGE_SCOPE):registry=https://$(PACKAGE_REGISTRY)/$(PACKAGE_PUBLISHER)" >> .npmrc
