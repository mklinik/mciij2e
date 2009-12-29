project(MiniJavaParser Java)

add_custom_command(
    OUTPUT
        TokenMgrError.java
        Token.java
        MiniJavaParserConstants.java
        JavaCharStream.java
        ParseException.java
        MiniJavaParser.java
        MiniJavaParserTokenManager.java
     COMMAND javacc ${PROJECT_SOURCE_DIR}/MiniJavaLexer.jj
     DEPENDS MiniJavaLexer.jj
     )

add_library(MiniJavaParser
    ${PROJECT_BINARY_DIR}/TokenMgrError.java
    ${PROJECT_BINARY_DIR}/Token.java
    ${PROJECT_BINARY_DIR}/MiniJavaParserConstants.java
    ${PROJECT_BINARY_DIR}/JavaCharStream.java
    ${PROJECT_BINARY_DIR}/ParseException.java
    ${PROJECT_BINARY_DIR}/MiniJavaParser.java
    ${PROJECT_BINARY_DIR}/MiniJavaParserTokenManager.java
    Main.java
    )
