## Introduction
MATLAB is a high-level language that is widely used for numerical computations, data analysis, and visualization. Originally designed to serve as an accessible language for the engineering and scientific community it has a very mathematical syntax and large array of tools one might need for such problems.

## Supported paradigms
MATLAB supports a variety of programming paradigms, including object-oriented, functional, and procedural programming. MATLAB is primarily an imperative language, but it does support some declarative programming constructs, such as logical indexing.

Functional Example:
```matlab
% Defines the factorial recursive function.
function result = factorial(n)
  if n == 0
      result = 1;
  else
      result = n * factorial(n-1);
  end
end
```

While we didn't need to use it for the class MATLAB has a fairly straight forward object scheme.  
It is similar to C++ in the sense that object properties and methods are seperated in blocks.  
Object Oriented Example: 
```matlab
classdef Circle
    properties
        Radius double
        Center Point
    end
    methods
        function obj = Circle(radius, center)
            obj.Radius = radius;
            obj.Center = center;
        end
        function area = computeArea(obj)
            area = pi * obj.Radius^2;
        end
    end
end
```
```matlab
center = Point(0, 0);
radius = 5;
circle = Circle(radius, center);
area = circle.computeArea();
disp(area); % Returns 78.5398
```

## Syntax
MATLAB has a relatively easy-to-learn syntax that is similar to other programming languages. However, its semantics are unique due to its focus on mathematical computations and its built-in functions. It also includes various access keywords like other languages. public, private, abstract,static and sealed for example to supplement it's object-oriented features.  
The language further allows to do easy collection splicing where we can get parts of the data without long detailed loops  
The 2nd assignment should display this fairly easily with the (:,1). This example says take every cell from column 1 of the data.
```matlab
% Read file
data = importdata('CurveData1.csv');

% Get data points
x = data(:, 1);
y = data(:, 2);

% Datalength check
if length(x) ~= 25 || length(y) ~= 25
    error('The file does not contain 25 data points.');
end
```
You can even do things like:
```matlab
xs=[x(1:5); x(11:end)]
ys=y(6:end)
```
The brackets allows us to make lists with the variables inside. Often useful to take out things we don't need, like test data for example.

## Data Structures and Uses
MATLAB has a variety of built-in data types, including arrays, matrices, structures, and cell arrays, and it also supports user-defined data types.
Depending on the data type it also offers different indexing options for different purposes.
```matlab
% create a cell array with two strings
myCellArray = {'foo', 'bar'};

% parentheses indexing returns a cell array
cellResult = myCellArray(1);
disp(cellResult); % prints "foo"

% curly bracket indexing returns the contents of the cell
contentsResult = myCellArray{1};
disp(contentsResult); % prints "foo"
```
The following becomes relevant as not all operations are accessible to cells. While the language feels fairly loose the greatest painpoint I had to discover about is the difference by cell indexing and value indexing, especially over larger datasets.

## Under the hood
MATLAB code is typically interpreted, but it can also be compiled into standalone executables using the MATLAB Compiler. MATLAB uses a virtual machine to manage memory and execute code. It also supports direct memory access through its low-level memory management functions.  
Speaking of memory management, MATLAB manages memory automatically using a garbage collector. As mentioned we can turn this off to allow manual memory management, useful to interface with other languages through its support for calling external functions, such as C, C++, and Fortran functions. Another notable example is matplotlib on python, giving the language an easy way to plot data without leaving the comforts of python.

## Comments
First let's start with the potential problems: Like in any other language MATLAB's allowance for global variables is a risk point not only because they can be read from anywhere but they can be updated at *any* time. Next as far as I could tell, basically every numeric value in matlab is floating point. Thankfully the default is double precision but can still pose a risk catastrophic cancellation for very large or very small numbers.  
And lastly, direct memory management is a loaded gun pointed at one's knee. Like C/C++ it's easy to lose track of memory indexes and eventually get garbage at best and crash the program at worse.

Now the good. This language feels like the excel of computer languages. Because of it's mathematical nature I could see myself use it for data analysis or side projects. It has a similar feeling... everything? While retaining a distinct identity to fill a niche role.  
Last journal I complained about the inability to opt out of functional programming with racket. Matlab is the opposite, you are given the ability to opt-in into the chaotic and often hard to think about recursive/functional programming. I would place it at a nice 2nd place of the 4 languages we have examined over this course right under python.
