Go
==
.. meta::
   :description lang=en: Go docs

.. warning::

    This rst document is generated programatically from https://github.com/gsweene2/garrett-learns-go/convert-to-rst.py

write-to-file.go
----------------
Example
*******
.. code-block:: go
  :linenos:



  package main
  import (
      "fmt"
      "os"
  )
  
  func check(e error) {
      if e != nil {
          panic(e)
      }
  }
  
  func WriteToFile() {
      filePath := "/Users/garrettsweeney/git/garrett-learns-go/write-to-file.txt"
      f, err := os.Create(filePath)
      check(err)
  
      defer f.Close()
  
      bytesWritten, err := f.WriteString("I can write to a file\n")
      check(err)
      fmt.Printf("Wrote %d bytes to %s\n", bytesWritten, filePath)
  
      f.Sync()
  }
  
  func main() {
      WriteToFile()
  }


go.mod
------
Example
*******
.. code-block:: go
  :linenos:



  module garrett-learns-go
  
  go 1.15


concat-strings_test.go
----------------------
Example
*******
.. code-block:: go
  :linenos:



  package main
  
  import "testing"
  
  func ConcatStringsTest(t *testing.T) {
      s1 := "Concat"
      s2 := "enation"
      got := ConcatStrings(s1,s2)
      want := "Concatenation"
  
      if got != want {
          t.Errorf("got %q want %q", got, want)
      }
  }
  


write-to-file.txt
-----------------
Example
*******
.. code-block:: go
  :linenos:



  I can write to a file


concat-strings.go
-----------------
Example
*******
.. code-block:: go
  :linenos:



  package main
  
  func ConcatStrings(s1 string, s2 string) string {
      return s1 + s2
  }
  


hello-world_test.go
-------------------
Example
*******
.. code-block:: go
  :linenos:



  package main
  
  import "testing"
  
  func TestHello(t *testing.T) {
      got := Hello()
      want := "Hello, Garrett"
  
      if got != want {
          t.Errorf("got %q want %q", got, want)
      }
  }
  


README.md
---------
Example
*******
.. code-block:: go
  :linenos:



  # Garrett Learns Go
  
  Each file is a concept or example of something, with test cases.
  
  Many examples are built from [gobyexample.com](https://gobyexample.com/) or [Learn Go with tests](https://quii.gitbook.io/learn-go-with-tests), but modified for my understanding.
  
  To run a program:
  ```
  go run program.go
  ```
  
  To run the tests:
  ```
  go test
  ```
  
  To build a binary and run:
  ```
  go build program.go
  ./program
  ```
  


hello-world.go
--------------
Example
*******
.. code-block:: go
  :linenos:



  package main
  
  import "fmt"
  
  func Hello() string {
      return "Hello, Garrett"
  }
  


add-three-numbers_test.go
-------------------------
Example
*******
.. code-block:: go
  :linenos:



  package main
  
  import "testing"
  
  func AddThreeNumbersTest(t *testing.T) {
      n1 := 3
      n2 := 4
      n3 := 5
      got := AddThreeNumbers(n1, n2, n3)
      want := 12
  
      if got != want {
          t.Errorf("got %q want %q", got, want)
      }
  }
  


add-three-numbers.go
--------------------
Example
*******
.. code-block:: go
  :linenos:



  package main
  
  func AddThreeNumbers(n1 int, n2 int, n3 int) int {
      return n1 + n2 + n3
  }
  


