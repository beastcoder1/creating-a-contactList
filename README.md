# creating-a-contactList
# how to cretae a cxontactLIst using java
package mobile;

public class contact {
	private String Name;
	private String Number;
	public contact(String name, String number) {
		Name = name;
		Number = number;
	}
	public String getName() {
		return Name;
	}
	public String getNumber() {
		return Number;
	}
	public contact createContact(String name, String number) {
		return new contact(name, number);
	}
}

# second class
package mobile;
import java.util.*;
  public class contactList {
    private ArrayList<contact> myContacts;
	  private contact myNumber;
	  public boolean addContact(contact newContact) {
		if(findContact(newContact) < 0) {
			myContacts.add(newContact);
			System.out.println("contact " + newContact.getName() + " has been added.");
			return true;
		}
		System.out.println("contact already exist.");
		return false;
	}
	public boolean deleteContact(contact Contact) {
		int position = findContact(Contact);
		if(position >= 0) {
			this.myContacts.remove(position);
			return true;
		}
		System.out.println(Contact + " doesn't exist");
		return false;
	}
	public void printContactList() {
	}
	public boolean updateContact(contact oldContact, contact newContact) {
		int position = findContact(oldContact);
		if(position >= 0) {
			this.myContacts.set(position, newContact);
			return true;
		}
		System.out.println(oldContact + " doesnt exist");
		return false;
	}
	private int findContact(contact newContact) {
		int foundPosition = this.myContacts.indexOf(newContact);
		if(foundPosition >= 0)
			return foundPosition;
		return -1;
	}
	private int findContact(String contactName) {
		for(int i = 0; i <= this.myContacts.size(); i++) {
			contact Contact = this.myContacts.get(i); 
			if(Contact.getName() == contactName) {
				return i;
			}
		}
		System.out.println(contactName + " doesn not exist");
		return -1;
	}
	#the third class is your main class, it involves calling those methods in your contactlist class and using them in your main class. 
  #you can sort that out yourself

