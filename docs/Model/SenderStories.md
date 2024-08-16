# # SenderStories

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**media** | [**\OpenAPI\Client\Model\SendMediaMedia**](SendMediaMedia.md) |  | [optional]
**mime_type** | **string** | Mime type of media | [optional]
**caption** | **string** | Optional. Text caption under the media. | [optional]
**preview** | **string** | Optional. Base64 encoded preview of the media. In JPEG format. | [optional]
**width** | **int** | Width of the media in pixels | [optional]
**height** | **int** | Height of the media in pixels | [optional]
**contacts** | **string[]** | List of contacts to send the story to | [optional]
**background_color** | **string** | Background color of the story (ARGB) | [optional] [default to '#00000000']
**caption_color** | **string** | Caption color of the story (ARGB) | [optional] [default to '#FFFFFFFF']
**font_type** | **string** | Font style of the story | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
