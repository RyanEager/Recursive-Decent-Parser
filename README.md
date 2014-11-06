Recursive-Decent-Parser
=======================

A recursive descent parse for the grammar given below. The parse method is to take a purported expression in L(G), represented as a String, and return a parse tree for the string if it is in L(G). The parse tree is to be of class OrderedTree and its nodes are to be of class Token. Both of these classes have already been defined for you and are available on the class web site.
The grammar that you are to use has start symbol Expr and rules

       Expr -> Literal | Var | FCall | LetExpr | IfExpr
       Literal -> ListLiteral | SymbolLiteral
       ListLiteral -> [ {Literal} ]
       FCall -> FName ( {Expr} )
       FName -> UserFName | PrimFName
       LetExpr -> let {Def} Expr
       Def -> define Sig Expr
       Sig -> UserFName ( {Var} )
       IfExpr -> if Expr Expr Expr
       
Here the parentheses and brackets are terminal symbols; the braces and vertical bars are metasymbols. The grammar is appropriate for recursive descent parsing.
The symbols SymbolLiteral, Var, PrimFName and UserFName are preterminals. A Var is a string that begins with a capital letter. A SymbolLiteral is a string that begins with the backquote character `. A PrimFName is one of the strings car, cdr, or cons. A UserFunctionName is a string that begins with a lower-case letter, is not a PrimFName, and does not appear on the right-hand side of any rule. These constraints are enforced in the Token class.
