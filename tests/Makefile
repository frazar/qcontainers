.PHONY: test build
.DEFAULT_GOAL = test

build:
	make -C ..

	gfortran -c ../qcontainers_f/qlibc_util.F90
	gfortran -c ../qcontainers_f/qtreetbl.F90
	gfortran -c ../qcontainers_f/qhashtbl.F90
	gfortran -c ../qcontainers_f/qvector.F90
	gfortran -c ../qcontainers_f/qlist.F90
	gfortran -c ../qcontainers_f/qset.F90

	gfortran -c assert_test.f90
	gfortran -c test_treetbl.f90
	gfortran -c test_hashtbl.F90
	gfortran -c test_vector.f90
	gfortran -c test_list.f90
	gfortran -c test_set.f90

	rm -f test.o
	gfortran -o test.o test_qcontainers.f90 *.o ../lib/libqcontainers.a

test: build
	./test.o

clean:
	make -C .. clean

	rm -f test.o *.o *.mod
