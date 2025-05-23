package main

import (
    "fmt"
    "github.com/appwrite/sdk-for-go/client"
    "github.com/appwrite/sdk-for-go/account"
)

func main() {
    client := client.NewClient()

    client.SetEndpoint("https://<REGION>.cloud.appwrite.io/v1") // Your API Endpoint
    client.SetProject("<YOUR_PROJECT_ID>") // Your project ID

    service := account.NewAccount(client)
    response, error := service.CreateOAuth2Token(
        "amazon",
        account.WithCreateOAuth2TokenSuccess("https://example.com"),
        account.WithCreateOAuth2TokenFailure("https://example.com"),
        account.WithCreateOAuth2TokenScopes([]interface{}{}),
    )

    if error != nil {
        panic(error)
    }

    fmt.Println(response)
}
