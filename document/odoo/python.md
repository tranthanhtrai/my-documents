# This's document about python basic
## 1. Map()

Hàm map() tích hợp sẵn trong Python có tác dụng duyệt tất cả các phần tử của một iterable (list, tuple, dictionary...) qua một hàm cho trước và trả về một list kết quả sau khi thực thi.

***map(function, iterable, ...)***
- function: Hàm thực thi cho từng phần tử trong iterable.
- iterable: một list, tuple, dictionary... muốn duyệt.
```
def binhphuong(n):
return n*n

number = (25, 100, 225, 400)
ketqua = map(binhphuong, number)
print(list(ketqua))
kq = [625, 10000, 50625, 160000]
```

## 2. Zip()
Looping through two list sumiltaneously
**for list1, list2 in zip(list1, list2)**

```
wizards = ['QuangHai','VanToan', 'HoangDuc']
clubs = ['HAGL','HANOI','VIETTEL']

for wizards, clubs in zip(wizards,clubs):
    print(f'{wizards} : {clubs}')


QuangHai : HAGL
VanToan : HANOI
HoangDuc : VIETTEL
```

## 2.Flush()
