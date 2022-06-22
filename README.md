# XSOAR-Email-Communication-v2

Email communication v2 is an upgraded and expanded version of the OOTB Email Communication pack. This package added capability to initiate and manage multiple email communication directly from the incident layout.
![image](https://user-images.githubusercontent.com/41276379/174926289-aa819163-3573-4776-bee5-185035ae2ace.png)

## Set it up
Go to About > Troubleshooting > Import the tar.gz file of this content pack

There are 3 required items for the content pack to work. You need to verify each items if the import was successful.
- Preprocessing rule
- Email thread layout
- Automation scripts

### Verify Preprocessing rule
Verify if Settings > Integrations > Pre-Process rules has this rule. The rule is used for getting reply email from user and link it to the working incident where the communication was originally initiated.
![image](https://user-images.githubusercontent.com/41276379/174940290-9a02f6f0-8fc0-4c72-848b-294defbf8e6f.png)

### Email thread layout
The pack includes a default layout *Email Thread v2*. Go to Settings > Objects Setup > Layout > Email Thread v2
![image](https://user-images.githubusercontent.com/41276379/174944744-dbea6d98-f901-42cc-b8ee-9756e36440cc.png)
The 1st tab of the layout (Email) is used to send/receive/view all email communications which are tied to current incident. In order to add this tab to other incident layout, follow these steps:
- Export the incident layout you want to add Email tab > you will get **layoutscontainer-<layoutname>.json** file
  ![image](https://user-images.githubusercontent.com/41276379/174945468-2a5c26d3-5def-4a97-8888-83ba5a31b235.png)

- Open the **layoutscontainer-<layoutname>.json** file, paste below JSON text after line 15
  ![image](https://user-images.githubusercontent.com/41276379/174946089-4f10f7df-29f1-430a-98ee-9499f60c54a2.png)

 ```
  			{
				"hidden": false,
				"id": "k8pjohtsgj",
				"name": "Email",
				"sections": [
					{
						"displayType": "ROW",
						"h": 7,
						"hideItemTitleOnlyOne": true,
						"hideName": true,
						"i": "k8pjohtsgj-caseinfoid-640beec0-e5f3-11ec-abd3-bb1df17fba5a",
						"items": [
							{
								"endCol": 4,
								"fieldId": "emailthreadhtml",
								"height": 44,
								"id": "7950e670-e7b3-11ec-a2f7-a3982abe66aa",
								"index": 0,
								"sectionItemType": "field",
								"startCol": 0
							}
						],
						"maxW": 3,
						"minH": 1,
						"moved": false,
						"name": "Email Thread",
						"static": false,
						"w": 2,
						"x": 0,
						"y": 0
					},
					{
						"displayType": "ROW",
						"h": 2,
						"hideItemTitleOnlyOne": false,
						"hideName": true,
						"i": "k8pjohtsgj-caseinfoid-5e8b0f50-e5f6-11ec-9898-299a6ea9e7f5",
						"items": [
							{
								"endCol": 2,
								"fieldId": "emailteam",
								"height": 22,
								"id": "ffdafd20-e5f6-11ec-9898-299a6ea9e7f5",
								"index": 0,
								"sectionItemType": "field",
								"startCol": 0
							},
							{
								"dropEffect": "move",
								"endCol": 2,
								"fieldId": "emailto",
								"height": 22,
								"id": "dd201be0-e5f5-11ec-9898-299a6ea9e7f5",
								"index": 1,
								"listId": "caseinfoid-c8209710-e5f5-11ec-9898-299a6ea9e7f5",
								"sectionItemType": "field",
								"startCol": 0
							},
							{
								"endCol": 2,
								"fieldId": "emailcc",
								"height": 22,
								"id": "e437e7a0-e5f5-11ec-9898-299a6ea9e7f5",
								"index": 2,
								"sectionItemType": "field",
								"startCol": 0
							},
							{
								"endCol": 2,
								"fieldId": "emailsubject",
								"height": 22,
								"id": "342cf8d0-e782-11ec-bd5d-ab77a49b0d99",
								"index": 3,
								"sectionItemType": "field",
								"startCol": 0
							},
							{
								"dropEffect": "move",
								"endCol": 1,
								"fieldId": "incident_attachment",
								"height": 53,
								"id": "5f092691-e783-11ec-bd5d-ab77a49b0d99",
								"index": 4,
								"isVisible": true,
								"listId": "k8pjohtsgj-0e43a290-eb74-11ec-9c1e-07ae362942f5",
								"sectionItemType": "field",
								"startCol": 0
							},
							{
								"args": {
									"service_mail": {
										"simple": "hiep4hiep@innothings.vn"
									}
								},
								"buttonClass": "warning",
								"dropEffect": "move",
								"endCol": 2,
								"fieldId": "",
								"height": 44,
								"id": "3fa0c8a0-e5f6-11ec-9898-299a6ea9e7f5",
								"index": 4,
								"listId": "k8pjohtsgj-84372020-e783-11ec-bd5d-ab77a49b0d99",
								"name": "Send",
								"scriptId": "f34fda37-387d-4c06-805d-d0979ed0130b",
								"sectionItemType": "button",
								"startCol": 1
							}
						],
						"maxW": 3,
						"minH": 1,
						"moved": false,
						"name": "Email Editor",
						"static": false,
						"w": 1,
						"x": 2,
						"y": 1
					},
					{
						"displayType": "ROW",
						"h": 1,
						"hideName": false,
						"i": "k8pjohtsgj-84372020-e783-11ec-bd5d-ab77a49b0d99",
						"items": [
							{
								"endCol": 2,
								"fieldId": "emailtopic",
								"height": 22,
								"id": "cd55c330-e781-11ec-bd5d-ab77a49b0d99",
								"index": 0,
								"sectionItemType": "field",
								"startCol": 0
							}
						],
						"maxW": 3,
						"minH": 1,
						"moved": false,
						"name": "Email communication",
						"static": false,
						"w": 1,
						"x": 2,
						"y": 0
					},
					{
						"displayType": "ROW",
						"h": 4,
						"hideItemTitleOnlyOne": true,
						"hideName": false,
						"i": "k8pjohtsgj-0e43a290-eb74-11ec-9c1e-07ae362942f5",
						"items": [
							{
								"endCol": 2,
								"fieldId": "emaileditor",
								"height": 44,
								"id": "25e71e40-eb74-11ec-9c1e-07ae362942f5",
								"index": 1,
								"sectionItemType": "field",
								"startCol": 0
							}
						],
						"maxW": 3,
						"minH": 1,
						"moved": false,
						"name": "Email body",
						"static": false,
						"w": 1,
						"x": 2,
						"y": 3
					}
				],
				"showEmptyFields": true,
				"type": "custom"
			},
 ```
 - Last step is set input for the Send button on layout. Click Send button, fill in **email_from** field with the email you use to send email from XSOAR. 
  ![image](https://user-images.githubusercontent.com/41276379/174946562-7d2d26f1-9f76-4042-bb0c-989d085e181a.png)

	
### Automation Scripts
Verify these scripts are available in XSOAR
- EmailAskUserNew
- EmailAskUserResponseNew
- EmailSubjectChange
- EmailTeamSelect
- EmailTopicsDisplay
- EmailTopicsSelect
- EmailTopcsShow
- ProprocessEmailThread
- SendEmailThread
