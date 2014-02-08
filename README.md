Functions
=========

#Learning to code in Python

import math


def area(base, height):
    '''(number, number) -> number

    Return the area of a triangle with dimensions base and height.
    '''

    return base * height / 2

def convert_to_celsius(fahrenheit):
    '''(number) -> float

    Return the number of Celsius degrees equivalent to fahrenheit degrees

    >>>convert_to_celsius(32)
    0.0
    >>>convert_to_celsius(212)
    100.0
    '''
    return (fahrenheit - 32) * 5 / 9

def perimeter(side1, side2, side3):
    '''(number, number, number) -> number

    Return the perimeter of the triangle with sides of length side1, side2 and side3.

    >>>perimeter(3, 4, 5)
    12
    >>>perimeter(10.5, 6, 9.3)
    25.8
    '''

    return side1 + side2 + side3

def semiperimeter(side1, side2, side3):
    ''' (number, number, number) -> float

    Return the semiperimeter of a triangle with sides of length side1, side2 and side3

    >>>semiperimeter(3, 4, 5)
    6.0
    >>>semiperimeter(10.5, 6, 9.3)
    12.9
    '''

    return perimeter(side1, side2, side3) / 2

def convert_to_minutes(num_hours):
    '''(int) -> int

    Return the number of minutes there are in number of hours

    >>>convert_to_minutes(2)
    120
    '''

    result = num_hours * 60
    return result

def announce_location(country):
    print(country)
    return country

def area_hero(side1, side2, side3):
    '''(number, number, number) -> float

    Return the area of a triange with sides of length side1, side2, and side3.

    >>>area_hero(3, 4, 5)
    6.0
    >>>area_hero(10.5, 6, 9.3)
    27.73168584850189
    '''

    semi = semiperimeter(side1, side2, side3)
    area = math.sqrt(semi * (semi - side1) * (semi - side2) * (semi - side3))
    return area

def report_status(scheduled_time, estimated_time):
    ''' (number, number) -> str

    Return the flight status (on time, early, delayed)
    for a flight that was scheduled to arrive at
    scheduled_time, but is now estimated to arrive at estimated_time.

    Pre-condition: 0.0 <= scheduled_time < 24 and
    0.0 <= estimated_time < 24

    >>>report_status(14.3, 14.3)
    'on time'
    >>>report_status(12.5, 11.5)
    'early'
    >>>report_status(9.0, 9.5)
    'delayed'
    '''

    if scheduled_time == estimated_time:
        return 'on time'
    elif scheduled_time > estimated_time:
        return 'early'
    else:
        return 'delayed'

def is_comfortable(temp):
    '''(number) -> bool
    Return whether temp is 22.5.'''
    return temp == 22.5

    
def fruit_color(fruit):
    if fruit == 'apple':
        return 'red'
    elif fruit == 'banana':
        return 'yello'
    elif fruit == 'pear':
        return 'green'

def traffic_report(light):
    if light == 'red':
        return 'stop'
    elif light == 'yellow':
        return 'slow'
    elif light == 'green':
        return 'go'

def grade_report(grade):
    if grade >= 80:
        return 'excellent'
    elif grade >= 50:
        return 'pass'

def count_vowel(s):
    ''' (str) -> int

    Return the number of vowels in s.  Do not treat the
    letter y as a vowel.

    >>> count_vowels('Happy Anniversary!')
    5
    >>> count_vowels('xyz')
    '''

    num_vowels = 0

    for char in s:
        if char in 'aeiouAEIOU':
            num_vowels = num_vowels + 1

        return num_vowels

def collect_vowels(s):
    ''' (str) -> str

    Return the vowels from s.  Do not treat the letter y as a vowel.

    >>> collect_vowels('Happy Anniversay!')
    'aAiea'
    >>> collect_vowels('xyz')
    ''
    '''

    vowels = ''

    for char in s:
        if char in 'aeiouAEIOU':
            vowels = vowels + char

    return vowels


def common_chars(s1, s2):
    '''(str, str) -> str

    Return a new string containing all characters from s1 that appear
    at least once in s2.  The characters in the result will appear in the
    same order as they appear in s1.

    >>> common_chars('abc', 'ad')
    'a'
    >>> common_chars('a', 'a')
    'a'
    >>> common_chars('abb', 'ab')
    'abb'
    >>> common_chars('abracadabra', 'ra')
    araaara'
    '''

    res = ''

    for ch in s1:
        for ch in s2:
            res = res + ch

    return res


def up_to_vowel(s):
    ''' (str) -> str

    Return a substring of s from index 0 up to but
    not including the first vowel in s.

    >>> up_to_vowel('hello')
    'h'
    >>> up_to_vowel('there')
    'th'
    >>> up_to_vowel('cs')
    'cs'
    '''

    # before_vowel contains all the characters found in s[0:i].
    before_vowel = ''
    i=0

    # Accumulate the non-vowels at the beginning of the string.
    while i < len(s) and not (s[i] in 'aeiouAEIOU'):
        before_vowel = before_vowel + s[i]
        i = i + 1

    return before_vowel

def get_answer(prompt):
    ''' (str) -> str

    Use prompt to ask the user for a "yes" or "no"
    answer and continue asking until the user gives
    a valid response.  Return the answer.
    '''

    answer = input(prompt)

    while not (answer == 'yes' or answer == 'no'):
        answer = input(prompt)

    return answer

def last_vowel(s):
    """(str) -> str

    Return the last vowel in s if one exists;
    otherwise, return None.

    >>> last_vowel("cauliflower")
    "e"
    >>> last_vowel("pfft")
    None
    """

    i = len(s) - 1
    while i >= 0:
        if s[i] in 'aeiouAEIOU':
            return s[i]
        i = i - 1

    return None

def double_even_indices(lst):
    """ (list of int) -> NoneType

    Double every other int in lst, starting
    at index 0.
    """

    i = 0
    while i < len(lst):
        lst[i] = lst[i] * 2
        i = i + 2


def double_first_element(lst):
	if len(lst) > 0:
		lst[0] = lst[0] * 2

def mystery(s):
    i = 0
    result = ''

    while not s[i].isdigit():
        result = result + s[i]
        i = i + 1

    return result

def example(L):
    """ (list) -> list
    """
    i = 0
    result = []
    while i < len(L):
        result.append(L[i])
        i = i + 3
    return result


def compress_list(L):
    """ (list of str) -> list of str

    Return a new list with adjacent pairs of string elements from L
    concatenated together, starting with indices 0 and 1, 2 and 3,
    and so on.

    Precondition: len(L) >= 2 and len(L) % 2 == 0

    >>> compress_list(['a', 'b', 'c', 'd'])
    ['ab', 'cd']
    """
    compressed_list = []
    i = 0

    while i < len(L):
        compressed_list.append(L[i] + L[i + 1])
        i = i + 2

    return compressed_list

def while_version(L):
    """ (list of number) -> number
    """
    i = 0
    total = 0

    while i < len(L) and L[i] % 2 != 0:
        total = total + L[i]
        i = i + 1

    return total

def for_version(L):
    found_even = False
    total = 0

    for num in L:
        if num % 2 != 0 and not found_even:
            total = total + num
        else:
            found_even = True
 
    return total

values = []
for num in range(1, 4):
    values.append(num * 3)
print(values)

def mystery(lst):
    for sublist in lst:
        total = 0
        for num in sublist:
            total = total + num
            
    return total

def merge(L):
    merged = []
    for i in range(0, len(L), 3):
        merged.append(L[i] + L[i + 1] + L[i + 2])
    return merged

def mystery(s):
    """ (str) -> bool
    """
    matches = 0
    for i in range(len(s) // 2):
        if s[i] == s[len(s) - 1 - i]:
            matches = matches + 1
    
    return matches == (len(s) // 2)






def merge(L):
    merged = []
    for i in range(0, len(L), 3):
        merged.append(L[i] + L[i + 1] + L[i + 2])
    return merged


def shift_right(L):
    ''' (list) -> NoneType

    Shift each item in L one position to the right
    and shift the last item to the first position.

    Precondition: len(L) >= 1
    '''

    last_item = L[-1]

    for i in range(len(L)):
        L[i + 1] = L[i]

    L[0] = last_item

def make_pairs(list1, list2):
    ''' (list of str, list of int) -> list of [str, int] list
    
    Return a new list in which each item is a 2-item list with the string from the
    corresponding position of list1 and the int from the corresponding position of list2.
    
    Precondition: len(list1) == len(list2)
    
    >>> make_pairs(['A', 'B', 'C'], [1, 2, 3])
    [['A', 1], ['B', 2], ['C', 3]]
    '''
    
    pairs = []
    
    for i in range(len(list1)):
        inner_list = []
        inner_list.append(list1[i])
        inner_list.append(list2[i])
    pairs.append(inner_list)
        
    return pairs

def contains(value, lst):
    """ (object, list of list) -> bool

    Return whether value is an element of one of the nested lists in lst.

    >>> contains('moogah', [[70, 'blue'], [1.24, 90, 'moogah'], [80, 100]])
    True
    """

    found = False  # We have not yet found value in the list.

    for item in lst:
        if value == item:
            value = True

    return found

def lines_startswith(file, letter):
    """ (file open for reading, str) -> list of str

    Return the list of lines from file that begin with letter. The lines should have the
    newline removed.

    Precondition: len(letter) == 1
    """

    matches = []

    for line in file:
        matches.append(line.startswith(letter).rstrip('\n'))

    return matches

def write_to_file(file, sentences):
    """ (file open for writing, list of str) -> NoneType

    Write each sentence from sentences to file, one per line.

    Precondition: the sentences contain no newlines.
    """

    for s in sentences:
        file.write(s + '\n')

def increment_values(d):
    """ (dict with number values) -> NoneType

    Increase each value in d by 1.
    """

    for k in d:
        k = k + 1

def contains(v, d):
    ''' (object, dict of {object: list}) -> bool

    Return whether v is an element of one of the list values in d.

    >>> contains('moogah', {1: [70, 'blue'], 2: [1.24, 'moogah', 90], 3.14: [80, 100]})
    True
    >>> contains('moogah', {'moogah': [1.24, 'frooble', 90], 3.14: [80, 100]})
    False
    '''

    found = False  # Whether we have found v in a list in d.

    for k in d:
        if v == k:
            found = True
            
    return found

def f(x):
    y = x * 3

    return y - x

def double_values(collection):
    for v in range(len(collection)):
        collection[v] = collection[v] * 2

    return double_values

def larger_of_smallest(L1, L2):
    '''(list of int, list of int) -> int

    Return the larger of the smallest value in L1 and the smallest value in
    L2.

    Precondition: L1 and L2 are not empty.

    >>> larger_of_smallest([1, 4, 0], [3, 2])
    2
    >>> larger_of_smallest([4], [9, 6, 3])
    4
    '''

    return max((min(L1)), (min(L2)))


def same_length(L1, L2):
    '''(list, list) -> bool

    Return True if and only if L1 and L2 contain the same number of elements.
    '''

    return len(L1) == len(L2)

def gather_every_nth(L, n):
    '''(list, int) -> list

    Return a new list containing every n'th element in L, starting at index 0.

    Precondition: n >= 1

    >>> gather_every_nth([0, 1, 2, 3, 4, 5], 3)
    [0, 3]
    >>> gather_every_nth(['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i'], 2)
    ['a', 'c', 'e', 'g', 'i']
    '''

    result = []
    i = 0
    while i < len(L):
        result.append(L[i])
        i = i + n

    return result

def get_keys(L, d):
    '''(list, dict) -> list

    Return a new list containing all the items in L that are keys in d.

    >>> get_keys([1, 2, 'a'], {'a': 3, 1: 2, 4: 'w'})
    ['a', 1]
    '''

    result = []
    for k in d:
        if k in L:
            result.append(k)

    return result

def get_negative_nonnegative_lists(L):
    '''(list of list of int) -> tuple of (list of int, list of int)

    Return a tuple where the first item is a list of the negative ints in the
    inner lists of L and the second item is a list of the non-negative ints
    in those inner lists.

    Precondition: the number of rows in L is the same as the number of
    columns.

    >>> get_negative_nonnegative_lists([[-1,  3,  5], [2,  -4,  5], [4,  0,  8]])
    ([-1, -4], [3, 5, 2, 5, 4, 0, 8])
    '''

    nonneg = []
    neg = []
    for row in range(len(L)):
        for col in range(len(L)):
            if L[row][col] < 0:
                nonneg.append(L[row][col])
            else:
                neg.append(L[row][col])
    
    return (neg, nonneg)
        
