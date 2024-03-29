## Multilingual Model Training and Ensemble Approach

The approach adopted for model training and prediction in this project involves the use of a multilingual model, specifically XLM-RoBERT. The training data, originally in English, was converted into six different languages, languages which are present in the testing data. Subsequently, predictions were made on the test data for each of these six languages using the multilingual model.

## Monolingual Model Training

To further enhance the predictive performance, monolingual models were trained individually for each of the six languages present in the dataset. These monolingual models were trained using the training data(converted to that language) specific to each language. Additionally, soft labels were employed during the training process(for the test dataset for texts of that particular language)

## Iterative Refinement

The refinement process was carried out iteratively. After training the initial set of monolingual models, predictions were made for the test data using these models. The predictions were then combined with the predictions of the multilingual model in a weighted mean approach, which resulted in an enhanced set of predictions.

This iterative process was repeated until no further improvement in the predictions was observed. The main objective behind this approach was to continually refine and improve the predictive capabilities of the ensemble model.

## Final Prediction

The final prediction is a combination of the ensemble predictions from the multilingual XLM-RoBERT model and the ensemble predictions from the individually trained monolingual models. By taking the mean of these combined predictions, we achieve a balanced and robust final prediction, which encapsulates the collective insights from both multilingual and monolingual approaches.

This approach capitalizes on the strengths of both multilingual and monolingual models, resulting in a highly accurate and diverse predictive solution.

## Ensemble multilingual and monolingual Results

| Number of Repetition | AUC (Private) | AUC (Public) |
|----------------------|---------------|--------------|
| 0                    | 0.9449        | 0.9457       |
| 1                    | 0.9261        | 0.9283       |
| 1                    | 0.9459        | 0.9471       |
| 2                    | 0.9462        | 0.9477       |
| 3                    | 0.9474        | 0.9483       |

 

## References
- https://huggingface.co/models
