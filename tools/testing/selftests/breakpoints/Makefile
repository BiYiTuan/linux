# Taken from perf makefile
uname_M := $(shell uname -m 2>/dev/null || echo not)
ARCH ?= $(shell echo $(uname_M) | sed -e s/i.86/x86/ -e s/x86_64/x86/)

ifeq ($(ARCH),x86)
TEST_PROGS := breakpoint_test
endif
ifeq ($(ARCH),aarch64)
TEST_PROGS := breakpoint_test_arm64
endif

TEST_PROGS += step_after_suspend_test

all: $(TEST_PROGS)

include ../lib.mk

clean:
	rm -fr breakpoint_test breakpoint_test_arm64 step_after_suspend_test
