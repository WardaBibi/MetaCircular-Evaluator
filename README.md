# MetaCircular-Evaluator
Our evaluator for Lisp will be implemented as a Lisp program. It may seem circular to think about evaluating Lisp programs using an evaluator that is itself implemented in Lisp. However, evaluation is a process, so it is appropriate to describe the evaluation process using Lisp, which, after all, is our tool for describing processes. An evaluator that is written in the same language that it evaluates is said to be metacircular.

The metacircular evaluator is essentially a Scheme formulation of the environment model of evaluation . Recall that the model has two basic parts:

To evaluate a combination (a compound expression other than a special form), evaluate the subexpressions and then apply the value of the operator subexpression to the values of the operand subexpressions.
To apply a compound procedure to a set of arguments, evaluate the body of the procedure in a new environment. To construct this environment, extend the environment part of the procedure object by a frame in which the formal parameters of the procedure are bound to the arguments to which the procedure is applied.
These two rules describe the essence of the evaluation process, a basic cycle in which expressions to be evaluated in environments are reduced to procedures to be applied to arguments, which in turn are reduced to new expressions to be evaluated in new environments, and so on, until we get down to symbols, whose values are looked up in the environment, and to primitive procedures, which are applied directly .This evaluation cycle will be embodied by the interplay between the two critical procedures in the evaluator, eval and apply.


<img width="514" alt="image" src="https://github.com/WardaBibi/MetaCircular-Evaluator/assets/101542862/e4455cf0-b5dc-4ce6-b1ca-e709449c1fe0">

    
