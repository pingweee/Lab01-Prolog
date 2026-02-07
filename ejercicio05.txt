color(red).
color(blue).
color(yellow).
color(green).
% -------------------------
% Funcion adyacente
adjacent(Col1, Col2) :- color(Col1), color(Col2), Col1\=Col2.
%---------------------------
map(A, B, C, D, E) :-
    adjacent(A, B), adjacent(A, D), adjacent(A, E),
    adjacent(B, C), adjacent(B, D), adjacent(B, E),
    adjacent(C, D), adjacent(C, E),
    adjacent(D, E).

%--------------------------
% Querys
% map(A, B, C, D, E): A=C, C=red, B=blue, D=yellow, E=green.
