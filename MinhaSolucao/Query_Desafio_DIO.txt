/*Exercicio 1*/
SELECT Nome, Ano FROM Filmes;

/*Exercicio 2*/
SELECT Nome, Ano, Duracao 
    FROM Filmes
    ORDER BY Ano ASC

/*Exercicio 3*/
SELECT Nome, Ano, Duracao  
    FROM Filmes
    WHERE Nome = 'De Volta para o Futuro';

/*Exercicio 4*/
SELECT Nome, Ano, Duracao  
    FROM Filmes
    WHERE Ano = 1997;

/*Exercicio 5*/
SELECT Nome, Ano, Duracao  
    FROM Filmes
    WHERE Ano > 2000;

/*Exercicio 6*/
SELECT Nome, Ano, Duracao  
    FROM Filmes
    WHERE Duracao > 100 AND Duracao < 150
    ORDER BY Duracao ASC;

/*Exercicio 7*/
SELECT Ano, COUNT(*) AS Quantidade
    FROM Filmes
    GROUP BY Ano
    ORDER BY Quantidade DESC;

/*Exercicio 8*/
SELECT * 
    FROM Atores
    WHERE Genero = 'M';

/*Exercicio 9*/
SELECT * 
    FROM Atores
    WHERE Genero = 'F'
    ORDER BY PrimeiroNome;

/*Exercicio 10*/
SELECT F.Nome, G.Genero
    FROM Filmes AS F
    JOIN FilmesGenero AS FG 
        ON F.Id = FG.IdFilme
    JOIN Generos AS G 
        ON FG.IdGenero = G.Id;

/*Exercicio 11*/
SELECT F.Nome, G.Genero
    FROM Filmes AS F
    JOIN FilmesGenero AS FG 
        ON F.Id = FG.IdFilme
    JOIN Generos AS G 
        ON FG.IdGenero = G.Id
    WHERE G.Genero = 'Mistério';

/*Exercicio 12*/
SELECT F.Nome, A.PrimeiroNome, A.UltimoNome, EF.Papel
    FROM Filmes AS F
    JOIN ElencoFilme AS EF 
        ON F.Id = EF.IdFilme
    JOIN Atores AS A 
        ON EF.IdAtor = A.Id;