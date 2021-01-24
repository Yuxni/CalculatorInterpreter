
Project: Calculator interpreter.

Under: OMEGA COURSE 2020.

By: Yuval Nissim 212909451.




User Manual: 
				To open the program run;
				1) Opening project's directory path in cmd.
				2) Running the command 'python main.py' to launch the UI.
				3) Enter mathematical expressions as input, to receive the calculation Results.
					
				when entered the programs run , a text interface will show up and you can interact with it.
				entering 'EXIT' to exit the program or enter an expression to calculate
					

Programmer Manual:
	
	How everything works; 
		
		-operators module: the operators module is responsible for all the operators defenition and rules ,
		it is based on a generic model to allow further implementation.
		
		Function class: the function object holds min and max allowed arguments along with the function reference the activation of the Function 
						 -Take note that the function reference takes an unknown number of arguments in order to increase generic use.
						 -Function objects are entirely generic and are easily mainpulated to obey different rules , you can define min and max allowed arguments,
						 but beware of changing the predefined constant count in each mathematical function implemented already they are there for logic and 
						 changes in them could bring Errors.
						 
					mathematical function: the mathematical functions are defined generically and input unknown amount of arguments using astrick tuple unpacking
			
		
		Operator class: is built from -a weight(i.e precedence in the expression),
									     -a Function class object reference(mentioned above - the function to be activated),
										 -a positional enum value from the POSITION class  ,
										 -(*optinal) edge case object reference or an iterable of it. 
										 
		operational positions: PREFIX, INFIX, POSTFIX
		
		EdgeCase class: built by a -enum value from the EdgeCasesNames class(i.e the name of the edgecase) , 
									-a new positional Enum value(the new positional operation the operator acts in)
									-a new Function object to be used.
						the solving algorithm checks if the edge case is supported and if it does it uses said function and operational positon 
		
	   
		-legal_chars module : responsible for the legality of each character inputted to the string and its classifcation
							  for supporting new characters you need to add shows there otherwise expression would be invalid
		
		 
	if you would like to add:
					- An new Operator: add a char key(if not legal add it to the operators set in legal_chars)
					  inside the Operator_dict dictionary and link it to a Operator Object with the set of rules fits your need(weight, function,position,edgecase)
					  
					  
					  # remember if you inserted something that is unsupported it will come up with a message telling you what and where is missing defeiniton
					  # although adding support would be quite easy.
					  
					- A new mathematical function : for the function to integrate in the program it needs to follow the generic rule set of the currently defined ones.
													i.e input an unkown amount of operands and unpack and handle them accordingly.
					  
					- A Position of the operator: define your wanted position name in the POSITION enum and in the solver implement a function to handle such operator position
					  and link it to the new  position enum key in the OPERATOR_POSITION_ON_LIST_DICT dictionary 
					
					  
					- A EdgeCase of the operator: define your wanted edgecase name in the EdgeCaseNames enum and in the solver implement a function to handle check such edge case
					  and link it to the new  EdgeCaseName enum key in the OPERATOR_EDGE_CASES_CHECK_DICT dictionary 
					
					
					- Another pair of brackets: define in matching index your opener and closer in the LEGAL_OPEN_PARENTHESES_SET and LEGAL_CLOSE_PARENTHESES_SET respctivly 
												and your brackets are now supported. mismatching brackets use in the expression will result in an exception 
					
					- A new legal character: add it in the classified sets it belongs to in legal.chars module
	


	Running pyTests:
					run the pyTest in calculator_tests configuration to run all the tests defined in said directory.
					includes :
							-simple equations
							-advanced equations
							-syntax errors equations
							
						
file list:
	-evaluator.py
	-exceptions.py
	-expression_list_validator.py
	-expression_string_validator.py
	-handler.py
	-input_handler.py
	-legal_chars.py
	-main.py
	-operators.py
	
	-test_advanced_expressions.py
	-test_simple_expressions.py
	-test_special_expressions.py
	-test_syntax_error_expressions.py


