% CASOS BASE
fib(0, 0).
fib(1, 1).

% Definir fibonacci
fib(X, N):- X1 is X-1, X2 is X-2, fib(X1, N1), fib(X2, N2), N is N1+N2.

% Querys
% fib(7, N): X = 13
