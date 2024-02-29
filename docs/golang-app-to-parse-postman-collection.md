# Write a Golang app to parse Postman Collection to return API Endpoint details

Whether you are an API Producer or Consumer, there’s a good chance you are using Postman API Client (given how popular it is). We are not going to discuss how to use Postman in this article as we already have a course published for it (and it costs less than $5) but what we’ll do here is take a quick look at one of the files in a repo that we at Snowpal will be shortly making public.

![](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F645f4f1e-5ccf-43bb-be5c-7a319528c04c_1588x752.png)

We needed a quick way to socialize our API Endpoints and since we have a number of APIs and 1000s of endpoints, sending Postman Collection links to our clients, though a viable option, did not scale. Sometimes, we needed to socialize just the endpoint routes and not every aspect of those endpoints.

So, we wrote a simple app in Golang to take care of this.

You can run the app by feeding it Postman Collection JSONs,  filter by HTTP Verb and choose to write just the title, description, URL or all of it to a local file.

```
package main

import (
	"encoding/json"
	"fmt"
	"os"
	"postman/lib"
)

func main() {
	postmen := make([]lib.Root, 0)
	pwd, _ := os.Getwd()
	for _, file := range postmanSpecifications() {
		dat, _ := os.ReadFile(pwd + "/spec/" + file)
		postman := lib.Root{}
		if err := json.Unmarshal(dat, &postman); err != nil {
			panic(err)
		}

		postmen = append(postmen, postman)
	}

	fo, err := os.Create(pwd + "/spec.md")
	if err != nil {
		panic(err)
	}

	// close fo on exit and check for its returned error
	defer func() {
		if err := fo.Close(); err != nil {
			panic(err)
		}
	}()

	endpointTitles := make([]string, 0)
	total := 0
	options := lib.Options{
		SkipDuplicates:     true,
		IncludeDescription: false,
		WriteTitles:        false,
		WriteUrls:          true,
	}
	for _, postman := range postmen {
		println(fmt.Sprintf("Writing endpoints for %s", postman.Info.Name))
		postman.WriteEndpoints(
                   []string{}, postman.Info.Name, "", &total, fo,
			&endpointTitles, options)
		println("Done \n")
	}
}

func postmanSpecifications() []string {
	return []string{
		"postman_building-blocks-api.json",
		"postman_content-management-api.json",
		"postman_project-management-api.json",
		"postman_conversation-api.json",
		"postman_classroom-api.json",
		"postman_go-status-api.json",
		"postman_custom-attribution-api.json",
		"postman_access-control-list-api.json",
	}
}
```

When you run the above app, it will produce the result below (in this case, we chose to write the URLs, for example). 

# Snowpal: Building Blocks API 
- (1) Dashboard.1.1: Get dashboard details (https://gateway.snowpal.com/dashboard/combined-responses) 
- (2) Dashboard.1.2: Get recently modified blocks and pods (https://gateway.snowpal.com/dashboard/recently-modified) 
- (3) Dashboard.1.3: Get unread count (https://gateway.snowpal.com/dashboard/unread-count) 
- (4) Dashboard.1.4: Get recently modified keys (https://gateway.snowpal.com/dashboard/recently-modified/keys) 
- (5) Dashboard.1.5: Get pods and tasks due shortly (https://gateway.snowpal.com/dashboard/due-shortly/pods-and-tasks) 
- (6) Dashboard.1.6: Get blocks due shortly (https://gateway.snowpal.com/dashboard/due-shortly/blocks) 
- (7) Dashboard.1.7: Get unread notifications (https://gateway.snowpal.com/dashboard/notifications/unread-status) 
- (8) Dashboard.1.8: Get unread conversations (https://gateway.snowpal.com/dashboard/conversations/unread-status) 
...

Now, this makes it much simpler to have a chat with a prospect and touch upon some of the endpoints to prove the value proposition of our APIs.
