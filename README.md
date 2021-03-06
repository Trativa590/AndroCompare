# AndroCompare - a tool to compare two Android Apps
AndroCompare is a tool which takes two Android Apps (.APK Files), compares them on a variety of factors and saves the resulting differences and similarities in a database.

This tool is extremely fast and can be used to do massive comparison of a large number of apps quickly. 
Two sample apps named app1.apk and app2.apk are provided. These apps have been compared and their results are saved in the database so that you can see how the results are organized.

Moreover if two apps have same package name but differ hugely in the number of permissions requested and the activities etc then there's a strong chance that one of them is repackaged. So, this tool can highlight the extra permissions/activities added to the repackaged version and consequently help in malware detection too.

## Features
It compares apps for differences in:
* permissions requested
* activities
* services
* broadcast receivers
* content providers
* apk size
* version name and code
* signing certificate

and saves the results in an organized way in a SQLite database. 


## Schema of Database
```
CREATE TABLE `APPS` (
	`app1_name`	TEXT,
	`app2_name`	TEXT,
	`app1_package`	TEXT,
	`app2_package`	TEXT,
	`app1_size`	TEXT,
	`app2_size`	TEXT,
	`app1_version_name`	TEXT,
	`app2_version_name`	TEXT,
	`app1_version_code`	TEXT,
	`app2_version_code`	TEXT,
	`perm_analysis`	TEXT,
	`perm_same`	TEXT,
	`perm_added`	TEXT,
	`perm_removed`	TEXT,
	`perm_add_count`	TEXT,
	`app1_cert`	TEXT,
	`app2_cert`	TEXT,
	`cert_diff`	TEXT,
	`app1_main_activity`	TEXT,
	`app2_main_activity`	TEXT,
	`main_activity_diff`	TEXT,
	`same_activities`	TEXT,
	`activities_added`	TEXT,
	`activities_removed`	TEXT,
	`same_services`	TEXT,
	`services_added`	TEXT,
	`services_removed`	TEXT,
	`same_receivers`	TEXT,
	`receivers_added`	TEXT,
	`receivers_removed`	TEXT,
	`same_providers`	TEXT,
	`providers_added`	TEXT,
	`providers_removed`	TEXT
);
```

----------------------------------------------------------------------------------------------------------------------------------------
## How to Run 
In the code file 'andro_compare.py', change the path variables to the apps to be compared: 
```
# change the paths to the relevant apps to be compared
apk1_path = "./app1.apk"
apk2_path = "./app2.apk"
```

Its written in Python 2.6 and currently supports Linux only. Moreover it uses the "hurry.filesize" module. So, install it using the following command

```pip install hurry.filesize```

You can use [DB Browser for SQLite](http://sqlitebrowser.org/) to view the database.


## Note
This tool is for research purposes only.

----------------------------------------------------------------------------------------------------------------------------------------

## Contact
You can get in touch with me on my LinkedIn Profile: [Haris Muneer](https://www.linkedin.com/in/harismuneer/)

## Issues
If you face any issue, you can create a new issue in the Issues Tab and I will be glad to help you out.

## License
[MIT](../master/LICENSE)
Copyright (c) 2018-present, harismuneer


