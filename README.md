## Account Factory

This code enables end-users to create AWS accounts and setup a custom base configuration quickly in an automated way. 


## Preapare Python executable Zip to execute into AWS Lambda
```
pip3 install --target ./package requests

cd ./package
zip ../AccountCreationLambda.zip .
zip AccountCreationLambda.zip AccountCreationLambda.py
```

To upload the dependency: https://docs.aws.amazon.com/lambda/latest/dg/python-package.html

## Update AWS Service Catalog after each change

1. Head to Us-east-1 (N. Virginia) https://us-east-1.console.aws.amazon.com/servicecatalog/home?region=us-east-1#portfolios?activeTab=localAdminPortfolios
2. Go to s3 `aws-avm-infrastructure-setup-sandboxInfo` and upload the updated files. 
3. Go to product `AccountBuilder` and click `Create new product version`
    - Choose `Specify a URL` and fill the input as `https://aws-avm-infrastructure-setup-sandbox.s3.amazonaws.com/accountbuilder.yml`
    - Bump the version and add a meaninfgul description
    - Deactivate the older version
4. Go to product `AccountBuilder` and launch the product to use. Product in this case is new AWS accounts.

## License Summary

This sample code is made available under a modified MIT license. See the LICENSE file.
