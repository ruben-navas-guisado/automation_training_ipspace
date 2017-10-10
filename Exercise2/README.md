Define the problem (what do you want to report)
	Our NOC team needs a simple CSV report that contains the following information for every network device:
		- Hostname
		- FQDN
		- Image
		- Model
		- Serial #
		- Version

	For covering this need we are using an in-house inventory tool but we are facing the following limitations:
		- The tool is using perl scripts to run CLI commands get the information from the CLI outputs.
		- The tool does not support parallel execution so only 1 device is polled at a time. It takes more than 1 day having the information for all devices.
	
Figure out how to get the information from the network devices
	All the information needed is available in ios_facts so we need to create a simple playbook and put this info in a CSV file.

Define the report format
	The format of the report is very simple (we will use '|' as field separator and every column will match one of the fields we need).

Create and test the playbook that collects the information and generates the report
	We have tested it using some lab IOS devices and it works pretty well and FAST because of parallel execution.

Write documentation
	The following playbook is uploaded to Git repository:
		collect_ios_facts.yml
