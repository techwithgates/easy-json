# Easy JSON
## Introduction
Easy JSON is an open source project that allows users to convert CSV files to JSON output. Easy JSON provides both JSON view and downloadable button so that users can choose either way to obtain the JSON data.<br><br>


## How to use?
1. Upload one or more CSV files

2. Click convert button

3. Click "View Data" that is below the file name

4. Use the "copy" and "download" buttons to obtain JSON data <br><br>


## How does it work?
The two arrays on the client side will be attached in a post request. The first array contains a list of file IDs and the second array contains a list of file objects. On the server side, Easy JSON will process the uploaded CSV files and will produce an array of object like structures that associates to the file IDs respectively. Easy JSON utilizes goroutine to concurrently process the request and it also applies wait group and mutex as well. Wait group is to simply wait for the goroutines to complete the job and mutex is to prevent data corruption, unexpeted data modfication or race condition in the goroutine. When the processing jobs are done, Easy JSON will send back a response that will be an array of objects where each object has a file ID and data attributes. <br><br>

## Demo
Note that the demo app is deployed on Vercel (free tier) and it has limitation when processing the uploaded files.

https://easy-json.vercel.app/ <br><br>

# License

This software is released under [MIT LICENSE](./LICENSE)