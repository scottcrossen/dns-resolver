# Makefile by Scott Leland Crossen
# @Copyright 2017 Scott Leland Crossen

# ==== Definitions ====

BYUNETID = slxn42
VERSION = 1
BINDIR = bin
SOURCEDIR = source
RELDIR = rel
TESTDIR = test
COMP = gcc
BINOBJS = ${BINDIR}/resolver.o
MAIN = ${RELDIR}/main
TEST = ${TESTDIR}/resolver-ref
COMPFLAGS = -g
LINKFLAGS = -lrt
HANDINDIR = /users/faculty/snell/CS324/handin/Fall2017/DNSResolver

# ==== Recipes ====

.PHONY: default
.DEFAULT: default
default: all

.PHONY: all
all: $(MAIN)

.PHONY: clean
clean:
	rm -rf $(BINDIR) $(RELDIR)

.PHONY: handin
handin:
	scp ${SOURCEDIR}/resolver.c ${BYUNETID}@schizo.cs.byu.edu:${HANDINDIR}/${BYUNETID}-${VERSION}-resolver.c

# ==== Targets ====

.PRECIOUS: ${BINDIR}/%.o
${BINDIR}/%.o: ${SOURCEDIR}/%.c
	mkdir -p $(@D)
	$(COMP) -c $< -o $@ $(COMPFLAGS)

.PRECIOUS: ${RELDIR}/%
${RELDIR}/%: ${BINOBJS}
	mkdir -p $(@D)
	$(COMP) $^ -o $@ $(LINKFLAGS)

# ==== Targets ====

.PHONY: test
test: test1 rtest1 test2 rtest2 test3 rtest3 test4 rtest4 test5 rtest5 test6 rtest6

.PHONY: test1
test1: $(MAIN)
	./${MAIN} www.example.com 8.8.8.8
.PHONY: rtest1
rtest1: $(TEST)
	./${TEST} www.example.com 8.8.8.8

.PHONY: test2
test2: $(MAIN)
	./${MAIN} byu.edu 8.8.8.8
.PHONY: rtest2
rtest2: $(TEST)
	./${TEST} byu.edu 8.8.8.8

.PHONY: test3
test3: $(MAIN)
	./${MAIN} www.byu.edu 8.8.8.8
.PHONY: rtest3
rtest3: $(TEST)
	./${TEST} www.byu.edu 8.8.8.8

.PHONY: test4
test4: $(MAIN)
	./${MAIN} i-dont-exist.byu.edu 8.8.8.8
.PHONY: rtest4
rtest4: $(TEST)
	./${TEST} i-dont-exist.byu.edu 8.8.8.8

.PHONY: test5
test5: $(MAIN)
	./${MAIN} www.intel.com 8.8.8.8
.PHONY: rtest5
rtest5: $(TEST)
	./${TEST} www.intel.com 8.8.8.8

.PHONY: test6
test6: $(MAIN)
	./${MAIN} . 8.8.8.8
.PHONY: rtest6
rtest6: $(TEST)
	./${TEST} . 8.8.8.8

.PHONY: test7
test7: $(MAIN)
	./${MAIN} drive.google.com 8.8.8.8
.PHONY: rtest7
rtest7: $(TEST)
	./${TEST} drive.google.com 8.8.8.8

.PHONY: test8
test8: $(MAIN)
	./${MAIN} keep.google.com 8.8.8.8
.PHONY: rtest8
rtest8: $(TEST)
	./${TEST} keep.google.com 8.8.8.8

.PHONY: test9
test9: $(MAIN)
	./${MAIN} education.byu.edu 8.8.8.8
.PHONY: rtest9
rtest9: $(TEST)
	./${TEST} education.byu.edu 8.8.8.8

.PHONY: test10
test10: $(MAIN)
	./${MAIN} pandora.byu.edu 8.8.8.8
.PHONY: rtest10
rtest10: $(TEST)
	./${TEST} pandora.byu.edu 8.8.8.8

.PHONY: test11
test11: $(MAIN)
	./${MAIN} com 8.8.8.8
.PHONY: rtest11
rtest11: $(TEST)
	./${TEST} com 8.8.8.8
