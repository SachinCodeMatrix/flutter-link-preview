# link_preview

[Flutter plugin](https://pub.dev/packages/link_preview) for previewing links (such as title, description, image). This is a port of [Android](https://github.com/LeonardoCardoso/Android-Link-Preview) and [iOS](https://github.com/LeonardoCardoso/SwiftLinkPreview) library. For now, it is not recommended to use this plugin in production.

## Usage

```
Future<void> getLinks() async {
      await LinkPreview.getPreview('https://flutter.dev',
          onData: (PreviewResponse data) => _previewData(data),
          onError: (error) => _handleError(error));
  }

  _previewData(PreviewResponse previewResponse) {
    // Preview status can be `complete` (handle data) or `loading` (show loading indicator)
    if (previewResponse.status == PreviewStatus.complete) {
      print('Received status: ${previewResponse.status}');
      print('Received title: ${previewResponse.title}');
      print('Received description: ${previewResponse.description}');
      print('Received image: ${previewResponse.image}');
      print('Received url: ${previewResponse.url}');
      print('Received final url: ${previewResponse.finalUrl}');
      print('Received cannonical url: ${previewResponse.cannonicalUrl}');
      print('Received html code: ${previewResponse.htmlCode}');
      print('Received row: ${previewResponse.row}');      
    } else {
      print('Received status: ${previewResponse.status}');
    }
  }
  
  _handleError(error) {
    print('Received error: ${error.message}');
  }
```


