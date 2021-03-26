# SSA без phi-узлов

Речь идет о варианте SSA, где используются базовые блоки с аргументами, вместо phi-узлов. В результате получается простой функциональный язык ("Functional SSA" [1]), в котором переход (jump) к выполнению очередного блока можно рассматривать, как вызов хвостовой рекурсивной функции.

Один из первых вариантов функциональной формы SSA был реализован в компиляторе MLton. В сообщении [2] Matthew Fluet описывает историю создания промежуточного представления на основе SSA и критикует подход с phi-узлами. В первую очередь, можно согласиться с тем, что функциональная форма SSA оказывается проще для понимания. В этом отношении следует указать на замечательную лекцию по началам SSA от Frank Pfenning, где изложение начинается с варианта, где используются базовые блоки с аргументами [3].

Аргументы базовых блоков используются в представлении SIL компилятора Swift [4], в Cranelift [5] и LLVM MLIR. Некоторые преимущества подхода без phi-функций указаны в документе, описывающем представление LLVM MLIR [6].

В работе [7] имеется формализация данного подхода в контексте языка Haskell, а ее критику см. в работе [8].

## Источники

1. https://www.cs.purdue.edu/homes/suresh/papers/hosc08.pdf
1. http://mlton.org/pipermail/mlton/2007-February/029597.html
1. https://www.cs.cmu.edu/~rjsimmon/15411-f15/lec/10-ssa.pdf
1. https://github.com/apple/swift/blob/master/docs/SIL.rst
1. https://cranelift.readthedocs.io/en/latest/ir.html
1. https://mlir.llvm.org/docs/Rationale/Rationale/#block-arguments-vs-phi-nodes
1. https://www.microsoft.com/en-us/research/wp-content/uploads/2016/11/compiling-without-continuations.pdf
1. https://www.cs.purdue.edu/homes/rompf/papers/cong-icfp19.pdf
