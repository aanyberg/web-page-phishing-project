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


## Questions

<ul>
  <li>What SQL code would you write to query all of the data contained in the provided dataset?<li>
  <li>Which field(s) has/have the strongest correlation with the “phishing” field?  Which field(s) has/have the weakest correlation with the “phishing” field?</li>
  <li>Would you say that the URL length is a strong indicator of whether or not the URL is phishing?  Why or why not?  What metrics do you have to support your answer?</li>
  <li>Would you say the number of redirections is a strong indicator of whether or not the URL is phishing?  Why or why not?  What metrics do you have to support your answer?</li>
  <li>Based on your analysis, what advice would you give to others for deciphering whether or not a URL is phishing?</li>
</ul>

## SQL Query
```
SELECT



## Contributing

Guidelines on how others can contribute to your project.

## License

Information about the license of your project.