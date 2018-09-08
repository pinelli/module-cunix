CC					:= gcc

RM					:= rm -rf

LDFLAGS			+= -Llib -lbinary_tree

CFLAGS			+= -Iinclude -g

SRCS				:= $(wildcard src/*.c)

OBJS				:= $(SRCS:.c=.o)

NAME				:= minishell

all:				$(NAME)

$(NAME):		$(OBJS)
						$(CC) $(CFLAGS) -o $(NAME) $(OBJS) $(LDFLAGS)

clean:
						$(RM) $(OBJS)

fclean: 		clean
						$(RM) $(NAME)

re: 				fclean all

test:				re
						@(./$(NAME) < input > output )
						@(diff -q verif output && echo "Test success" || echo "Test Fails")

debug:			re
						valgrind -v --leak-check=full --track-origins=yes ./$(NAME)

run:	re
	./$(NAME)
