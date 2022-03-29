# Customily full stack Challenge.

Congratulations for getting to this point! If you complete this task the job will be almost yours 💪

## Prerequisites
Before starting this test we recommend to have a minimum understanding of how Customily works.
- As you already went through the interview you should know the basics (what Customily is used for). 
- Now you will have to carefully read [our API documentation](https://help.customily.com/en/article/customily-preview-api) so you can have all the tools you need to complete this test

## Frontend Test
For this test you need to create a Javascript application that does what's listed below.
We encourage the use of Javascript frameworks such as (Angular,React or Vue).
It's **not** important for the interface to look exactly as shown below. **We won't be evaluating your graphic design skills**

### The app should:
1) Display the product passed by URL and generate the HTML controls (with its values) on the fly so the user can personalize the product.
A product can have any combination of:
- `text fields` 
- `text fonts selectors` 
- `text color selectors`, 
- `image selectors`  
- `image upload fields`.

For example

_Product 464c481b-65d8-4006-8151-c10846020e75: 2 textfields and 2 text font selectors_ ![alt text](https://i.imgur.com/9IUGt9th.png) 
_Product a67b5c68-ce51-4df6-bb94-990bfb2389b1: 1 textfiled, 1 font selector and 1 image selector_ ![alt text](https://i.imgur.com/IoHYHkxh.png) 
_Product a81a5ce9-d6fc-408a-b6d1-7a5c955b14a5: 1 textfield, 1 font selector and 1 text color selector_ ![alt text](https://i.imgur.com/BQ7nu46h.png) 
_Product c7f0ce84-8577-4fef-9c14-e17693278d9c: 1 image upload field_ ![alt text](https://i.imgur.com/5xhVlIqh.png) 


In order to generate these controls, you should read the product metadata. You can obtain the product metadata with `engraver.currentProduct`:
  - To obtain the text field id for the i'th position use, `engraver.currentProduct.preview.textsPreview[i].id`
  - To obtain the image fields id for the i'th position use, `engraver.currentProduct.preview.imagePlaceHoldersPreview[i].id`
  - To obtain the list for the font paths for the i'th position use `engraver.currentProduct.preview.textsPreview[i].fontsMap`
  - To obtain the list for the font colors for the i'th position use `engraver.currentProduct.preview.textsPreview[0].fontColorsMap`
  - To obtain the list for the image paths for the i'th position use `engraver.currentProduct.preview.imagePlaceHoldersPreview[i].dynamicImagesPath`

  - All the user interaction should be reflected in the canvas using: 
    - `engraver.setText(id, line)`
    - `engraver.setFont(id, option)`
    - `engraver.setFontColor(id, option)`
    - `engraver.setImage(imageId,image)` 
    - `engraver.setPresetImage(imageId,imageOption)`
  
 2) Save the personalization selected in each HTML control using a `save` button. When pressing the button all the data should be sent to the backend to be stored in a database (including the product picture the canvas was displaying at that moment).
  
## Backend test
For this test you need to create a simple backend on C#.NET core with 2 endpoints. One will receive the personalization data from the frontend, store it in a relational database (`Postgres` if possible). Another one to retrieve the personalization data saved previously as a json. You should use EF Code first and automatic migrations.

   
## Delivery
The solution should be uploaded to a GitHub private repository. Create a new repo on your GitHub account, create a branch named `Customily`, push the solution to that branch and invite me as a collaborator to that repo (`alejandroLoz`). The entire application should run using `Docker Compose`. If migrations for the database need to be executed for the app to run, they should be executed by `Docker` automatically. 

