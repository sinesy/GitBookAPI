# Image File

## Convert a TIFF image to a JPEG image

**Syntax**

```javascript
utils.convertTifToJpg(Long tifDirId,String tifFileName,Long jpgDirId,String jpgFileName,Float compressionFactor);
```

**Details**

```
tifDirId - folder identifier, where the input TIFF imagefile is already stored 
tifFileName -TIFF image file name, stored in the folder identified by tifDirId 
jpgDirId- folder identifier, where the JPEG image will be saved 
jpgFileName- file name for the JPEG image to create 
compressionFactor- positive number <= 1.0, used to define the compression factor the JPEG image
```

## Scale a jpg image, using width & height



Create an image jpg file, starting from an already existing jpg image file and scale it, using a new width x height.

**Syntax**:

```
  utils.scaleJpgFile(
    Long srcJpgDirId,
    String srcJpgFileName,
    Long destDirId,
    String destFileName,
    Long maxWidth, 
    Long maxHeight
  );
```

| srcJpgDirId    | directory id where the already existing jpg image file has been stored |
| -------------- | ---------------------------------------------------------------------- |
| srcJpgFileName | already existing jpg file name                                         |
| destDirId      | directory id where creating a new scaled jpg image                     |
| destFileName   | jpg file name to create, generated starting from the source image      |
| maxWidth       | new image width                                                        |
| maxHeight      | new image height                                                       |



## Scale a jpg image, using a scale



Create an image jpg file, starting from an already existing jpg image file and scale it, using a scale to reduce/enlarge it.

**Syntax**:

```
  utils.scaleJpgFile(
    Long srcJpgDirId,
    String srcJpgFileName,
    Long destDirId,
    String destFileName,
    Double scale
  );
```

| srcJpgDirId    | directory id where the already existing jpg image file has been stored |
| -------------- | ---------------------------------------------------------------------- |
| srcJpgFileName | already existing jpg file name                                         |
| destDirId      | directory id where creating a new scaled jpg image                     |
| destFileName   | jpg file name to create, generated starting from the source image      |
| scale          | scale ratio                                                            |









