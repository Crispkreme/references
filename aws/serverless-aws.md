
## Create a S3 bucket
Terminal: `Ubuntu`  
Command:  
```sh

    # go to your aws account console
    # in the dashboard find the s3 in the search bar
    # create a bucket
    # go to bucket and select it to go the bucket details
    # go to the permission tags
    # unselect the block all access
    # update changes
    # go to bucket policy
    
    {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Effect": "Allow",
                "Principal": "*",
                "Action": "s3:GetObject",
                "Resource": "arn:aws:s3:::b479-ramos-s3-operations/*"
            }
        ]
    }

    # click the object/picture itself
    # then go to the properties
    # look for object url

    # Copying the objects
    


```

<!-- https://docs.aws.amazon.com/lambda/latest/dg/with-s3-example.html -->

## creating a trigger from lambda with s3 instance
- go to your aws account console
- look for lambda
- click the create a function button
- click Author from scratch
    - Function name =  anything
    - Runtime = Node.js 16x
    - Execution role = Create a new role from AWS policy templates
    - Role name = anything
    - Policy templates - optional
    - select Amazon S3 object read-only permissions from the dropdown
- click the create a function button
- go to the Code source 
- click the add trigger button
- then attach there your newly created s3 bucket earlier
    - Trigger configuration
    - s3
    - Bucket = <your_newly_created_bucket> 
    - check the <I_acknowledge_that_using_the_same_S3_bucket_for_both_input_and_output_is_not_recommended_and_that_this_configuration_can_cause_recursive_invocations,_increased_Lambda_usage,_and_increased_costs>
- then put this code inside the index.js

Terminal: `Ubuntu`  
Command:  
```sh

    console.log('Loading function');
    const aws = require('aws-sdk');
    const s3 = new aws.S3({ apiVersion : '2006-03-01' });

    exports.handler = async (event, context) => {

        const bucket = event.Records[0].s3.bucket.name;
        const key = decodeURIComponent(event.Records[0].s3.object.key.replace(/\+/g, ''));
        const params = {
            Bucket: bucket,
            Key: key
        };
        
        try {
            const { ContentType } = await s3.getObject(params).promise();
            console.log('CONTENT TYPE: ', ContentType);
            return ContentType;
        } catch (err) {
            console.log(err);
            const message = `Error getting object ${key} from bucket ${bucket}. Make sure the key and/or bucket is correct.`
            console.log(message);
            throw new Error(message)
        }

    }

```