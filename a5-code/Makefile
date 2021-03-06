# All required AND optional tests

COMPFLAGS = -g -annot
OCC = ocamlc $(COMPFLAGS)
LIBS = 


PROGRAMS = \
	demo_parse \
	demo_eval \
	calculon \

MODULES = \
	calclex.cmo \
	calcparse.cmo \
	calceval.cmo \

TEST_PROGRAMS = \


all : $(MODULES) $(PROGRAMS) 

setup:
	chmod u+x calculon_required_solution
	chmod u+x calculon_optional_solution

calclex.cmo : calclex.ml
	$(OCC) -c $<

calcparse.cmo : calcparse.ml calclex.cmo
	$(OCC) -c $<

demo_parse : calclex.cmo calcparse.cmo demo_parse.ml
	$(OCC) -o $@ $^

calceval.cmo : calceval.ml calcparse.cmo calclex.cmo
	$(OCC) -c $<

demo_eval : calclex.cmo calcparse.cmo calceval.cmo demo_eval.ml
	$(OCC) -o $@ $^

calculon : calclex.cmo calcparse.cmo calceval.cmo calculon.ml
	$(OCC) -o $@ $^

clean :
	rm -f *.cmo *.cmi *.mlt *.annot $(PROGRAMS) $(TEST_PROGRAMS) 

########################################
# Testing Targets
test : test-p1 test-p2 test-p3 test-p4 test-p5

clean-tmp : test-data
	rm -f test-data/*.tmp
	rm -f *.tmp

test-data :
	mkdir -p test-data

# PROBLEM 1
test-p1 : calculon clean-tmp
	@chmod u+x test_calculon.sh
	@printf "===TESTS for P1===\n"
	./test_calculon.sh test_p1_data.sh
	@printf "\n"

# PROBLEM 2
test-p2 : calculon clean-tmp
	@chmod u+x test_calculon.sh
	@printf "===TESTS for P2===\n"
	./test_calculon.sh test_p2_data.sh
	@printf "\n"

# PROBLEM 3
test-p3 : calculon clean-tmp
	@chmod u+x test_calculon.sh
	@printf "===TESTS for P3===\n"
	./test_calculon.sh test_p3_data.sh
	@printf "\n"

# PROBLEM 4
test-p4 : calculon clean-tmp
	@chmod u+x test_calculon.sh
	@printf "===TESTS for P4===\n"
	./test_calculon.sh test_p4_data.sh
	@printf "\n"

# PROBLEM 5
test-p5 : calculon clean-tmp
	@chmod u+x test_calculon.sh
	@printf "===TESTS for P5===\n"
	./test_calculon.sh test_p5_data.sh
	@printf "\n"

# Run all optional tests
test-op : test-op1 test-op2 test-op3 test-op4 test-op5

# OPTIONAL PROBLEM 1
test-op1 : calculon clean-tmp
	@chmod u+x test_calculon.sh
	@printf "===TESTS for OP1===\n"
	./test_calculon.sh test_op1_data.sh
	@printf "\n"

# OPTIONAL PROBLEM 2
test-op2 : calculon clean-tmp
	@chmod u+x test_calculon.sh
	@printf "===TESTS for OP2===\n"
	./test_calculon.sh test_op2_data.sh
	@printf "\n"

# OPTIONAL PROBLEM 3
test-op3 : calculon clean-tmp
	@chmod u+x test_calculon.sh
	@printf "===TESTS for OP3===\n"
	./test_calculon.sh test_op3_data.sh
	@printf "\n"

# OPTIONAL PROBLEM 4
test-op4 : calculon clean-tmp
	@chmod u+x test_calculon.sh
	@printf "===TESTS for OP4===\n"
	./test_calculon.sh test_op4_data.sh
	@printf "\n"

# OPTIONAL PROBLEM 5
test-op5 : calculon clean-tmp
	@chmod u+x test_calculon.sh
	@printf "===TESTS for OP5===\n"
	./test_calculon.sh test_op5_data.sh
	@printf "\n"
