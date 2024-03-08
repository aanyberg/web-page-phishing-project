# Web Phishing Attemps

 In this project, I have analyzed web page URL phishing data to determine which fields in 
 the URL suggest that URL may be phishing attemps.

 Dataset used: <a href="https://www.kaggle.com/datasets/danielfernandon/web-page-phishing-dataset?resource=download">Kaggle - Web Page Phishing Dataset</a>

 Simulated tables:
 ```
 web_page_fishing:
  unique_id
  url_length
  n_redirection
  phishing

phishing_dataset:
  unique_id
  n_dots
  n_hyphens
  n_underline
  n_slash
  n_questionmark
  n_equal
  n_at
  n_and
  n_exclamation
  n_space
  n_tilde
  n_comma
  n_plus
  n_asterisk
  n_hashtag
  n_dollar
  n_percent
```


## Q & A

<ul>
  <li><strong>Which field(s) has/have the strongest correlation with the “phishing” field?  Which field(s) has/have the weakest correlation with the “phishing” field?</strong></li>
  <p>- The fields that have the strongest correaltion to the phishing field is n_slash and url_length.</p>
  <li><strong>Would you say that the URL length is a strong indicator of whether or not the URL is phishing?  Why or why not?  What metrics do you have to support your answer?</strong></li>
  <p>- According to the supplied data there is a strong indicator that a longer URL would be phishing. Another factor is that a longer URL containing more slashes than normal would indicate a phishing attempt. This conclusion is based of off the correlation of these fields. The correlation between the "phishing" field and "n_slash" and "url_length" is 0.611472 and 0.430125 respectively. That being said, there could be phishing attempts with that uses a shorter URL with fewer slashes in it.</p>
  <li><strong>Would you say the number of redirections is a strong indicator of whether or not the URL is phishing?  Why or why not?  What metrics do you have to support your answer?</strong></li>
  <p>Based on the correlation data the indication is that there is next to no correlation between the phishing attempts and the number of redirections. The correlation between "phishing" and "n_redirection" is: -0.050822. This is a bit contraintuititve because one would expect more redirections with a phishing attempt to hide the end destination, based on this the redirects alone isn't a strong indicator of a phishing attempt.</p>
  <li><strong>Based on your analysis, what advice would you give to others for deciphering whether or not a URL is phishing?</strong></li>
  <p>My advice would be to not look at each of these factors in isolation, mainly because the amount of redirects in this data shows very low correlation between the phishing attempts and that the URLs in this data of longer nature, something that isn't always true. In my opinion there is a few other factors that should be considered, such as the existence of SSL certificates, spelling errors in the URL and the context in which the URL was received.</p>
</ul>

## SQL Query
The SQL code to query all information in the two simulated tables web_page_fishing and phishing_dataset.
```sql
SELECT
    wpf.unique_id,
    wpf.url_length,
    wpf.n_redirection,
    wpf.phishing,
    pd.unique_id,
    pd.n_dots,
    pd.n_hyphens,
    pd.n_underline,
    pd.n_slash,
    pd.n_questionmark,
    pd.n_equal,
    pd.n_at,
    pd.n_and,
    pd.n_exclamation,
    pd.n_space,
    pd.n_tilde,
    pd.n_comma,
    pd.n_plus,
    pd.n_asterisk,
    pd.n_hashtag,
    pd.n_dollar,
    pd.n_percent

FROM
    web_page_fishing as wpf
INNER JOIN
    phishing_dataset pd ON wpd.unique_id = pd.unique_id;
```

