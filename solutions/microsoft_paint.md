> You are Given an image represented as a matrix. Each value in the matrix represents the color of an individual pixel. Given a new color represented as an integer and a starting row and column, transform every adjacent pixel to the starting pixel that has the same color to the new color.
>
> Note: This is effectively implementing a "bucket fill" in a software like Microsoft paint.
>
> Ex: Given the following `image`, `row`, `column`, and `color`…
> - image = [
>     [0,1,1],
>     [0,1,0],
>     [1,1,1]
>   ], row = 1, column = 1, color = 3 modify image to be as follows...
>   image = [
>     [0, 3, 3],
>     [0, 3, 0],
>     [3, 3, 3],
>   ].

Solution:
```
def bucket_fill(image, row, column, old_color, new_color):
    if row < 0 or row > len(image)-1 or \
        column < 0 or column > len(image[0])-1 or \
        image[row][column] != old_color or \
        image[row][column] == new_color:
        return

    image[row][column] = new_color

    bucket_fill(image, row-1, column, old_color, new_color)
    bucket_fill(image, row+1, column, old_color, new_color)
    bucket_fill(image, row, column-1, old_color, new_color)
    bucket_fill(image, row, column+1, old_color, new_color)
    bucket_fill(image, row-1, column-1, old_color, new_color)
    bucket_fill(image, row-1, column+1, old_color, new_color)
    bucket_fill(image, row+1, column-1, old_color, new_color)
    bucket_fill(image, row+1, column+1, old_color, new_color)


def change_color(image, row, column, new_color):
    if image[row][column] == new_color:
        return
    old_color = image[row][column]
    bucket_fill(image, row, column, old_color, new_color)
```

Test results:
```
In [6]: image = [
   ...:   [0,1,1],
   ...:   [0,1,0],
   ...:   [1,1,1]
   ...: ]; row = 1; column = 1; color = 3

In [7]: change_color(image, row, column, color)

In [8]: image
Out[8]: [[0, 3, 3], [0, 3, 0], [3, 3, 3]]
```
