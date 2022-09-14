# Photoshop Script Save JPEG 
Saving multiple psd, jpeg file

### EN
You can select more than one psd and jpeg with the original name can be saved in the desired settings.

### TR
Birden fazla psd ve jpeg dosyalarını orjinal ismi ile istediğiniz ayalarda kaydedebilirsiniz.

#### Javascript　
```javascript
  // get all the files to process
 var inFolder = Folder.selectDialog("Please select folder to process");
 if (inFolder != null)
  {
    var fileList = inFolder.getFiles();
  }

// and then loop over the file list
for (var i = 0; i < fileList.length; i++)
{
    var doc = open(fileList[i]);
    var saveFolder = new Folder('/Users/safak/Desktop/New Folder'); //enter path for where you want the file saved

var docRef = activeDocument;
var fileName = docRef.name;
var doc= activeDocument
var jpgOptions = new JPEGSaveOptions();
jpgOptions.quality = 3; //enter number or create a variable to set quality
jpgOptions.embedColorProfile = true; 
jpgOptions.formatOptions = FormatOptions.STANDARDBASELINE;

//other options///////////////////////////
//jpgOptions.formatOptions = FormatOptions.PROGRESSIVE;
//jpgOptions.formatOptions = FormatOptions.OPTIMIZEDBASELINE;

if(jpgOptions.formatOptions == FormatOptions.PROGRESSIVE){

    jpgOptions.scans = 3}; //only used with Progressive

jpgOptions.matte = MatteType.NONE;

//jpgOptions.matte = MatteType.BACKGROUND;
//jpgOptions.matte = MatteType.BLACK;
//jpgOptions.matte = MatteType.FOREGROUND;
//jpgOptions.matte = MatteType.NETSCAPE;
//jpgOptions.matte = MatteType.SEMIGRAY;
//jpgOptions.matte = MatteType.WHITE;

doc.saveAs (new File(saveFolder +'/' + fileName), jpgOptions)}
```
