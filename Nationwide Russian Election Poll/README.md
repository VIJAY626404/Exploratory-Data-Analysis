# Presidential Election Polls 2024 EDA

![Python](https://img.shields.io/badge/python-3.9-blue)
![Jupyter Notebook](https://img.shields.io/badge/jupyter%20notebook-%20orange)
![License](https://img.shields.io/badge/license-MIT-green)

## Overview

This project performs exploratory data analysis (EDA) on the Presidential Election Polls dataset from March 4, 2024, focusing on voter demographics, behaviors, and preferences.

## EDA Problems and Solutions

### 1. Demographic Analysis
- **Distribution of Voters by Age and Sex**

    ```python
    sns.histplot(data=df, x='age', hue='sex', multiple='stack')
    plt.title('Distribution of Voters by Age and Sex')
    plt.show()
    ```

- **Federal District vs. City Type**

    ```python
    sns.countplot(data=df, x='federal_district', hue='type_of_city')
    plt.title('Federal District vs. City Type')
    plt.xticks(rotation=45)
    plt.show()
    ```

### 2. Voting Behavior
- **Awareness of Election Date vs. Intention to Vote**

    ```python
    pd.crosstab(df['knows_election_date'], df['will_vote']).plot(kind='bar', stacked=True)
    plt.title('Awareness of Election Date vs. Intention to Vote')
    plt.show()
    ```

- **Voter Turnout Prediction by Demographics**

    ```python
    sns.countplot(data=df, x='will_vote', hue='sex')
    plt.title('Voter Turnout Prediction by Sex')
    plt.show()
    ```

### 3. Candidate Preferences
- **Candidate Popularity by Age Group**

    ```python
    sns.countplot(data=df, x='candidate', hue='age')
    plt.title('Candidate Popularity by Age Group')
    plt.xticks(rotation=45)
    plt.show()
    ```

- **Media Influence on Candidate Preference**

    ```python
    sns.countplot(data=df, x='candidate', hue='television_usage')
    plt.title('Candidate Preference vs. Television Usage')
    plt.xticks(rotation=45)
    plt.show()
    ```

### 4. Socioeconomic Factors
- **Income by Employment Status**

    ```python
    sns.boxplot(data=df, x='employment', y='income')
    plt.title('Income by Employment Status')
    plt.xticks(rotation=45)
    plt.show()
    ```

- **Income by Education Level**

    ```python
    sns.boxplot(data=df, x='education', y='income')
    plt.title('Income by Education Level')
    plt.xticks(rotation=45)
    plt.show()
    ```

### 5. Media Consumption
- **Television and Internet Usage by Age Group**

    ```python
    sns.countplot(data=df, x='television_usage', hue='age')
    plt.title('Television Usage by Age Group')
    plt.show()

    sns.countplot(data=df, x='internet_usage', hue='age')
    plt.title('Internet Usage by Age Group')
    plt.show()
    ```

- **Impact of Media Consumption on Election Awareness**

    ```python
    pd.crosstab(df['television_usage'], df['knows_election_date']).plot(kind='bar', stacked=True)
    plt.title('Television Usage vs. Awareness of Election Date')
    plt.show()
    ```

### 6. Weight Analysis
- **Impact of Weighting on Results**

    ```python
    df_weighted = df.copy()
    df_weighted['weighted_vote'] = df['will_vote'] * df['weight1']
    weighted_votes_distribution = df_weighted.groupby('candidate')['weighted_vote'].sum().reset_index()
    sns.barplot(data=weighted_votes_distribution, x='candidate', y='weighted_vote')
    plt.title('Weighted Vote Distribution by Candidate')
    plt.xticks(rotation=45)
    plt.show()
    ```

## Interactive Visualizations
For an enhanced interactive experience, consider exploring the visualizations in Plotly or Bokeh. Interactive plots can help in understanding complex relationships and making the analysis more engaging.

## License
This project is licensed under the MIT License.
## Contributing
Feel free to contribute to this project by submitting a pull request or opening an issue. Your suggestions and improvements are always welcome!
## Contact
For any questions, contact [vijaykumarshah1942@gmail.com](mailto:vijaykumarshah1942@gmail.com).



