# PagefileMetadata

## What it does

This module allows you to add media metadata information to FieldtypeFile fields. Under the hood it uses the PHP library [getID3](https://github.com/JamesHeinrich/getID3) by James Heinrich and stores the raw data in the fields' filedata property.

*getID3* is an open source PHP library for reading and analysing metadata from various types of multimedia files, including audio, video and image files. The library can extract a wide range of information such as title, artist, album, bitrate, playtime, resolution and even technical details about the file's encoding and format. It supports a wide range of formats including MP3, MP4, AVI, FLAC, OGG and more.

One of the motivations for developing this module was the need to know the aspect ratio of self-hosted mp4 videos in order to avoid layout shifts during rendering.

However, this use case is very specific and the idea of this module is to make the metadata accessible via simple apis. The module comes with some video specific functions like width, height, aspect and type.

## Features
- Analyse and store metadata information
- Field based opt-in for FieldtypeFile files

## Install
1. Copy the module files to /site/modules/PagefileMetadata/
2. Run composer install in module directory.
   ```bash
   composer install
   ```

### Edit Field settings
`Fields` > `yourFieldtypeFile` > `Details`
Check the checkbox *Enable analyze and store metadata* to enable the feature for a specific field

## API

### Returns full metadata as array
```php
/** @var array */
$file->metadata or $file->metadata()
```
 
A few video specific properties are available directly via function params
```php
/** @var int */
$file->metadata('width')

/** @var int */
$file->metadata('height')

/** @var int */
$file->metadata('aspect')
```

You can add your own custom parameters by hooking into ___getMetadata.

<img width="1534" alt="image" src="https://github.com/user-attachments/assets/2e0168a4-be18-4c6f-8825-646cc6692834">


## Todos
- Add process in backend to regenerateMetadata

## Feedback
If you have any feedback, please reach out to us at [code@neuerituale.com](mailto:code@neuerituale.com) or create an issue in the github projekt.
