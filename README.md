# PagefileMetadata

## What it does

This module allows to add media metadata information to FieldtypeFile fields using the PHP Library [getID3](https://github.com/JamesHeinrich/getID3) by James Heinrich. One of the motivations that lead to the development of this module was the need to know the aspect ratio of self-hosted mp4 videos in order to avoid layout shifting during rendering. However, this application is very specific and the metadata of individual formats are very different and its details can be used for many use cases.  

*getID3* is an open-source PHP library used for reading and analyzing metadata from various types of multimedia files, including audio, video, and image files. The library can extract a wide range of information, such as the title, artist, album, bitrate, playtime, resolution, and even technical details about the file's encoding and format. It supports a large number of formats, such as MP3, MP4, AVI, FLAC, OGG, and more.

## Features
- Analyse and store metadata information
- Fieldbased opt-in for FieldtypeFile files

## Install
1. Copy the module files to /site/modules/PagefileMetadata/
2. Run composer install in module directory.
   ```bash
   composer install
   ```

### Edit Field settings
`Fields` > `yourFieldtypeFile` > `Details`
Check the checkbox *Analyze and store metadata* to enable the feature for a specific field

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

## Todos
- Add process to regenerateMetadata