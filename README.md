
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class NumberWizard : MonoBehaviour {
    int max;
    int min;
    int guess;
    // Use this for initialization
    void Start () {
        StartGame();

       
	}
    void StartGame()
    {
        max = 1000;
        min = 1;
        guess = 500;
        Debug.Log("Welcome to our NumberWz");
        Debug.Log("To get start, choose one number you like but");
        Debug.Log("The highest number you can pick is " + max);
        Debug.Log("And the lowest number you choose is " + min);
        Debug.Log("Tell me if your number is lower or higher than" + guess);
        Debug.Log("Push Up = Higher, Push Down = Lower, Enter = Correct");
        max = max + 1;
    }
	
	// Update is called once per frame
	void Update () {
        //detect when some arrow press down and been release
        if (Input.GetKeyDown(KeyCode.UpArrow))
         {
            Debug.Log("Higher then!");
            min = guess;
            NextGuess();
           
         }
   
        else if (Input.GetKeyDown(KeyCode.DownArrow))
        {
            Debug.Log("Lower down now!");
            max = guess;
            NextGuess();
        }
        
        else if (Input.GetKeyDown(KeyCode.Return))
        {
            Debug.Log("So that your number, eh!?");
            StartGame();
        }	
	}
    void NextGuess()
    {
        guess = (max + min) / 2;
        Debug.Log("Then our new guess is: " + guess);
    }
}
