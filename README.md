# UML

```mermaid

classDiagram
    class Game{
        - readonly WordProvider 
        - readonly GameResult[] gameStats
        + Game()
        + void ShowMenu()
        - void StartGame()
        - void ShowGameStats
    }

    class WordProvider{
        - readonly List<string> words
        - readonly Random random
        + WordProvider()
        + String GetRandomWord()
        + string GetScrambledWord(string word)
    }

    class GameResult{
        + string Word 
        + double timeTaken
        + GameResult(string word, double timeTaken)
    }

    class Program{
        - _static_ void Main(string[] args)
    }

Program ..> Game
Game o--> WordProvider
Game o--> GameResult
