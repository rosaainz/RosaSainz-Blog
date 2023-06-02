---
title: "Order_whats"
date: 2023-05-31T23:00:06-06:00
draft: false
---

## Intro 
The project involves receiving an order via WhatsApp for a product and the system sending a message back with the quotation for the order.

## Inputs
Examples of the input:

{{< lead >}}
* 2 Berlinesas de Queso Mascarpone
* 2 Roles de Xoconostle
* 2 Croissants de Higo
* 2 Chocolatines
* 2 Rol de Almendra
* 4 Media Luna de Jamón y Queso
* 2 conchas vainilla ***
* 2 roles glaseados
{{< /lead >}}

{{< lead >}}
Buenos días, te doy mi pedido 😬😬😬
* 2 Berlinesas
* 2 roles de xoconostle 
* 2 chocolatines
* 1 rol de almendras 
* 4 medias luna 
* 3 roles glaseados
* 1 concha de vainilla **
{{< /lead >}}

## How did I start? 

To carry out this project, I initially had the idea of defining the entire program flow, database, etc. I started by defining it in the following way:
1. Declare a catalog where products with their prices are listed.
2. Define keywords to identify the start of an order if certain words are mentioned in the message, for example, "order," "I want this," etc.
3. Connect to WhatsApp using an API.
4. Identify the order using the keywords.
5. Once the message is obtained, identify the quantity and name of the product. This can be done by dividing the order into rows, then into words, and lemmatizing to unify the words. For example, if someone writes "conchitas," it should be treated as "conchas." Then, store the quantity with the corresponding product, possibly in a map.
6. Validate that those words exist in the catalog.
7. Retrieve the price from the catalog, multiply it by the quantity, and sum up each result to obtain the total.
8. Generate a message with the quotation and send it via WhatsApp to the same number from which the message was received.

## Problems

I wasn't sure how to start coding, so I began by doing lemmatization exercises. Essentially, I asked Chat GPT to provide me with exercises to understand lemmatization. I did a couple of exercises, but I didn't fully grasp how lemmatization worked.

I started by creating a simple code. I created a text file that contains products with their prices, and the code takes an order with the products listed exactly as they are in the catalog. It calculates the total amount by multiplying the quantity of requested items by the price and summing up those multiplications. This code worked only if the input was written in a specific format.

## Solutions

I was interested in lemmatization because I wanted to be able to receive messages in any format and have the program continue calculating the total. I was struggling with the lemmatization part because I didn't understand it well. That's when I reached out to my mentor, José Juan, and that's when everything clicked, haha! He told me to try typing `myers.diff("hola", "ola")` in the Python REPL and analyze the output.


{{< figure src="myers.png" alt="myers.diff" default="true" >}}


As you can see, the letters that remain are labeled with a 'k'. Here's more information: [https://pypi.org/project/myers/](https://pypi.org/project/myers/)

So, in my code, I implemented a comparison between each product in the message and each product in the catalog. I counted the occurrences of the letter 'k', and if it was above the average, then that product from the catalog would be used to calculate the total.

## Repo
Anyway,  I will be sharing the entire process through the repository: https://github.com/rosaainz/order_whatsapp

