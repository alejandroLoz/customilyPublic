# Customily Technical Test.

If you got to this point Congratulations! If you complete this task the job will be almost yours 💪

## Prerequisites
Before starting this test we recommend to have a minimum understanding of how Customily works.
- As you already went through the interview you should know the basics (what Customily is used for), now you should learn a bit about Customily's admin panel and [this video](https://www.youtube.com/watch?v=j6-fIL6bSTA) will help you out with that.
- Once that you have an understanding of what you can do with Customily's admin panel, you'll need to know how our javascript library ([customily.js](https://cdn.customily.com/customily.js)) works 
and we have a video for that as well 😊.Follow [this video](https://www.youtube.com/watch?v=nFA4rfmzXqk) that refers to [this example](https://cdn.customily.com/example.html) so you can learn how to use some of our library's function.

## Frontend Test
For this test you need to create a Javascript application that does what's listed below.
We encourage the use of Javascript and CSS frameworks and/or libraries, if the app runs on IE11 is definitly a plus.

The app should:
- Get all the products for the user `frontEndDev` via the API. Keep in mind that this is now shown or mentioned in the videos above.
The two calls that you need to make are exemplified in [this POSTMAN example](https://app.customily.com/CustomilyAPIExamples.postman_collection.json). 
Take into account that you'll need to authenticate first so you can properly call `GetProductsFromTo`

- List them as follows:

  - When viewed on desktop: a 2 x 4 grid with pagination 
  
    ![Desktop home](http://i.imgur.com/KAVLzbH.png)

  - When viewed on mobile: a single colum with infinite scrolling 
  
    ![Mobile home](https://i.imgur.com/PoDR0py.png)  
   
When the user clicks the `Try it` button, the app should take him to another page where:

  - He'll be able to see the personalization canvas for that product (you should call `engraver.setProduct(id)`)
  - He'll be able to see the input controls for text and fonts for that product. You should generate these controls on the fly.
    In order to generate these controls, you should read the product metadata.  You can obtain the product metadata with `engraver.currentProduct`, we only want to show the textfields and the dropdowns for the font options, so you can ignore everything else returned by said function.

      - To obtain the text id for the i'th position use, `engraver.currentProduct.preview.textsPreview[i].id`
      - To obtain the list for the font paths for the i'th position use `engraver.currentProduct.preview.textsPreview[i].fontsMap`<br /> <br />
:warning: *Make sure to strip the last bit of the fonts, in other words,instead of displaying <br/>`"Avenir Heavy-61ed8ee8-0bae-477d-9310-c248a4924613.otf"` , you should show : `"Avenir Heavy"`*

  - All the user interaction should be reflected in the canvas. (using `engraver.setText(id, line)` and `engraver.setFont(id, option)`)
  
  This is how it should look for desktop:
  ![Desktop pp](https://i.imgur.com/7Il9WwC.png)
  
  This is how it should look for mobile:
  ![Mobile pp](https://i.imgur.com/CMUrC4b.png)
  
  You should add a `Save` button to save the personalization entered by the user in the previously generated controls. When pressing the button all the data should be sent to the backend to be stored in a database.
  
## Backend test
For this test you need to create a simple backend on C#.NET with an endpoint that will receive the personalization data from the frontend and store it in any database of your choice! We should be able to retrieve the data on another endpoint by using the product id.
   
## Delivery
The solution should be uploaded to a GitHub private repository. Create a new repo on your GitHub account, create a branch named `Customily`, push the solution to that branch and invite me as a colaborator to that repo (`alejandroLoz`).

### With Docker (huge plus)
If you know `Docker`, you can use `Docker Compose` to run everything with a single `docker-compose up` command. If migrations for the database need to be executed for the app to run, they should be executed by `Docker` automatically.

### Without Docker
The solution should be run using `npm run test`. This should open a new window with the home page of the solution. Please let us know what database type you will use to properly test the app.
