% Funciones -----
miembro(X, [X|_]) :- !.
miembro(X, [_|T]) :- miembro(X, T).
longitud([], 0).
longitud([_|T], L) :- longitud(T, L1), L is L1+1.
concatena([], L, L).
concatena([X|L1], L2, [X|L3]) :- concatena(L1, L2, L3).
reverso([], []).
reverso([H|T], LR) :- reverso(T, R1), append(R1, [H], LR). 
palindromo(L) :- reverso(L, L).

% fibonacci lista
fib_lista(1, [0]) :- !.
fib_lista(2, [0, 1]) :- !.
fib_lista(N, Lista) :- N > 2, N1 is N - 1, fib_lista(N1, Lista1), reverso(Lista1, [U, P|_]), Siguiente is U + P,           % 3. Sumamos los dos últimos
    append(Lista1, [Siguiente], Lista).

% Querys -------
% miembro(6, [1, 2, 3, 4, 3, 6]): X= true
% longitud([1,2, 3, 4], L): L= 4
% concatena([1,2, 3, 4], [5, 6, 7], X): X= [1, 2, 3, 4, 5, 6, 7]
% reverso([1, 2, 3, 4, 5, 6, 7], R): X= [7, 6, 5, 4, 3, 2, 1]
% fib_lista(8, L): L= [0, 1, 1, 2, 3, 5, 8, 13]
% palindromo([1, 2, 3, 4, 5, 6, 5, 4, 3, 2, 1]): X= true
