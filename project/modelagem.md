```javascript
project: {
	name: String,
	description: String,
	date_begin: Date,
	date_dream:	Date,
	date_end: Date,
	visible: Boolean,
	realocate: Boolean,
	expired: Boolean,
	visualizable_mod: Boolean,
	project_tags: [],
	goals:[
		{
			name: String,
			description: String,
			date_begin: Date,
			date_dream:	Date,
			date_end: Date,
			realocate: Boolean,
			expired: Boolean,
			date_realocate: Date,
			activities:[
				{
					name: String,
					description: String,
					date_begin: Date,
					date_dream:	Date,
					date_end: Date,
					realocate: Boolean,
					expired: Boolean,
					date_realocate: Date,
					comments:[
						{
							text: String,
							date_comment: Date.
							files:[
								{
									path: String,
									weight: Double,
									name: String
								}
							]
						}
					]
				}
			]
		}	
	],
	members_project: [
		{
			type_name : String,
			$ref : String,
			$id : ObjectId(),
			$db : String,
			notify:[
				{

				}
			]
		}
	]

}

user: {
	background_path: String,
	name: String,
	bio: String,
	date-register: Date,
	avatar-path: String,
	username: String,
	email: String,
	password: String,
	last-access: Timestamp,
	online: Boolean,
	disable: Boolean,
	hash-token: String,
	notify:[
		{

		}
	]
}

log_system: {
	date_log: Date,
	date_msg: String
}
```