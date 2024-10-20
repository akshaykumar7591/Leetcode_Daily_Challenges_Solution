class Solution {

    public boolean parseBoolExpr(String expression) {
        // Repeatedly simplify the expression by evaluating subexpressions
        while (expression.length() > 1) {
            int start = Math.max(
                expression.lastIndexOf('!'),
                Math.max(
                    expression.lastIndexOf('&'),
                    expression.lastIndexOf('|')
                )
            );
            int end = expression.indexOf(')', start);
            String subExpr = expression.substring(start, end + 1);
            char result = evaluateSubExpr(subExpr);
            expression = expression.substring(0, start) +
            result +
            expression.substring(end + 1);
        }
        return expression.charAt(0) == 't';
    }

    private char evaluateSubExpr(String subExpr) {
        // Extract the operator and the enclosed values
        char op = subExpr.charAt(0);
        String values = subExpr.substring(2, subExpr.length() - 1);
        // Apply logical operations based on the operator
        if (op == '!') return values.charAt(0) == 't' ? 'f' : 't';
        if (op == '&') return values.contains("f") ? 'f' : 't';
        if (op == '|') return values.contains("t") ? 't' : 'f';
        return 'f'; // This point should never be reached
    }
}
