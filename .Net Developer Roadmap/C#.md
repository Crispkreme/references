## C# Fundaments

**Introduction**
What is the difference of C# vs .NET

**C#**
- C# is a programming language

**.NET**
- .NET is a framework for building applications on windows

This are the 2 components of .NET
- CLR (Common Language Runtime)
- Class Library

**CLR**
- is essentially an application that is setting in the memory whose job is to translate the IL code into machine code and this process is called **just-in-time (JIT)**code

**Architecture of .NET Applications**
- When you build an application it consists of building blocks called "**Classes**" this classes collaborate with each other and as a results the application provides some functionality.

- **Classes** - class is a container that has some data which called **attributes** and functions called **methods**. Function and method have a behavior they execute code to do the things for us 
- **Data** - represents the state of the applications.

Terminal: `Ubuntu`  
Command:  
```sh

    Example:
    | **Class**               |
    | ----------------------- | 
    | Data                    | 
    | ----------------------- |  
    | Methods                 | 

    Example:
    | **Car**                 |
    | ----------------------- | 
    | Make                    | 
    | Model                   | # this is the "**DATA**"
    | Color                   | 
    | ----------------------- |  
    | Start()                 | #this is the "**Methods/Functions**"
    | Move()                  | 

```

- **Namespace** - is a container for related classes.
- **Assembly** - is a container for related namespace physically it is a file on the disk which can either be executable or **Dynamically Linked Library (DLL)**.

Terminal: `Ubuntu`  
Command:  
```sh

    # go to your C# application
    # create new file
    # then select console application
    # Templates > Visual C# > Windows > Console Applications

    namespace HelloWorld 
    {
        class Program
        {
            static void Main(string[] args) 
            # main - method
            # args - parameters
            {
                Console.WriteLine("Hello World");
            }
        }
    }
```

**Variable and Constants**
- **Variable** 
    - a name given to a storage location in the memory.
    - it declare a static value to create safety to our applications.

- **Constant** 
    - is a immutable/does not change value throught the application lifetime.
    - it must always have a value.
    - we cannot define the constants without settings its value;

- **Identifiers** 
    - Cannot start with a number;
    - Cannot include with a white space;
    - Cannot be a reserved keyword;
    - use meaningful names.

Terminal: `Ubuntu`  
Command:  
```sh

    int number;
    int Number = 1;
    const float Pi = 3.14;

```

- **Naming Conventions**
    - Camel Case: **firstName**. # use in local variables.
    - Pascal Case: **FirstName**. # use in constants.
    - Hungarian Case: **strFirstName**.

Terminal: `Ubuntu`  
Command:  
```sh
    
    Data-Types

    Primitive Types:
        - Integral Numbers
        - Real Number
        - Characters
        - Boolean

    Example:
    | **Car**                 |  C# Type | .NET Types | Bytes | Range
    | ----------------------- | -------- | ---------- | ----- | --------------------------- |
    | Integral Numbers        | byte     | Byte       | 1     | 0 to 255                    |
    |                         | short    | Int16      | 2     | -32,768 to 32,767           |
    |                         | int      | Int32      | 4     | -2.1B to 2.1B               |
    |                         | long     | Int64      | 8     | ...                         |
    | ----------------------- |--------- | ---------- | ----- | --------------------------- |
    | Real Numbers            | float    | Single     | 4     | -3.4x10^(38) to 3.4x10^(38) |
    |                         | double   | Double     | 8     | ...                         |
    |                         | decimal  | Decimal    | 16    | -7.9x10^(28) to 7.9x10^(28) |
    | ----------------------- |--------- | ---------- | ----- | --------------------------- |
    | Characters              | char     | Char       | 2     | Unicode Characters          |
    | ----------------------- |--------- | ---------- | ----- | --------------------------- |
    | Boolean                 | bool     | Boolean    | 1     | True / False                |

    float number = 1.2f; # f - it tells compiler to treat it as a float
    decimal number = 1.2m; # m - it tells compiler to treat it as a decimal

    Non Primitive Types:
        - String
        - Array
        - Enum
        - Class

```

**Overflowing**
Terminal: `Ubuntu`  
Command:  
```sh
    
    # checking for overflowing
    checked 
    {
        byte number = 255;
        number = number + 1;
    }

```

**Scope**
- where a variable/constants has a meaning.
- it can be access through its children

Terminal: `Ubuntu`  
Command:  
```sh
    
    {
        # a or b cannot access it parent;
        # a can access the b or c as a child;
        byte a = 1;
        {
            byte b = 2;
            {
                byte c = 3;
            }
        }
    }

    Examples:
    namespace Variables 
    {
        class Program
        {
            static void Main(string[] args) 
            {
                byte number = 2;
                int count = 10;
                float totalPrice = 20.95f;
                char character = 'A';
                string firstname = "Marvin"
                bool isWorking = false;

                Console.WriteLine(number);
                Console.WriteLine(count);
                Console.WriteLine(totalPrice);
                Console.WriteLine(character);
                Console.WriteLine(firstname);
                Console.WriteLine(isWorking);

                # format string
                Console.WriteLine("{0} {1}", byte.MinValue, byte.MaxValue);
                Console.WriteLine("{0} {1}", float.MinValue, float.MaxValue);
            }
        }
    }

```

**Type of Converstion**

Terminal: `Ubuntu`  
Command:  
```sh
    
    # EXPLICIT TYPE CONVERSION
    float f = 1.0f;
    int i = (int)f;

    # NON COMPATIBLE TYPE CONVERSION
    string s = "1";
    int i = Convert.ToInt32(s);
    int j = int.Parse(s);

    # CONVERT CLASS
    - ToByte();
    - ToInt16();
    - ToInt32();
    - ToInt64();

    Examples:
    namespace TypeConversion 
    {
        class Program
        {
            static void Main(string[] args) 
            {
                # EXPLICIT TYPE EXAMPLE:

                    # Scenario 1:
                    byte b = 1;
                    int i = b;
                    Console.WriteLine(i);

                    # Scenario 2:
                    int i = 1000;
                    byte b = (byte) i;
                    Console.WriteLine(b);

                # NON COMPATIBLE TYPE EXAMPLE:

                    # Scenario 1:
                    var number = "1234";
                    int i = Convert.ToInt32(number);
                    Console.WriteLine(i)

                    # Scenario 2:
                    try
                    {
                        var number = "1234";
                        int b = Convert.ToByte(number);
                        Console.WriteLine(b)
                    }
                    catch (Exception)
                    {
                        Console.WriteLine("the number cannot converted to a byte.");
                    }

                    # Scenario 3:
                    try
                    {
                        var str = "true";
                        int b = Convert.ToBoolean(str);
                        Console.WriteLine(b)
                    }
                    catch (Exception)
                    {
                        Console.WriteLine("the number cannot converted to a byte.");
                    }
            }
        }
    }
```

**C# Operators**
Terminal: `Ubuntu`  
Command:  
```sh
    
    # Arithmetic Operators
    # Comparison Operators
    # Assignment Operators
    # Logical Operators
    # Bitwise Operators

    Examples:
    namespace Operators 
    {
        class Program
        {
            static void Main(string[] args) 
            {
                var a = 10;
                var b = 3;
                var c = 5;

                Console.WriteLine( a + b );
                Console.WriteLine( a / b );
                Console.WriteLine( (float)a / (float)b );
                Console.WriteLine( a + b * c);
                Console.WriteLine( (a + b) * c);
                Console.WriteLine( a > b );
                Console.WriteLine( a == b );
                Console.WriteLine( a != b );
                Console.WriteLine( !(a != b) );
                Console.WriteLine( c > b && c > a );
                Console.WriteLine( c > b && c == a );
                Console.WriteLine( c > b || c == a );
            }
        }
    }
```

## C# 12*
## .Net 8
## .NET CLI
## .NET Aspire