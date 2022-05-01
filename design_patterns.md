# Design Patterns

## Abstract Factory

The abstract factory defines a interface to create all distinct products, but leaves the real creation of the product to the concrete factory classes. Each type of factory matches a determined variety of products.

The client code calls the methods of creation of a specfici factory object instead of call directly with a call to the constructor(using the `new` operator). As a factory matches a unique variant of product, all their products will be compatible.

## Factory Method

The Factory Method is useful when you needs to provide high level of flexibility for your code.
The factory methods can be recognizable as creation methods that creates objects of concrete classes, but returns them as objects of type or abstract interface.

## Builder

The builder pattern is useful when you need to create a object with many options of configuration.

The builder pattern can be recognizable in a Class that have a unique method of creation and many methods to configurate the resulting object. The methods of the builder usually supports chaining (Example: `someBuilder.configValueA(1).configValueB(1).create()`.

## Adapter

This pattern is frequently used  in systems based in some legacy code. In that cases, the adapters don't create legacy code with modern classes.

The constructor uses a instance of a different abstract/interface. When the constructor receives a call from one of its methods, he converts it's parameters to the given appropriate format and directs to one or many methods from the received object.

```ruby
class Target
  def request
    'Target: The default target\'s behavior.'
  end
end

class Adaptee
  def specific_request
    '.eetpadA eht fo roivahed laicepS'
  end
end

class Adapter < Target
  def initialize(adaptee)
    @adaptee = adaptee
  end

  def request
    "Adapter: (TRANSLATED) #{@adaptee.specific_request.reverse!}"
  end
end

def client_code(target)
  print target.request
end

puts 'Client: I can work just fine with the Target objects:'
target = Target.new
client_code(target)
puts "\n\n"

adaptee = Adaptee.new
puts 'Client: The Adaptee class has a weird interface. See, I dont\'t undnerstand it:'
puts "Adaptee: #{adaptee.specific_request}"
puts "\n"

puts 'Client: But I can work with it via the Adapter:'
adapter = Adapter.new(adaptee)
client_code(adapter)
```