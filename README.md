# UML

```mermaid

classDiagram
    Class Game{
        - readonly WordProvider 
        - readonly GameResult[] gameStats
        + Game()
        + void ShowMenu()
        - void StartGame()
        - void ShowGameStats
    }

    Class WordProvider{
        - readonly List<string> words
        - readonly Random random
        + WordProvider()
        + String GetRandomWord()
        + string GetScrambledWord(string word)
    }

    Class GameResult{
        + string Word {get;}
        + double timeTaken {get;}
        + GameResult(string word, double timeTaken)
    }

    Class Program{
        - static void Main(string[] args)
    }

Program --> Game
Game o--> WordProvider
Game o--> GameResult