# graphcool-too-long-root-token-name

## Reproduction

```sh
graphcool deploy
```

Leads to

```
Deploying to shared-eu-west-1 with target prod... !

ERROR: Whoops. Looks like an internal server error. Please contact us from the Console (https://console.graph.cool) or via email (support@graph.cool) and includ
e your Request ID: eu-west-1:system:cj9pfqm2423a901185n7d0mbh

{
  "data": {
    "push": null
  },
  "errors": [
    {
      "message": "Whoops. Looks like an internal server error. Please contact us from the Console (https://console.graph.cool) or via email (support@graph.cool)
 and include your Request ID: eu-west-1:system:cj9pfqm2423a901185n7d0mbh",
      "requestId": "eu-west-1:system:cj9pfqm2423a901185n7d0mbh",
      "path": [
        "push"
      ],
      "locations": [
        {
          "line": 2,
          "column": 9
        }
      ]
    }
  ],
  "status": 200
}
```

The reason is the too long name of the root token in `graphcool.yml`:

```yml
rootTokens:
- looooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooooongName
```
