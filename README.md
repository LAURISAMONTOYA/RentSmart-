RentSmart’s core functionality relies on classes such as House, Landlord, Tenant, and RentalApplication.

Person(Superclass)
Attributes:
name: String — Name of the user.
phone: String — Contact number of the user.
email: String — Email address for communication.
userId: int — Unique identifier for each user.
Methods:
getName(): String — Returns the name of the user.
getPhone(): String — Returns the phone number of the user.
getEmail(): String — Returns the email address of the user.
getUserId(): int — Returns the unique user ID.

Landlord (Subclass of User)
Attributes:
properties: List<Property> — A list of properties managed by the landlord.
Methods:
viewProperties(): void — Displays all properties managed by the landlord.
assignProperty(Tenant tenant, Property property): void — Assigns a property to a tenant.
Requirements
As a landlord, I must be able to view the full inventory of properties by size, number of bedrooms.
As a landlord, I must be able to assign properties to tenants or reassign once they move out.
As a Landlord, I must be able to view tenant maintenance requests.
As a Landlord, I must be able to assign maintenance requests to the janitor.
Manage the properties
Handle tenant move-ins
 As a Landlord I must be able to view the tenants assigned to each properties.
PublicUser (Subclass of User)
This class represents a public user who can view properties and submit rental applications.
Attributes:
Inherits all attributes from User.
Methods:
viewProperties(List<Property> properties): void — Displays all available properties.
submitRentalApplication(Property property, RentalApplication application): void — Submits a rental application for a specific property.
Tenant → Attributes ((name, phone etc..)
Attributes


Requirements
As a tenant, I must be able to pay my rent
As a tenant, I must be able to make maintenance requests.
As a tenant, I must be able to view my monthly fees or bills.
As a new applicant, I should be able to fill out a rental application and send it to the Landlord for review.
Property → Attributes ((address,propertyId,.)
Attributes
propertyId: int — Unique identifier for each property.
address: String — Full address of the property.
size: double — Size of the property in square feet or meters.
numBedrooms: int — Number of bedrooms in the property.
numBathrooms: int — Number of bathrooms in the property.
monthlyRent: double — Monthly rental price for the property.
availabilityStatus: boolean — Whether the property is available for rent or occupied.
restrictions: String[] — Any restrictions (e.g., no pets, no smoking).
Methods:
isAvailable(): boolean — Returns whether the property is available for rent.
markAsRented(): void — Marks the property as rented when assigned to a tenant.
markAsAvailable(): void — Marks the property as available when vacated.

Requirements
It should have all relevant details (price, size,restrictions,address etc)
I should see the availability status.
I should be able to fill rental application form if available

Rental Application → Attributes (Paper work,sign contract, upload documents?)
RentalApplication
Attributes:
applicationId: int — Unique identifier for each application.
applicantName: String — Name of the applicant (tenant).
applicantPhone: String — Contact number of the applicant.
applicantEmail: String — Email address for communication with the applicant.
selectedProperty: Property — The property that the applicant is applying for.
monthlyRentOffered: double — Monthly rent offered by landlord based on selected property.


Methods:
submitApplication(): void — Submits rental application to landlord for review.
