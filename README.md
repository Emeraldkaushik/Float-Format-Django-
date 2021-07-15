# Float-Format-Django-


floatformat¶
When used without an argument, rounds a floating-point number to one decimal place – but only if there’s a decimal part to be displayed. For example:

value	Template	Output
34.23234	{{ value|floatformat }}	34.2
34.00000	{{ value|floatformat }}	34
34.26000	{{ value|floatformat }}	34.3
If used with a numeric integer argument, floatformat rounds a number to that many decimal places. For example:

value	Template	Output
34.23234	{{ value|floatformat:3 }}	34.232
34.00000	{{ value|floatformat:3 }}	34.000
34.26000	{{ value|floatformat:3 }}	34.260
Particularly useful is passing 0 (zero) as the argument which will round the float to the nearest integer.

value	Template	Output
34.23234	{{ value|floatformat:"0" }}	34
34.00000	{{ value|floatformat:"0" }}	34
39.56000	{{ value|floatformat:"0" }}	40
If the argument passed to floatformat is negative, it will round a number to that many decimal places – but only if there’s a decimal part to be displayed. For example:

value	Template	Output
34.23234	{{ value|floatformat:"-3" }}	34.232
34.00000	{{ value|floatformat:"-3" }}	34
34.26000	{{ value|floatformat:"-3" }}	34.260
If the argument passed to floatformat has the g suffix, it will force grouping by the THOUSAND_SEPARATOR for the active locale. For example, when the active locale is en (English):

value	Template	Output
34232.34	{{ value|floatformat:"2g" }}	34,232.34
34232.06	{{ value|floatformat:"g" }}	34,232.1
34232.00	{{ value|floatformat:"-3g" }}	34,232
