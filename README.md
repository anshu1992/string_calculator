# README

# String Calculator

This project demonstrates the principles of Test-Driven Development (TDD) through the implementation of a simple string calculator. The `StringCalculator` class provides an `add` method that handles various cases of number addition from a string input, including handling custom delimiters and throwing exceptions for negative numbers.

## Features

- Performs addition on a simple string of length up to 2.
- Handles an unknown amount of numbers.
- Handles new lines between numbers.
- Supports custom delimiters specified in the format `//[delimiter]\n[numbers...]`.
- Throws an exception for negative numbers, listing all negative values.

## Usage

### Installation

1. Clone the repository:
  ```sh
  git clone https://github.com/anshu1992/string_calculator
  cd string_calculator
  ```

2. Install dependencies:
  ```sh
  bundle install
  ```

### Running Tests

The project uses RSpec for testing. To run the tests, use the following command:
```sh
bundle exec rspec
```

### Example

Here is a simple example of how to use the `StringCalculator` class:

```ruby
require_relative 'string_calculator'

calculator = StringCalculator.new
puts calculator.add("1,2")             # Output: 3
puts calculator.add("1,2,3,4,5")       # Output: 15
puts calculator.add("1\n2,3")          # Output: 6
puts calculator.add("//;\n1;2;3")      # Output: 6
```

## StringCalculator Class

The `StringCalculator` class provides a method `add` which takes a string of numbers and returns their sum.

### Method: `add`

#### Parameters

- `numbers_string` (String): The string containing numbers separated by delimiters.

#### Returns

- Integer: The sum of the numbers in the input string.

#### Raises

- RuntimeError: If the input string contains negative numbers. The exception message lists all negative numbers found.

## Covered Cases

| Commit Link | Description |
|-------------|-------------|
| [Case 1](https://github.com/anshu1992/string_calculator/commit/ce5af7a534077f557b6f17160c16bde340ffdb95) | Performs addition on a simple string of up to length 2 |
| [Case 2](https://github.com/anshu1992/string_calculator/commit/697c3e8fd230eb066db7731d1b0730c603a0a3a5?diff=split&w=1) | Allows the `add` method to handle an unknown amount of numbers |
| [Case 3](https://github.com/anshu1992/string_calculator/commit/d11e30b767e90bddd9d3948d9b0d29865a5118b2) | Allows the `add` method to handle new lines between numbers |
| [Case 4](https://github.com/anshu1992/string_calculator/commit/67b842d0ecd82d61395ac5efe274ae030ff803bb) | Supports custom delimiters |
| [Case 5](https://github.com/anshu1992/string_calculator/commit/8260e7166c32585fab9e667408dc23ac4bc27b7a) | Calling `add` with a negative number will throw an exception "negatives not allowed" |

## Project Structure

```
.
- Gemfile: Specifies gem dependencies.
- Gemfile.lock: Locks the gem dependencies to specific versions.
- README.md: Contains the project description and usage instructions.
- string_calculator.rb: Contains the StringCalculator class implementation.
- spec/
  - spec_helper.rb: Configures the RSpec environment.
  - string_calculator_spec.rb: Contains RSpec tests for the StringCalculator class.
```
