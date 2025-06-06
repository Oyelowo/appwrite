package main

import (
    "fmt"
    "github.com/appwrite/sdk-for-go/client"
    "github.com/appwrite/sdk-for-go/functions"
)

func main() {
    client := client.NewClient()

    client.SetEndpoint("https://<REGION>.cloud.appwrite.io/v1") // Your API Endpoint
    client.SetProject("<YOUR_PROJECT_ID>") // Your project ID
    client.SetKey("<YOUR_API_KEY>") // Your secret API key

    service := functions.NewFunctions(client)
    response, error := service.CreateDeployment(
        "<FUNCTION_ID>",
        file.NewInputFile("/path/to/file.png", "file.png"),
        false,
        functions.WithCreateDeploymentEntrypoint("<ENTRYPOINT>"),
        functions.WithCreateDeploymentCommands("<COMMANDS>"),
    )

    if error != nil {
        panic(error)
    }

    fmt.Println(response)
}
