# Hangman_guess
Bi-LSTM and Rule based approach to Hangman Guessing

This repository contains a Python-based solution to improve Hangman guessing strategies using Bi-LSTM models and vowel prior probabilities. The project leverages sequence models and multi-label classification to predict missing letters in partially revealed words within a fixed number of incorrect tries.

## Features
1. Bi-LSTM Model: Trains a bidirectional LSTM to predict missing letters based on encoded input sequences.
2. Vowel Prior Integration: Uses vowel probability priors for the first few predictions, improving accuracy in early guesses.
3. Custom Encoding: Input sequences encode letters as indices (1-26 for letters, 27 for underscores). Target vectors are 26-dimensional, representing the likelihood of each alphabet letter.
4. Masked Data Training: Handles scenarios where one or more letters are missing, with specific focus on one-missing-letter tasks.
5. Hybrid Strategy: Combines rule-based vowel guessing with data-driven Bi-LSTM predictions to maximize performance across different game setups.

## Approach
1. Data Encoding:
Input: Convert partially revealed words into encoded sequences, including underscores for unknown letters.
Output: Predict likelihoods for all possible letters (a-z).
2. Vowel Priors:
When incorrect tries are >4, prioritize guesses based on vowel probabilities.
3. Bi-LSTM:
Bidirectional LSTM processes sequences in both forward and backward directions to capture contextual dependencies.
Outputs letter probabilities, refined with Binary Cross Entropy Loss for multi-label classification.
4. Hybrid Guessing Strategy:
Start with vowel priors and transition to Bi-LSTM predictions for robust performance across all game stages.

## Results
1. One Missing Letter: High accuracy due to efficient masking and training strategies.
2. Multiple Missing Letters: Model performs sub-optimally (~20% accuracy), with scope for further improvement through enhanced sequence modeling.


