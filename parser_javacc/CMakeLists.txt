project(MiniJavaParser Java)

add_custom_command(
    MiniJavaCC
        generated/TokenMgrError.java
        generated/Token.java
        generated/MiniJavaParserConstants.java
        generated/JavaCharStream.java
        generated/ParseException.java
        generated/MiniJavaParser.java
        generated/MiniJavaParserTokenManager.java
     COMMAND javacc -OUTPUT_DIRECTORY=generated MiniJavaLexer.jj
     DEPENDS MiniJavaLexer.jj
     )
