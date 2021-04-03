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


Lambda: Welcome Message
-----------------------

Code Example
************

.. code-block:: python
  :linenos:

  print_welcome_lambda = lambda first, last: f"Welcome to garretts-docs, {first} {last}"

Test Example
************
  
.. code-block:: python
  :linenos:

  def test_print_welcome_lambda():
      # Arrage
      first, last = "Garrett", "Smith"
      # Act
      result = print_welcome_lambda(first, last)
      # Assert
      expected = "Welcome to garretts-docs, Garrett Smith"
      assert expected == result

List Comprehension: Find Substrings in list of Strings
------------------------------------------------------

Code Example
************

.. code-block:: python
  :linenos:

  """
  List Comprehension: Find Substrings in list of Strings with 
  """

  def find_strings_that_contain_substring_in_list_comprehension(list_of_strings, substring):
      return [word for word in list_of_strings if substring in word.lower()] 

Test Example
************
  
.. code-block:: python
  :linenos:

  def test_find_strings_that_contain_substring_in_list_comprehension():
      # Arrange
      list_of_strings = ['Fred','Freedy','Reddison','Dave','Bob','Red']
      # Act
      result = find_strings_that_contain_substring_in_list_comprehension(list_of_strings,'red')
      # Assert
      expected = ['Fred','Reddison','Red']
      assert expected == result
 
Basic List Comprehension
------------------------

Code Example
************

.. code-block:: python
  :linenos:

  def string_to_list_comprehension(my_string):
      letter_list = [ letter for letter in my_string ]
      return letter_list

Test Example
************
  
.. code-block:: python
  :linenos:

  def test_string_to_list_comprehension():
      # Arrange
      my_string = 'awesome'
      # Act
      result_string = string_to_list_comprehension(my_string)
      # Assert
      expected = ['a','w','e','s','o','m','e']
      assert expected == result_string

Merge Dictionaries
------------------

Code Example
************

.. code-block:: python
  :linenos:

  def merge_dictionaries(dict_1, dict_2):
      return {**dict_1, **dict_2}

Test Example
************
  
.. code-block:: python
  :linenos:

  def test_merge_dictionaries():
      # Arrage
      older_data = { "bob": 35, "phil": 39, "katie": 30 }
      newer_data = { "phil": 41, "fred": 19 }
      # Act
      result = merge_dictionaries(older_data, newer_data)
      # Assert
      expected = { "bob": 35, "phil": 41, "katie": 30, "fred": 19 }
      assert expected == result

  def test_merge_dictionaries():
      # Arrage
      older_data = { "phil": 41, "fred": 19 }
      newer_data = { "bob": 35, "phil": 39, "katie": 30 }
      # Act
      result = merge_dictionaries(older_data, newer_data)
      # Assert
      expected = { "phil": 39, "fred": 19, "bob": 35, "katie": 30 }
      assert expected == result


Configure repo with pre-commit formatting
-----------------------------------------

Reference: https://black.readthedocs.io/en/stable/version_control_integration.html

Create new file ``pre-commit-config.yaml``

.. code-block:: yaml
  :linenos:

  repos:
    - repo: https://github.com/psf/black
      rev: 19.10b0 # Replace by any tag/version: https://github.com/psf/black/tags
      hooks:
        - id: black
          language_version: python3 # Should be a command that runs python3.6+
  
Install pre-commit with ``pip install pre-commit``

Run pre-commit with ``pre-commit install``

Then commit the changes and add another commit. Should see the following:

.. code-block:: console
  :linenos:

  [INFO] Initializing environment for https://github.com/psf/black.
  [INFO] Installing environment for https://github.com/psf/black.
  [INFO] Once installed this environment will be reused.
  [INFO] This may take a few minutes...
  black....................................................................Passed


Template Example
----------------

Code Example
************

.. code-block:: python
  :linenos:

Test Example
************
  
.. code-block:: python
  :linenos:
