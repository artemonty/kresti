import sys
sys.setrecursionlimit(27000)
field = [["_", "_", "_"], ["_", "_", "_"], ["_", "_", "_"]]
print(" ".join(field[0]))
print(" ".join(field[1]))
print(" ".join(field[2]))

first_player_metka = None
second_player_metka = None
status_vvoda = False
already_box = []

while not(status_vvoda):
    first_player = input("Введите '1', чтобы играть крестиком. Чтобы ходить ноликом, введите '0': ")
    if str(first_player) == "1":
        first_player_metka = "X"
        second_player_metka = "O"
        status_vvoda = True
    elif str(first_player) == "0":
        first_player_metka = "O"
        second_player_metka = "X"
        status_vvoda = True

    else:
        print("Неправильный ввод.")
        status_vvoda = False

current_chisla = [11, 12, 13, 21, 22, 23, 31, 32, 33]
def move1():
    global already_box
    move = input("Первый игрок, введите номер столбика, а затем номер строки без пробела!: ")
    if move.isdigit() == True:
        if int(move) in current_chisla:
            if int(move) not in already_box:
                nmbr_stlb = int(str(move)[0])-1
                nmbr_str = int(move) % 10 - 1
                field[nmbr_str][nmbr_stlb] = first_player_metka
                print(" ".join(field[0]))
                print(" ".join(field[1]))
                print(" ".join(field[2]))
                already_box += [int(move)]
            else:
                print("Данная ячейка занята.")
                move1()
    else:
        print("Ошибка. Такой ячейки нет!")
        move1()
def move2():
    global already_box
    move = input("Второй игрок, введите номер столбика, а затем номер строки без пробела!: ")
    if move.isdigit() == True:
        if int(move) in current_chisla:
            if int(move) not in already_box:
                nmbr_stlb2 = int(str(move)[0]) - 1
                nmbr_str2 = int(move) % 10 - 1
                field[nmbr_str2][nmbr_stlb2] = second_player_metka
                print(" ".join(field[0]))
                print(" ".join(field[1]))
                print(" ".join(field[2]))
                already_box += [int(move)]
            else:
                print("Данная ячейка занята.")
                move2()
    else:
        print("Ошибка. Такой ячейки нет!")
        move2()
def check_win():
    if (field[0][0] == field[0][1] == field[0][2] == "X") or (field[0][0] == field[1][0] == field[2][0] == "X") or (field[0][0] == field[1][1] == field[2][2] == "X") or (field[2][1] == field[1][1] == field[2][0] == "X") or (field[1][0] == field[1][1] == field[1][2] == "X") or (field[2][0] == field[2][1] == field[2][2] == "X"):
        print("Игра закончена, победили крестики!")
        return True
    if (field[0][0] == field[0][1] == field[0][2] == "O") or (field[0][0] == field[1][0] == field[2][0] == "O") or (field[0][0] == field[1][1] == field[2][2] == "O") or (field[2][1] == field[1][1] == field[2][0] == "O") or (field[1][0] == field[1][1] == field[1][2] == "O") or (field[2][0] == field[2][1] == field[2][2] == "O"):
        print("Игра закончена, победили нолики!")
        return True

while len(already_box) < 10:
    move1()
    if check_win():
        break
    elif len(already_box) == 9:
        print("Ничья.")
        break
    else:
        move2()



check_win()
