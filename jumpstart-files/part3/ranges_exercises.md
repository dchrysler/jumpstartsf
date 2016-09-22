# Range Exercises

0. Define a method, `#alphabet_slice(range)`, that accepts a range of integers as an argument. Use the range to slice a string of characters representing the alphabet. Remember, the `String#slice` method can accept a range as an argument!

  ```ruby
    alphabet_slice((0..3))  # ==> "abcd"
    alphabet_slice((0...3)) # ==> "abc"
    alphabet_slice((0..25)) # ==> "abcdefghijklmnopqrstuvwxyz"
  ```
  
  ```ruby
  #PROBLEM ONE
  def alphabet_slice(range)
      alphabet = ["a", "b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "l", "m", "n", "o", "p", "q", "r", "s", "t", "u", "v", "w", "x", "y", "z"]
      alphabet[(range)].join
  end
  
  puts "-------ONE-------"
  puts alphabet_slice((0..3)) == "abcd"
  puts alphabet_slice((0...3)) == "abc"
  puts alphabet_slice((0..25)) == "abcdefghijklmnopqrstuvwxyz"
  ```

0. Define a method, `#alphabet_without(array)`, that accepts an array of letters as an argument. Your method should return an array of all the characters in the alphabet, but exclude the characters in the input array.

  ```ruby
    alphabet_without(["a"])      # ==> b - z in array
    alphabet_without(["a", "z"]) # ==> b - y in array
  ```

  ```ruby
  #PROBLEM TWO
  def alphabet_without(array)
      array2 = []
      ("a".."z").each do |letter|
          unless array.include? letter
          array2 << letter
          end
      end
      array2
  end
  
  puts "-------TWO-------"
  puts alphabet_without(["a"]) == ["b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "l", "m", "n", "o", "p", "q", "r", "s", "t", "u", "v", "w", "x", "y", "z"]
  puts alphabet_without(["a", "z"]) == ["b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "l", "m", "n", "o", "p", "q", "r", "s", "t", "u", "v", "w", "x", "y"]
  ```

0. Define a method, `#evens_below(integer)`, that accepts an integer as an argument. Your method should return an array of all the even numbers (starting at 0) that are less than (but not equal to) the integer argument.

  ```ruby
    evens_below(6)  # ==> [0, 2, 4]
    evens_below(9)  # ==> [0, 2, 4, 6, 8]
  ```
  
  ```ruby
  #THREE
  def evens_below(integer)
      array = []
      n = 0
      while n < integer
          if n % 2 == 0
              array << n
              n += 1
          end
      end
      array
  end
  
  puts "-------THREE-------"
  puts evens_below(6) == [0, 2, 4]
  puts evens_below(9) == [0, 2, 4, 6, 8]
  ```

0. Define a method, `#to_range(array)` that, given an array of integers, constructs a range covering the span of integers in the array argument.

  ```ruby
    to_range([1, 8, 11, 5, 6])  # ==> (1..11)
    to_range([6, 15, 2, 12])    # ==> (2..15)
  ```
  
  ```ruby
  #FOUR
  def to_range(array)
      array.sort!
      range = (array[0]..array[-1])
  end
  
  puts "-------FOUR-------"
  puts to_range([1, 8, 11, 5, 6]) == (1..11)
  puts to_range([6, 15, 2, 12]) == (2..15)
```
