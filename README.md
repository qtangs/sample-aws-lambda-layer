# sample-aws-lambda-layer
Sample AWS Lambda Layer with Serverless Framework.

Complete guide: https://medium.com/@qtangs/creating-new-aws-lambda-layer-for-python-pandas-library-348b126e9f3e


# Initialize

    # Installing the serverless cli
    npm install -g serverless
    # Configure AWS profile (method 1 with AWS CLI)
    aws configure --profile <profile_name>
    # Configure AWS profile (method 2 with Serverless CLI)
    serverless config credentials --provider <profile_name> --key <access_key_id> --secret <secret_access_key>
    # Create a new working folder and set up subfolders
    mkdir serverless-with-layer
    cd serverless-with-layer
    mkdir -p layers/pandas

# Package

    pushd layers/pandas && ./get_layer_packages.sh && popd
    serverless package

# Deploy

    serverless deploy --package .serverless