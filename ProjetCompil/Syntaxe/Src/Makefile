# ----------------------------------------------------------------------------
# Makefile pour la passe 1
# 
# Compilation de la passe 1 : 
#    make
#
# Faire du menage (efface les fichiers generes) : 
#    make clean
#    
# ----------------------------------------------------------------------------

all : TestLex.class TestSynt.class 

TestLex.class : TestLex.java sym.java Lexical.java ErreurLexicale.java
	cd ../../..; javac -Xlint:unchecked ProjetCompil/Syntaxe/Src/*.java

parser.java sym.java : syntaxe.cup
	java -jar ../../Global/Bin/java-cup-11a.jar syntaxe.cup

Lexical.java : lexical.flex
	java -jar ../../Global/Bin/JFlex.jar lexical.flex

TestSynt.class : TestSynt.java parser.java ErreurSyntaxe.java
	cd ../../..; javac -Xlint:unchecked ProjetCompil/Syntaxe/Src/*.java

lextest-%: ../Test/%/*.cas 
	../Test/lextest $^

syntest-%: ../Test/%/*.cas
	../Test/syntest $^



clean :
	/bin/rm -f sym.java Lexical.java parser.java *.class

