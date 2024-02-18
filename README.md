main_lst = []
good_lst = ['помидоры','огурцы','бананчики','апельсины','соль']
cost_lst = [5,3,99,2,9]
end_lst = []
cost = 0

def check():
    global cost
    while True:
        ans = input('Введите покупку и кол-во через пробел ')
        ans = ans.split()
        if len(ans) == 2 and ans[1].isdigit() == True:
                ans[0] = ans[0].lower()
                if ans[0] in good_lst:
                    if int(ans[1]) < 11:   
                        print('Покупка добавлена в список')
                        i = cost_lst[good_lst.index(ans[0])]
                        i = i * int(ans[1])
                        cost += i
                        ans.append(i)
                        main_lst.append(ans)
                        end_lst.append(ans)
                        print(ans)
                        break
                    else:
                         print('Столько не унести')
                         continue
                else:
                    print('Этого продукта в магазине нет')



n = int(input('Кол-во покупок '))

def show_end_lst():
    print('товар   кол-во   стоимость')
    for i in range(n):
        a = ''
        for j in range(3):
            a += f'{end_lst[i][j]}     '
        print(a)
        

for i in range(n):
    check()

print(main_lst)
print('Список продуктов заполнен')
show_end_lst()
print(f'Сумма покупок {cost}')
