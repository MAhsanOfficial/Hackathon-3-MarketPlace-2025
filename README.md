# Hackathon-3 Full Flash Market Place 2025:

## Front-end
Front-End-(UI) NextJS Is the Power Full technology in Front-end More faster page Loads​We using Some Libraries Like Tailwind CSS , ShadCN , and Responsive Design​*Key Features About UI!*​User Friendly Interface
Browsing for All Products design Responsive Layouts that work on both mobile and desktop Devices ​

### Essential Pages:
Home , Product Listing , Product Details , Cart and Checkout, Order-Conformation

## Sanity (Back-end)
Sanity-(CMS) Back-End Purpose ? Why Sanity CMS Serves as the Back-end , providing a flexible and real time content management system​Use Sanity To Manage The Product Data , Customer Records and Order information​As the Primary Database for the E-Commerce Store​Real time Updates to Reflects Stock Changes and order
Processing ​Real time Content Updates ​Custom Schemas add On My own Choice ​


## Third Party (API):
### 1)Configuring Environment Variables:
Begin by setting up your environment variables. If a .env.local file doesn't already exist in your project's root directory, create one. Then, add the following variables:


###  ShipEngine :​
Tracks and Updates Shipment Details , Enables assigning tracking shipment zones​

###  Payment Gateway:​
Processes Payments Securely, Support Cash On Delivery in Digital Plaforms Payments Like: (Stripe,EasyPaisa,JazzCash,etc)​

###  Notification Service /Order APIs:​
Use Services Like twillo or Firebase for SMS/Email notification about order Status​

## API Requirements​

### ​1)Product Management ​(API)​Endpoint Name : /product​Method : GET​Description : Fetch all availble products for sanity ​Respons.
Example:​[​{"id":1,"name":"product1","price":1000}​{"id":2,"name":"product2","price":2000}...​]
### 2) 2))Order Management​ (API)​Endpoint Name : /orders​Method : POST​Description : Create a New Order​Response.
Example:​{"order_id":332,"status":"Sucess","message":"​Order Created sucessfully"}​​
### 3)Shipment Management (API) Endpoint Name : /shipment​Method : GET​Description : Track The order Status Via – A thrid Party (API)​Response.
Example:​{"shipment_id":832 ,"order_id":544 ,"status":"In Transit", ​"expected_delivery_date":"17-01-2025"}



## API Integration and Import Data in Sanity 

### 1) Configuring Environment Variables:
Begin by setting up your environment variables. If a .env.local file doesn't already exist in your project's root directory, create one. Then, add the following variables:
 
NEXT_PUBLIC_SANITY_PROJECT_ID=your_project_id
NEXT_PUBLIC_SANITY_DATASET=production
SANITY_API_TOKEN=your_sanity_token

### 2) Fetching Sanity Project ID and API Token
#### Project ID
##### To find your Sanity project ID:
1)Log in to your Sanity account at https://www.sanity.io/manage
2. Select your project
3. In the project dashboard, you’ll see the project ID listed

### 3). Creating the Sanity Schema
Now, let’s create a schema for our products. In your Sanity schema folder (usually `sanity/schemaTypes`), create a new file called `product.ts`:
Then, update your `sanity/schemaTypes/index.ts` file to include the new product schema:

Now, let’s create a script to import data from an external API into Sanity. Create a new file `scripts/importSanityData.mjs` in your project root:

Now, let’s install the necessary packages. Run the following command in your terminal:
                                  npm install @sanity/client axios dotenv

To run the import script, we need to add a new script to our `package.json` file. Open your `package.json` and add the following to the `"scripts"` section:
                                   "import-data": "node scripts/importSanityData.mjs"
Now you can run the import script using:
                                   npm run import-data
### This script will fetch products from the FakeStoreAPI, upload any associated images to Sanity’s asset store, and then create new product documents in your Sanity dataset.

