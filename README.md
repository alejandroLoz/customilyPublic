# Customily full stack Challenge.

Congratulations for getting to this point! If you complete this task the job will be almost yours 💪

## Prerequisites
Before starting this test we recommend to have a minimum understanding of how Customily works.
- As you already went through the interview you should know the basics (what Customily is used for). 
- Now you will have to carefuly read [our API documentation](https://help.customily.com/en/article/customily-preview-api) so you can have all the tools you need to complete this test

## Frontend Test
For this test you need to create a Javascript application that does what's listed below.
We encourage the use of Javascript and CSS frameworks and/or libraries.

The app should:
1) Display the product passed by URL and generate the HTML controls on the fly so the user can personalize the product

Take into account that a product can have fonts selectors, image selectors, text fields and image upload fields.
In order to generate these controls, you should read the product metadata. You can obtain the product metadata with `engraver.currentProduct`:
  - To obtain the text field id for the i'th position use, `engraver.currentProduct.preview.textsPreview[i].id`
  - To obtain the image fields id for the i'th position use, `engraver.currentProduct.preview.imagePlaceHoldersPreview[i].id`
  - To obtain the list for the font paths for the i'th position use `engraver.currentProduct.preview.textsPreview[i].fontsMap`
  - To obtain the list for the image paths for the i'th position use `engraver.currentProduct.preview.imagePlaceHoldersPreview[i].dynamicImagesPath`

  - All the user interaction should be reflected in the canvas. (using `engraver.setText(id, line)`,`engraver.setFont(id, option)`,`setImage(imageId,image)` and `setPresetImage(imageId,imageOption)`)
  
 2) Save the personalization entered in the HTML controls using a `save` button. When pressing the button all the data should be sent to the backend to be stored in a database (including the picture the canvas was displaying).
  
## Backend test
For this test you need to create a simple backend on C#.NET core with 2 endpoints. One will receive the personalization data from the frontend, store it in any database of your choice. Another one to retreive the personalization data saved previously as a json
   
## Delivery
The solution should be uploaded to a GitHub private repository. Create a new repo on your GitHub account, create a branch named `Customily`, push the solution to that branch and invite me as a colaborator to that repo (`alejandroLoz`). The application entire application should run using `Docker Compose`. If migrations for the database need to be executed for the app to run, they should be executed by `Docker` automatically. 

