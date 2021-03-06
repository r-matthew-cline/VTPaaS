# Voice Translation Pipeline as a Service (VTPaaS)

VTPaaS is a RestAPI that allows developers to extend a single language text chatbot to a multi-lingual conversational interface. The service makes use of the Google-Cloud APIs for speech recognition, translation, and speech synthesis. The service can also be used for simple voice translation as well. VTPaaS currently supports 9 languages:

 - English
 - Spanish
 - German
 - Swedish
 - Turkish
 - Portugese
 - Japanese
 - French
 - Dutch

A demo of the application used with an English speaking Cleverbot instance can be found [here](https://vtpaas.clinetechnologysolutions.com/capture).

### Serverless Architecture
Originally the application was hosted on an AWS EC2 instance using a python backend to serve the API. To further reduce the cost of maintaining the API, and improve both the availability and scalability of the application, VTPaaS was migrated to a serverless architecture. The python backend was originally built using Flask so the transition was relatively smooth using the [Zappa](https://github.com/Miserlou/Zappa) utility.

Zappa interfaces with AWS and your python virtual environment to create AWS Lambda functions and an AWS API Gateway to serve the application. The biggest challenge when moving to Lambda functions was the fact that the original application relied on storing certain files to the local directory between certain API calls. Since Lambda storage is not persistant, this presented problems. This was a small problem, but was difficult to detect with the limited debugging capability through AWS's Cloud Monitor.

## API Definitions
//todo: define API standards
