
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using TMPro;

    public class NumberWizard : MonoBehaviour {
    [SerializeField] int max;
    [SerializeField] int min;
    [SerializeField] TextMeshProUGUI GuessText;
    int guess;
    
    void Start () {
        StartGame();
	}
    
    void StartGame()
    {
        max = max + 1; //make sure 1000 is a guessable
        NextGuess();
    }
	
    public void PressHigh()
    {
        min = guess + 1; //make sure it will not guess an already guess number
        NextGuess();
    }
    public void PressLow()
    {
        max = guess;
        NextGuess();
    }
	
	
    void NextGuess()
    {
        guess = Random.Range(min, max); //make the guess become random
        GuessText.text = guess.ToString();
    }
}
