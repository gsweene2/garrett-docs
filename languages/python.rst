Python
======

.. meta::
   :description lang=en: Python docs


Count Occurances in List
------------------------

Code Example
************

.. code-block:: python
  :linenos:

  from collections import Counter

  def count_occurances_in_list(my_list, item):
      return my_list.count(item)

  def count_occurances_of_each_item_in_list(my_list):
      return Counter(my_list)

Test Example
************

.. code-block:: python
  :linenos:

  def test_count_occurances_in_list():
      # Arrange
      my_list = [1, 3, 4, 2, 2, 2, 4, 2]
      # Act
      occurances = count_occurances_in_list(my_list, 2)
      # Assert
      assert 4 == occurances

  def test_count_occurances_of_each_item_in_list():
      # Arrange
      my_list = ['a', 'c', 'd', 'b', 'b', 'b', 'c', 'b']
      # Act
      occurances = count_occurances_of_each_item_in_list(my_list)
      # Assert
      expected = { 'a': 1, 'b': 4, 'c': 2, 'd': 1}
      assert expected == occurances

Shallow vs Deep Copy
--------------------

Code Example
************

.. code-block:: python
  :linenos:

  import copy

  def shallow_copy(my_list):
      return list(my_list)

  def deep_copy(my_list):
      return copy.deepcopy(my_list)

Test Example
************

.. code-block:: python
  :linenos:

  def test_shallow_copy__modify_object_in_init_list__should_affect_copy_list():
    # Arrange
    init_list = [1, 2, 3, [1, 2, 3]]
    # Act
    copy_list = shallow_copy(init_list)
    init_list[3].append(4)
    # Assert
    assert copy_list == [1, 2, 3, [1, 2, 3, 4]]
    assert init_list == [1, 2, 3, [1, 2, 3, 4]]

  def test_deep_copy__modify_object_in_init_list__should_not_affect_copy_list():
    # Arrange
    init_list = [1, 2, 3, [1, 2, 3]]
    # Act
    copy_list = deep_copy(init_list)
    init_list[3].append(4)
    # Assert
    assert copy_list == [1, 2, 3, [1, 2, 3]]
    assert init_list == [1, 2, 3, [1, 2, 3, 4]]


Sorting
-------

Code Example
************

.. code-block:: python
  :linenos:

  def sort_list_ascending(my_list):
      return sorted(my_list)

  def sort_list_descending(my_list):
      return sorted(my_list, reverse=True)

Test Example
************

.. code-block:: python
  :linenos:

  def test_sort_list_ascending__should_return_sorted_list():
      # Arrange
      my_list = ['A','C','D','B','E']
      # Act
      sorted_list = sort_list_ascending(my_list)
      # Assert
      expected = ['A','B','C','D','E']
      assert sorted_list == expected

  def test_sort_list_descending__should_return_sorted_list():
      # Arrange
      my_list = ['A','C','D','B','E']
      # Act
      sorted_list = sort_list_descending(my_list)
      # Assert
      expected = ['E','D','C','B','A']
      assert sorted_list == expected


Ternary Statements
------------------

Code Example
************

.. code-block:: python
  :linenos:

  def get_key_from_map_else_return_default_ternary(my_map, key):
      return my_map[key] if key in my_map else 'Not Found'

Test Example
************

.. code-block:: python
  :linenos:

  def test_get_key_from_map_else_return_default_ternary_key_exists():
      # Arrange
      my_map = {'a':1,'b':2,'c':3}
      # Act
      value = get_key_from_map_else_return_default_ternary(my_map, 'a')
      # Assert
      assert value == 1

  def test_get_key_from_map_else_return_default_ternary_key_dne():
      # Arrange
      my_map = {'a':1,'b':2,'c':3}
      # Act
      value = get_key_from_map_else_return_default_ternary(my_map, 'z')
      # Assert
      assert value == 'Not Found'



