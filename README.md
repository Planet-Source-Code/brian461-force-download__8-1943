<div align="center">

## Force Download


</div>

### Description

If you are annoyed with pdf's that open in the browser as I am here is a way to force the user to be prompted to download a file. Changed the $filename directory to the directory that you have all of your pdf, doc, or other binary files. Then just make a call for the file. Example (downdload.php?file=myFile.pdf) and it will prompt the user to open the file for save it to disk.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[brian461](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/brian461.md)
**Level**          |Beginner
**User Rating**    |4.8 (19 globes from 4 users)
**Compatibility**  |PHP 4\.0, PHP 5\.0
**Category**       |[Files](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/files__8-2.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/brian461-force-download__8-1943/archive/master.zip)





### Source Code

```
<?php
if (isset($_GET['file'])) {
 $file = $_GET['file'];
	header("Content-Type: application/force-download\n");
	header("Content-Disposition: attachment; filename=$file");
	$filename = "/usr/local/apache2/htdocs/" . $file;
	$contents = fread(fopen($filename, "rb"), filesize($filename));
	echo $contents;
} else {
	echo "No file specified";
}
?>
```

