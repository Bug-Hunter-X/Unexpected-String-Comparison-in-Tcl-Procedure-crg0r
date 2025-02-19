# Unexpected String Comparison in Tcl Procedure

This repository demonstrates a subtle bug in a Tcl procedure that arises from implicit string comparison. The `badproc` procedure uses `==` for comparison, which leads to unexpected behavior when the inputs are strings instead of numbers.

## Bug Description
The Tcl `==` operator performs string comparison, not numerical comparison. If you pass strings that happen to look like numbers, the comparison may not work as expected numerically.  The `bug.tcl` file illustrates this behavior.  The fix, demonstrated in `bugSolution.tcl`, provides an explicit numerical comparison using `expr`. 

## Solution
The solution uses the `expr` command to perform numerical comparison, ensuring that the procedure behaves correctly for both numeric and string inputs (when applicable).