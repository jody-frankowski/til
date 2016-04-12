# ACL mask

In unix systems acl allows one to add fine-grained permissions to files
and directories. One interesting bit in the acl system is the mask. To quote
the manpage: "The ACL_MASK entry denotes the maximum access rights that can be granted by entries of type ACL_USER, ACL_GROUP_OBJ, or ACL_GROUP."
Basically it defines an upper limit for the permissions of everyone except
the file owner and others in the traditional permission system. It is setup
that way so that acl unaware programs will be able to add or remove permissions
as expected. [This great serverfault answer](http://serverfault.com/questions/352783/why-does-chmod1-on-the-group-affect-the-acl-mask)
goes in greater details.
