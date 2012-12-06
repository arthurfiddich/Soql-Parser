Soql Parser
===========

A parser/checker for Force.com SOQL syntax written in Ruby.

Dependencies
------------

 * Ruby
 * Gems
 * Treetop

Quick Start
-----------

	$ cd Soql-Parser

	$ irb

	1.9.3-p0 :001 > require './parser.rb'
	 => true

	1.9.3-p0 :002 > Parser.load
	 => #<SoqlParser:0x00000001c952b0 @consume_all_input=true>

	1.9.3-p0 :003 > Parser.parse 'SELECT Id FROM Opportunity WHERE Amount > 100000'
	 => SyntaxNode+Query0 offset=0, "...here amount > 100000" (select_clause,from_clause):
		...
