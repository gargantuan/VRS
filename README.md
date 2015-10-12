# VRS
Validation Rule Sheets

### An open standard for creating and consuming validation rules for unser input. 

A validation rule sheet (VRS) is a document that provides groups of validation rules. These rules can be consumed by front and back-end applications to validate user input. Potential uses could include

1. Client side HTML Form input validations
2. Serverside user submitted input validation
3. PDF Form input validation
4. iPhone App user input validation 

The proposed advantage of VRS over other solutions is that validation rules can be shared bewteen the front and back end. In addidtion, VRS is implmentation language agnostic.

### HTML Example

Given the following HTML Form

```
<form mehod="post" action="http://www.mysite.com/register" vrs="http://www.mysite.com/rules.vrs">
	<label>
		Email
		<input name="user_email" type="email" placeholder="your email" />
	</label>
	<label>
		Password
		<input name="user_password" type="password" />
	</label>
</form>
```

The corresponding VRS file may look like this:

	// rules.vrs

	#user_email {
		required: true;
		regex: \.+\@.+\..+\;
	}
	
	#user_password {
		required: true;
		must-contain: a-z;
		must-contain: A-Z;
		must-contain: 0-9;
		must-contain: SPECIAL_CHARS;
		min-length: 6;
	}
	
