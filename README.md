# serverless-thumbnail
Recreate the thumbnail service described here .. https://aws.amazon.com/blogs/compute/binary-support-for-api-integrations-with-amazon-api-gateway/ .. using the serverless.com framework (and document some gotchas).

From blog ...

https://aws.amazon.com/blogs/compute/binary-support-for-api-integrations-with-amazon-api-gateway/

http://forum.serverless.com/t/returning-binary-data-jpg-from-lambda-via-api-gateway/796

https://forums.aws.amazon.com/thread.jspa?threadID=243584&tstart=0


SLS Thumbnail - does NOT work
---

$ curl --request POST -H "Accept: image/png" -H "Content-Type: image/png" --data-binary "@demo.png" https://d7l4s1fx4d.execute-api.us-east-1.amazonaws.com/dev > thumb-sls.json

curl --request POST -H "Accept: image/png" --data-binary "@demo.png" https://d7l4s1fx4d.execute-api.us-east-1.amazonaws.com/dev > thumb-sls.json

(Accept header still goes through JSON conversion)

manually created prod stage (failed same reason)
---

$ curl --request POST -H "Accept: image/png" -H "Content-Type: image/png" --data-binary "@demo.png" https://d7l4s1fx4d.execute-api.us-east-1.amazonaws.com/prod > thumb-sls.json



From Blog - WORKS!
---

$ curl --request POST -H "Accept: image/png" -H "Content-Type: image/png" --data-binary "@demo.png" https://cftbm0oopk.execute-api.us-east-1.amazonaws.com/prod > thumb.png
