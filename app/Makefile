CC =            nvcc

# CFLAGS +=       -Wall -Wextra -W -g -g03 -pedantic
NAME    =       samaritain

SRC     =       src/main.cpp

OBJ     =       $(SRC:%.c=%.o)  $(SRCS:.c=.o)

RM      =       rm -f

LDFLAGS	=				  -I/usr/local/cuda/include lib/libdarknet.a -lpthread -lcudnn -lcuda  -lcublas -lcurand -lopencv_core -lopencv_highgui -lm
# LDFLAGS	=				  -I/usr/local/cuda/include  -lpthread -lcudnn -lcuda  -lcublas -lcurand -lopencv_core -lopencv_highgui -lm

$(NAME):        $(OBJ)
								$(CC) -o $(NAME) $(OBJ) $(LDFLAGS)

all:            $(NAME)

clean:
								$(RM) $(OBJ) $(NAME)

fclean:         clean
								$(RM) $(NAME)

run:            $(NAME)
								./${NAME}

re:             fclean all
