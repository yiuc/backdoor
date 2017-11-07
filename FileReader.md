# File Reader
https://backdoor.sdslabs.co/challenges/FLREAD
We need to use the relative path to find the flag.
## Steps
1. in the main page you will see the folder list.
2. You can try to select `Parent Directory` and you will find the flag.php. When you select `flag.php` but it is blank page.
3. back to /FLREAD/app/viewer and click the `viewer.php`, you can use this **POST** function to read the file.
4. try to use the relative path to `../flag.php` but it show file unexist.
5. input `viewer.php` you will see the source code.
```
<?php

	if(isset($_POST['file']))
	{
		$file = $_POST['file'];
		$file = preg_replace('/\.\.\//', './', $file);

		$content = file_get_contents($file);

		if(isset($content))
			$content = "{$file} : No such file exists";

		$content = htmlspecialchars($content);

		echo "<pre>";
		echo $content;
		echo "</pre>";
		die;
	}
?>

<html>
	<head>
		<title>
			File Viewer
		</title>
	</head>
	<body>
		<div>
			<form>
				File: <input type = "text" name = "file"><br>
				<input type = "submit" value = "Read file">
			</form>
		</div>
	</body>
</html>
```
6. in the source, it do some regex check to exist the *../* funciton **../** will change to **./**,
7. so try `.../flat.php`
8. done
## Reference
http://openhighschoolcourses.org/mod/book/tool/print/index.php?id=12503
