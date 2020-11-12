NAME = uls

FLAGS = -std=c11 -Wall -Wextra -Werror -Wpedantic
LMXD = libmx

all: create_obj PATH

create_obj:
	mkdir obj

PATH:
	make -sC libmx
	clang $(FLAGS) -Iinc -Ilibmx/inc -c src/*.c
	mv *.o obj/
	clang -o $(NAME) obj/*.o -L$(LMXD) -lmx

clean:
	make clean -sC libmx
	rm -rf obj

uninstall:
	make uninstall -sC libmx
	rm -rf obj
	rm -rf $(NAME)

reinstall:
	make reinstall -sC libmx
	make uninstall
	make
