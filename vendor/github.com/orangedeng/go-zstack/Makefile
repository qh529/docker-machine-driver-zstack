TARGETS := $(shell ls scripts)

.dapper:
	@echo Downloading dapper
	@curl -sL http://dev-tool.oss-cn-shenzhen.aliyuncs.com/dapper-`uname -s`-`uname -m`/dapper  > .dapper.tmp
	@@chmod +x .dapper.tmp
	@./.dapper.tmp -v
	@mv .dapper.tmp .dapper

$(TARGETS): .dapper
	./.dapper $@

trash: .dapper
	./.dapper -m bind trash

trash-keep: .dapper
	./.dapper -m bind trash -k

deps: trash

.DEFAULT_GOAL := ci

.PHONY: $(TARGETS)
