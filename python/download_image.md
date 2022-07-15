# Helper function: checks whether a list is consecutive

```python
def download_images(image_dict):
    # Download images from dict provided from xml stream
    downloaded_images = os.listdir('./images/jpegs')
    # download images from dict
    for image, url in image_dict.items():
        if image in downloaded_images:
            print('{} has already been downloaded- skipping'.format(image))
        else:
            try: 
                output_path = './images/jpegs/{}'.format(image)
                with open(output_path, 'wb') as handle:
                    response = requests.get(url, stream=True)

                    if not response.ok:
                        print(response)
                    
                    for block in response.iter_content(1024):
                        if not block:
                            break
                            
                        handle.write(block)
            except Exception as e:
                print('Error downloading {}: {}'.format(image, e))
```
