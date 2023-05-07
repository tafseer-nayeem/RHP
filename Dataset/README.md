
The Review Helpfulness Prediction (RHP) dataset is hosted on 🤗 Hugging Face with train, validation, and test splits, which can be accessed using [this link](https://huggingface.co/datasets/tafseer-nayeem/review_helpfulness_prediction). The full dataset can be accessed using this [GDrive link](https://drive.google.com/file/d/1Hte0Ul0qyxR4n6NtBqokf9ZQc_n4n8rq/view?usp=sharing). 

### Dataset Summary

The success of e-commerce services is largely dependent on helpful reviews that aid customers in making informed purchasing decisions. However, some reviews may be spammy or biased, making it challenging to identify which ones are helpful. Current methods for identifying helpful reviews only focus on the review text, ignoring the importance of who posted the review and when it was posted. Additionally, helpfulness votes may be scarce for less popular products or recently submitted reviews. To address these challenges, the we introduce a dataset and task for review helpfulness prediction, incorporating the reviewers' attributes and review date, and build the dataset by scraping reviews from [TripAdvisor](https://www.tripadvisor.com/).


### Languages

English

## Dataset Structure

### Data Instances

One example from the `test` split of the dataset is given below in JSON format. 

```
    {
        "user_review_posted": 28,
        "user_total_helpful_votes": 78,
        "expertise": 0.013414038240254,
        "user_cities_visited": 89,
        "review_days": 0.39430449069003204,
        "helpful_class": 4,
        "review_text": "Had to see for myself. Over priced, bloviated, cheap. I am highly sensitive to mold, and it permeated the hotel. Sheets were damp, pipes blew hot air even when turned off. Considering all the hype, that's what this place is, all hype for too much money."
    }
```
### Data Fields

-  'user_review_posted': An integer representing the number of reviews posted by the reviewer.
-  'user_total_helpful_votes': An integer representing the cumulative helpful votes received by the reviewer.
-  'expertise': A normalized floating point number representing the mean number of helpful votes received per review.
-  'user_cities_visited': An integer representing the number of cities visited by the reviewer.
-  'review_days': A normalized floating point number representing the relative age of a review in days.
-  'helpful_class': An integer representing the degree of helpfulness of a review.
-  'review_text': A string representing the review.

### Data Splits

The following Table presents the summary of our dataset with train, validation, and test splits.

|                 | Train   | Valid  | Test  |
|:---------------:|---------|--------|-------|
| Total #Samples  | 145,381 |  8,080 | 8,080 |
| Avg. #Sentences |   7.82  |   7.8  |  7.81 |
| Avg. #Words     |  152.37 | 152.25 | 148.9 |

## Dataset Creation

We build our dataset by scraping reviews from [TripAdvisor](https://www.tripadvisor.com). Out of 225,664 reviews retrieved, close to one third have no helpful votes. We filter such reviews, and this reduces the number of reviews to 161,541. We leverage a logarithmic scale to categorize the reviews based on the number of votes received. Specifically, we map the number of votes into five intervals (i.e., [1,2), [2, 4), [4, 8), [8, 16), [16, infinity)), each corresponding to a helpfulness score of {1, 2, 3, 4, 5}, where the higher the score, the more helpful the review. More details can be found in our [EACL 2023](https://aclanthology.org/2023.findings-eacl.125/) paper.

### Discussion of Ethics

In our data scraping process, we took into account ethical considerations. We obtained data at an appropriate pace, avoiding any potential DDoS attacks.

### Known Limitations

Limitation of our dataset is that we only worked with reviews written in English. As a result, we filter out the reviews written in other languages and notice code-switched reviews when the reviewers alternate between two or more languages in a single review. 

## Additional Information

### Licensing Information

Contents of this repository are restricted to only non-commercial research purposes under the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/). Copyright of the dataset contents belongs to the original copyright holders.

### Citation Information

If you use any of the resources or it's relevant to your work, please cite [the paper](https://aclanthology.org/2023.findings-eacl.125/). 

```
@inproceedings{nayeem-rafiei-2023-role,
    title = "On the Role of Reviewer Expertise in Temporal Review Helpfulness Prediction",
    author = "Nayeem, Mir Tafseer  and
      Rafiei, Davood",
    booktitle = "Findings of the Association for Computational Linguistics: EACL 2023",
    month = may,
    year = "2023",
    address = "Dubrovnik, Croatia",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2023.findings-eacl.125",
    pages = "1684--1692",
    abstract = "Helpful reviews have been essential for the success of e-commerce services, as they help customers make quick purchase decisions and benefit the merchants in their sales. While many reviews are informative, others provide little value and may contain spam, excessive appraisal, or unexpected biases. With the large volume of reviews and their uneven quality, the problem of detecting helpful reviews has drawn much attention lately. Existing methods for identifying helpful reviews primarily focus on review text and ignore the two key factors of (1) who post the reviews and (2) when the reviews are posted. Moreover, the helpfulness votes suffer from scarcity for less popular products and recently submitted (a.k.a., cold-start) reviews. To address these challenges, we introduce a dataset and develop a model that integrates the reviewer{'}s expertise, derived from the past review history of the reviewers, and the temporal dynamics of the reviews to automatically assess review helpfulness. We conduct experiments on our dataset to demonstrate the effectiveness of incorporating these factors and report improved results compared to several well-established baselines.",
}
```