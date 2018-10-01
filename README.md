
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
        guess = (max + min) / 2;
        GuessText.text = guess.ToString(); 
        max = max + 1;
    }
	
public void PressHigh()
    {
        min = guess;
        NextGuess();
    }
public void PressLow()
    {
        max = guess;
        NextGuess();
    }
	
	
void NextGuess()
    {
        guess = (max + min) / 2;
        GuessText.text = guess.ToString();
    }
}
