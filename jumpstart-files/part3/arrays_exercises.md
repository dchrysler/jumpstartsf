# Array Exercises

0. Write a method, `#first_n_evens(n)` that returns an array of the first n even numbers, starting from 0.

  ```ruby
    first_n_evens(1) # ==> [0]
    first_n_evens(3) # ==> [0, 2, 4]
  ```
  
  ```ruby
  def first_n_evens(n)
    results = []
    n.times do |num|
        results << num * 2
  	end
    results
	end
    
	"-------ONE-------"
	puts first_n_evens(1) == [0]
	puts first_n_evens(3) == [0, 2, 4]
	```
  

0. Write a method, `#reverse(array)` that reverses an array in-place; don't create any new arrays!

  ```ruby
    reverse([1])          # ==> [1]
    reverse([1, 2])       # ==> [2, 1]
    reverse([4, 5, 6, 7]) # ==> [7, 6, 5, 4]
  ```
  
  ```ruby
  def reverse(array)
    new_array = array.reverse
	end

	puts "-------TWO-------"
	puts reverse([1]) == [1]
	puts reverse([1,2]) == [2,1]
	puts reverse([4,5,6,7]) == [7,6,5,4]
```

0. Write a method, `#rotate(array, shift)` that, given an array and integer, shift, rotates the array in-place by the shift amount.
  * Hint: some combination of `#shift`/`#push` or `#unshift`/`#pop` should come in handy here.

  ```ruby
    rotate([1, 2, 3, 4], 1)  # ==> [4, 1, 2, 3]
    rotate([1, 2], 2)        # ==> [1, 2]
    rotate([4, 5, 6, 7], 3)  # ==> [5, 6, 7, 4]
  ```
  
  ```ruby
  def rotate(array, shift)
    shift.times do |move|
        num = array.pop
        array.unshift(num)
    end
    array
	end

	puts "-------THREE-------"
	puts rotate([1, 2, 3, 4], 1) == [4, 1, 2, 3]
	puts rotate([1, 2], 2) == [1, 2]
	puts rotate([4, 5, 6, 7], 3) == [5, 6, 7, 4]
	```

0. Write a method, `#all_uniqs(array1, array2)` that, given two arrays, produces a new array of only elements unique to `array1` and elements unique to `array2`. Don't worry about the order of the elements in the output array.

  ```ruby
    all_uniqs([1, 2, 3], [1, 2, 4]) # ==> [3, 4]
    all_uniqs([1, 2, 7], [1, 3, 8]) # ==> [2, 7, 3, 8]
  ```

	```ruby
	#PROBLEM FOUR
	def all_uniqs(array1, array2)
	    array3 = []
	    array1.each do |element|
	        unless array2.include? element
	        array3 << element
	        end
	    end
	    array2.each do |el|
	        unless array1.include? el
	        array3 << el
	        end
	    end
	    array3
	end
	
	puts "-------FOUR-------"
	puts all_uniqs([1, 2, 3], [1, 2, 4]) == [3, 4]
	puts all_uniqs([1, 2, 7], [1, 3, 8]) == [2, 7, 3, 8]
	```
