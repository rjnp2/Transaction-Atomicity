### Field.unique_for_date¶
Set this to the name of a DateField or DateTimeField to require that this field be unique for the value of the date field.

For example, if you have a field title that has unique_for_date="pub_date", then Django wouldn’t allow the entry of two records with the same title and pub_date.

Note that if you set this to point to a DateTimeField, only the date portion of the field will be considered. Besides, when USE_TZ is True, the check will be performed in the current time zone at the time the object gets saved.

This is enforced by Model.validate_unique() during model validation but not at the database level. If any unique_for_date constraint involves fields that are not part of a ModelForm (for example, if one of the fields is listed in exclude or has editable=False), Model.validate_unique() will skip validation for that particular constraint.
