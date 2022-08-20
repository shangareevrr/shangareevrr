Ответы на тестовые задачи:
1 задача:

def isEven(value):return value&1==0

По сравнению с приведенным примером - используется побитовое сравнение числа на четность. В плане процессорного времени и занимаемой памяти - будет быстрее и легче по сравнению с делением на два.


2 задача:

1 метод
a=[1,2,3,4,5,6,7]
a.append(int(input()))
a.pop(0)
print(a)
использование методов языка

2 метод
a=[1,2,3,4,5,6,7]
a = a[1:]
a.append(int(input()))
print(a)
жесткое истользование индексов без методов

3 задача:

использование алгоритма быстрой сортитровки

def partition(nums, low, high):
    # Выбираем средний элемент в качестве опорного
    # Также возможен выбор первого, последнего
    # или произвольного элементов в качестве опорного
    pivot = nums[(low + high) // 2]
    i = low - 1
    j = high + 1
    while True:
        i += 1
        while nums[i] < pivot:
            i += 1

        j -= 1
        while nums[j] > pivot:
            j -= 1

        if i >= j:
            return j

        # Если элемент с индексом i (слева от опорного) больше, чем
        # элемент с индексом j (справа от опорного), меняем их местами
        nums[i], nums[j] = nums[j], nums[i]

def quick_sort(nums):
    # Создадим вспомогательную функцию, которая вызывается рекурсивно
    def _quick_sort(items, low, high):
        if low < high:
            # This is the index after the pivot, where our lists are split
            split_index = partition(items, low, high)
            _quick_sort(items, low, split_index)
            _quick_sort(items, split_index + 1, high)

    _quick_sort(nums, 0, len(nums) - 1)

# Проверяем, что оно работает
random_list_of_nums = input().split()
for i in range(len(random_list_of_nums)):
    random_list_of_nums[i] = int(random_list_of_nums[i])
quick_sort(random_list_of_nums)
print(random_list_of_nums)
