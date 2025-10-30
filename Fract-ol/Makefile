
CC			= gcc
CFLAGS		= -Wall -Wextra -Werror -Iincludes -Iincludes/lib42 -Iincludes/minilibx
NAME		= fractol

SRC_DIR		= src
LIBFT_DIR	= includes/lib42
MLX_DIR		= includes/minilibx

SRCS = \
	$(SRC_DIR)/main.c \
	$(SRC_DIR)/mandelbrot.c \
	$(SRC_DIR)/julia.c \
	$(SRC_DIR)/burning_ship.c \
	$(SRC_DIR)/draw.c \
	$(SRC_DIR)/mouse_and_key.c \
	$(SRC_DIR)/init.c \
	$(SRC_DIR)/utils.c

OBJS = \
	$(SRC_DIR)/main.o \
	$(SRC_DIR)/mandelbrot.o \
	$(SRC_DIR)/julia.o \
	$(SRC_DIR)/burning_ship.o \
	$(SRC_DIR)/draw.o \
	$(SRC_DIR)/mouse_and_key.o \
	$(SRC_DIR)/init.o \
	$(SRC_DIR)/utils.o

LIBFT = $(LIBFT_DIR)/libft.a
MLX   = $(MLX_DIR)/libmlx.a
MLXFLAGS = -L$(MLX_DIR) -lmlx -lX11 -lXext -lm

all: $(NAME)

$(NAME): $(LIBFT) $(MLX) $(OBJS)
	$(CC) $(CFLAGS) $(OBJS) $(LIBFT) $(MLXFLAGS) -o $(NAME)

$(SRC_DIR)/%.o: $(SRC_DIR)/%.c
	$(CC) $(CFLAGS) -c $< -o $@

$(LIBFT):
	$(MAKE) -C $(LIBFT_DIR)

$(MLX):
	$(MAKE) -C $(MLX_DIR)

clean:
	$(MAKE) clean -C $(LIBFT_DIR)
	$(MAKE) clean -C $(MLX_DIR)
	rm -f $(OBJS)

fclean: clean
	$(MAKE) fclean -C $(LIBFT_DIR)
	rm -f $(NAME)

re: fclean all

.PHONY: all clean fclean re