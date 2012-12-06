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
	  SyntaxNode+SelectClause0 offset=0, "select id" (select,space,field_list):
	    Identifier+Identifier0 offset=7, "id"
	  SyntaxNode+FromClause0 offset=9, " from opportunity" (space1,from,space2,identifier):
	    Identifier+Identifier0 offset=15, "opportunity"
	  SyntaxNode+WhereClause0 offset=26, "...here amount > 100000" (space1,where,space2,condition):
	    SyntaxNode+FieldBoundCondition0 offset=33, "amount > 100000" (identifier,field_bound_operator,literal):
	      Identifier+Identifier0 offset=33, "amount"
	      IntegerLiteral+IntegerLiteral0 offset=42, "100000"
