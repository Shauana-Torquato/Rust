

1- What is Rust?

	Rust is an open-source system programming language
	It is used to develop afficient and safe software
	It makes possible to manage memory and control low-level details but also high-level concepts as iteration and interfaces

		-Type safe: The compiler assures that no operation will be applied to a variableof a wrong type - o compilador assegura que nenhuma operação será aplicada a uma variável de tipo errado
		-Memory safe: Rust pointers (known as references) always refer to valid memory - Ponteiros Rust (conhecidos como referências) sempre se referem a uma memória válida
		-Data race free:  Rust's borrow checker guarantees thread-safety by ensuring that multiple parts of a program can't mutate the same value at same time
		-Zero-cost abstractions: Rust allows the use of high-level concepts, like iteration, interfaces and functional programming, with minimal to no performance costs. The abstraction perform as well as if you wrote the underlying code by hand
		-Minimal runtime: Rust has a minimal and optimal runtime. The language also has no garbage collector to manage memory efficiently. In this way, Rust is most similar to languages like C and C++
		-Targets bare metal: Rust can target embedded and "bare metal" programming, making it suitable to write an operating system kernel or device drivers

2- Unique features of Rust

	Features and limitations of Rust
		The Rust module system: modules, crates and paths
		Rust standart libraries and third-party crates
		The Rust Cargo tool and dependency manager
		When to use Rust

	- Manage code with Rust module system
			collection of features to help the management and organizing of the code (Rust module system)
					Rust module system is composed of:
							crates
							modules
							paths
							tools to work with those items

			Crates - 
				A Rust crate is a compilation unit. 
				It's the smallest piece of code the Rust compiler can run.
				The code in a crate is compiled as reusable units.  
				A crate contains a hierarchy of Rust modules with an implicit, unnamed top-level module.

			Modules - 
				Rust modules help you organize your program by letting you manage the scope of the individual code items inside a crate. 
				Related code items or items that are used together can be grouped into the same module. 
				Recursive code definitions can span other modules

			Paths: 
				In Rust, you can use paths to name items in your code. 
				For example, a path can be a data definition like a vector, a code function, or even a module. 
				The module featue also helps you control the privacy of your paths. 
				You can specify the parts of your code that are accessible publicly versus parts that are private.  
				This feature lets you hide the implementation details

	- Use Rust crates and libraries
			The Rust Standart Library (std) contains reusable code for fundamental definitions and operations in Rust programs. 
			This library has definitions for: 
				core data types like (String) and (Vac<T>); 
				operations for Rust primitives;
				code for commonly used macro functions;
				support for input and output actions;
				and many other areas of functionality.

					There are tens of thousands of libraries and third-party crates available to use in Rust programs, 
						most of which can be accessed through Rust's third-party crate repository crates.io

					Crates used in the programming exercises:

						- std : the Rust standart library
							- std::collections  - Definitions forr collection types, such as (HashMap)
							- std::env  - Functions for working with your environment
							- std::fmt  - Functionality to control output format
							- std::fs  - Functions for working with file system
							- std::io  - Definitions and functionality for working with input/output
							- std::path  - Definitions and functions that support working with file system path data
						- structopt : a third-party crate for easily parsing command-line arguments
						- chrono : a third-party crate to handle date and time data
						- regex : a third-party crate to work with regular expressions
						- serde : a third-party crate of serialization and deserialization operations for Rust data structures

					By default, the std library is available to all Rust crates
					To access reusable code in a crate or library, we implement the (use) keyword. 
					With the (use) keyword, the code in the crate or library is "brought into scope" so you can acess the definitions and functions in your program
					The standart library is accessed in (use) statements with path (std) as in  (use std::fmt). 
					Other crates or libraries are accessed with their name, such as (use regex::Regex).

	- Create and manage projects with Cargo
			While it's possible to use the Rust compiler (rustc) directly to build crates, most projects use the Rust buildtool and dependency manager called Cargo

			Cargo doings include:
				- create new project templates with the (cargo new) command
				- build a project with the (cargo build) command
				- build and run a project with the (cargo run) command
				- test a project with the (cargo test) command
				- check project types with the (cargo check) command
				- buil documentation for a project with the (cargo doc) command
				- publish a library to crates.io with (cargo publish) command
				- add dependent crates to a project by adding the crate name to the Cargo.toml file

	- When to use Rust
			- Rust allows for control over the performance and resource consumption of programs and libraries written in the language on par with C and C++, 
			while still being memory safe by default. 
			This level of control eliminates entire classes of common bugs.
			- Rust has rich abstraction features that allow developers to encode many of the invariants of their program into code.
			The code is then checked by the compiler instead of relying onconvention or documentation.
			This feature can often lead to the feeling of "if it compiles, it works"
			- Rust has built-in tools for building, testing, documenting and sharing code as well as a rich ecosystem of third-party tools and libraries. 
			These tools can make some tsks that are difficult in some languages, such as building dependencies, easy and productive in Rust

	- Check your knowledge
			1- What's a compelling advantage of working with Rust :
			letter A - Rust is type-safe, memory-safe and data race free
			2 - How is Rust code executed: 
			letter C - Through compilation followed by direct execution
			3 - What's an example of something you can't do with Cargo:
			letter B - Update the installed Rust compiler version

3- The Rust playground

		The playground is an IDE for Rust development that's available on the internet at https://play.rust-lang.org/
		You can write your code, and then compile and run your code in the same environment.
		In the playground, you can accesses methods and functions in the Rust std standard library
		
		- Tools and features
				the Rust playground has several built-in tools and development features:

					- Format code: The Rustffmt tool formats code to follow official Rust styles.
					The tool adjust the code and aplies recommended indentation and spacinf between elements and operators
					- Test code: the Clippy tool checks for mistakes in the code. The tool runs lint tests on code to find errors and areas for improvement
					- Save code: as you work in the Rust playground, you code is saved automatically to the local storage for your browser.
					This feature makes it easy to recover your most recent work, specially if you happen to close your browser window
					- Share code: The Share feature creates a shareable GitHub gist for the code in the playground.
					You can save thos URL to access your code later.
					The URK loads the gist for your specific code into the playground.

							NOTE
							The local storage for a browser is a singleton resource.
							If you have more than one browser window open to the Rust playgroundand you're working on different code in each window,
							only your most recently saved code across all windows is persisted in the local storage
		
		- Build options
				
			- run : build and run your code and show the output.
			The Run option is the same as using the (cargo run) command

			- build : build your code but don't run the code. 
			The build option is the same as using the (cargo build) command

			- test :  build your code and run all the tests against the code.
			The test option is the same as using the (cargo test) command

		- Protection limits
				There are some limitations in the playground that protect the site from being used in a malicious manner.
				The restrictions help to ensure the site remains available for all users

					- network : when you compile or run code in the playground, a network connection isn't available

					- memory : the playground limits the available memory to compile code and run a built program

					- execution time : the playground sets a maximum amount of time to compile code and run a built program

					- disk : the amount of available disk space to compile code and run a built program is limited

		-Check your knowledge
				1- What Rust playground tool can you use to find mistakes in your code:
				letter B - Clippy
				2 - When is a network connection not available in the Rust playground: 
				letter C - When compiling code or running a program

4 - Exercise 

		- Connect to the Rust playground.
		- Enter the following code in the playground editor:
				fn main(){println!(Welcome to Rust!);}
		- Select Tools > Rustfmt to format the code
				The tool adjusts the code to follow official Rust styles
		- Select Tools > Clippy to check for mistakes in the code. The results are displayed under the editor
		- To fix the sample code, add quote marks around the text "Welcome to Rust!"
		- Now we'll compile the code and run the program.
		- To choose how to build and run the code in the playground, open the Run dropdown menu at the top of the UI
		- Select Run to build and execute the sample program. The program output is displayed under the editor
		- As you work in the playground, the code is automatically saved to the browser storage
		- If you close the browser window, you can lose the code that you entered
		- To make the code always available, you can create a shareable URL
		- Select the Share feature on the toolbar to create a GitHub gist for the code in the playground
		- Select the paper icon next to the text Permalink to the playground to get a shareable gist for the code
		- Now you can save the URL to access the code later, or share the URL for others to see the code

				- ANSWERS:
					
					https://play.rust-lang.org/?version=stable&mode=debug&edition=2021&gist=e6fd2b3922b07d6cef2e8d949a331150

					https://play.rust-lang.org/?version=stable&mode=debug&edition=2021&gist=d843033d988d5249d5583f877f0015be

5 - Summary

		In this module, you learned: 
			- Types of applications you can build by using the Rust programming language. 
			- Rust is useful for both low-level and high-level types of development.
			- Rust commands to work with your code. 
			- The (rustc) command is used to write and compile Rust programs.
			- The Rust Cargo feature and the module system for code organization. 
			- Use Cargo to create a new project, and build and run it.

		Try recipes in the Rust Cookbook

			The Rust Cookbook contains recipes for code that follows recommended practices for common programming tasks. 
			By following the recipes, you can learn how to work with commonly used crates in Rust. 
			The recipes cover a wide-range of topics, including processing text and numbers, working with databases, applying common algorithms, and debugging programs.

		References

			- [Rust std standard library] (https://doc.rust-lang.org/std/)
			- Rust crates.io library repository
			- Rust cookbook recipes
			- Rust playground help
			- Stack overflow developer survey of 2022