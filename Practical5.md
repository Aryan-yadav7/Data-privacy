## Practical: Anonymization Techniques

 ### Aim

 To study and understand different **data anonymization techniques**, including **k-anonymity, differential privacy, and data masking**, and understand how they can be applied to protect sensitive information in a real-world dataset.

 ### Theory

 Data anonymization is the process of modifying or removing personally identifiable information (PII) from a dataset so that individuals cannot easily be identified.

 Organizations often collect sensitive data such as names, addresses, phone numbers, medical records, salaries, and financial information. Before such data is shared for analysis or research, anonymization techniques can be applied to reduce privacy risks.

 The three techniques studied in this practical are:

 ### 1\. K-Anonymity

 **K-anonymity** protects individuals by making each record indistinguishable from at least `k − 1` other records with respect to selected identifying attributes.

 For example, consider the attributes:

 - Age
- Gender
- ZIP Code

 If `k = 3`, then at least three records should have the same combination of these quasi-identifiers.

 To achieve k-anonymity, data can be:

 - **Generalized** — replacing exact values with broader ranges.
- **Suppressed** — removing certain values.

 For example:

```
Age:       24 → 20–29
ZIP Code:  110001 → 110***
```

 Thus, the exact identity of an individual becomes more difficult to determine.

 ### 2\. Differential Privacy

 **Differential privacy** is a mathematical approach to protecting individual information when statistical results are released.

 Instead of releasing an exact statistic, such as:

```
Average salary = ₹60,000
```

 a controlled amount of random noise is added:

```
Private average salary ≈ ₹59,700
```

 The goal is that the result remains useful for analysis while making it difficult to determine whether a particular individual's information was included in the dataset.

 A parameter called **epsilon (ε)** controls the privacy level:

 - Smaller ε → stronger privacy and more noise.
- Larger ε → weaker privacy and less noise.

 Differential privacy is particularly useful when organizations need to publish statistical information without revealing information about individual records.

 ### 3\. Data Masking

 **Data masking** replaces all or part of sensitive information with other characters or values.

 For example:

```
Original Phone: 9876543210
Masked Phone:   XXXXXXX210
```

 or:

```
Original Email: rahul@example.com
Masked Email:   r****@example.com
```

 Masking is commonly used when sensitive data needs to remain available for testing, demonstrations, or limited internal use while reducing exposure of the original values.

 ## Procedure

 1. Select a dataset containing potentially sensitive information.
2. Identify the **direct identifiers**, such as name, phone number, and email address.
3. Identify **quasi-identifiers**, such as age, gender, and ZIP code, which could identify a person when combined.
4. Identify **sensitive attributes**, such as medical conditions or salary.
5. Apply **data masking** to hide portions of sensitive values.
6. Apply **k-anonymity** by generalizing or suppressing quasi-identifiers so that multiple records become indistinguishable.
7. Apply the concept of **differential privacy** by adding controlled noise to statistical results.
8. Compare the original information with the anonymized information.
9. Observe the trade-off between **privacy protection and data utility**.

 ## Observation

 The anonymization techniques modify data in different ways:

 | Technique | What it does |
| --- | --- |
| **K-Anonymity** | Makes records less distinguishable based on quasi-identifiers |
| **Differential Privacy** | Adds controlled randomness to statistical results |
| **Data Masking** | Hides all or part of sensitive values |

## Result

 The practical demonstrates that different anonymization techniques can be used to reduce the risk of identifying individuals in a dataset. **K-anonymity** protects against identification through combinations of attributes, **differential privacy** protects individuals when statistical information is released, and **data masking** hides sensitive portions of individual values.

 ## Conclusion

 Data anonymization is an important privacy-preserving technique for organizations that need to analyze or share data. No single technique is appropriate for every situation; the choice depends on the type of data, the intended use, and the required level of privacy.
