# Initial Setup

## Domain Whitelist

Open the AWS Connect instance setup page and go to `Application integration` tab then whitelist the following domains.
We recommend users to Approve the Updated Version's URL in Amazon Connect and add it to the installation parameters in Freshsales  

> Old Version  https://freshdeskccp.arta.sandeza.io \
> Updated Version https://d2crcltdyq83bm.cloudfront.net \
> https://d3h0owdjgzys62.cloudfront.net \
> Your freshsales URL **eg : https://sandeza-support.freshsales.com**

## Lambda Setup

### Adding layers

Select `layers` on the sidemenu and click `Create Layer` button

![create_layer](images/create_layerv2.png)

Download the layer files from <a href="https://lambda-layers-1h8d3.s3.ap-south-1.amazonaws.com/freshdesk-integration-layer.zip" target="_blank">S3 link</a>

<!-- ![layer_configuration](images/layer_configuration.png) -->

Fillout the fields as required and upload the ZIP file which downloaded before. Select `Node 12.x` as runtime and create the layer.

### Creating Lambda

Create new lambda function with basic execution permission with runtime `Node 12.x` and copy the code from the <a href="https://github.com/Sandeza/arta-freshdesk-integration-lambda" target="_blank">Github repo</a>.

> Note : Lambda and AWS Connect instance should be in same region

Add layers to lambda by selecting `Layers` under `Function Overview` tab and click `Add a layer` button as shown below

![add_layer](images/add_layerv2.png)

Select the layer which you have created before and the layer version then click Add button

![select_layer](images/select_layerv2.png)

Now the layer was added to lambda as shown below

![layer_added](images/layer_addedv2.png)

Add the environment variables as shown in below image

> Note : Include `https://` in beginning and don't include `/` at last

![env_variables](images/env_variables.png)

### Whitelist

Open the AWS Connect instance setup page and go to `Contact flows` tab and scroll to AWS Lambda and whitelist the created lambda and click the `Add Lambda Function` to add the lambda function with connect instance.

![env_variables](images/lambda_whitelistv2.png)

## Contact Flow setup

As Shown in the below image add lambda and set contact attribute block.

![contact_flow](images/contact_flow.png)

Open the lambda block and select the created lambda then change the Timeout to 8sec

![contact_flow](images/lambda_config.png)

Open the Set contact attribute block and give same Destination key and Attribute as `customerInfo` and type as `External`

> Note : Dont't change Destination key and Attribute value

![contact_flow](images/set_contact_attribute.png)
