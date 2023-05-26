Story 1: In order to track wildlife sightings, as a user of the API, I need to manage animals.

Branch: animal-crud-actions

Acceptance Criteria

Create a resource for animal with the following information: common name and scientific binomial✅
Can see the data response of all the animals✅
Can create a new animal in the database✅
Can update an existing animal in the database
Can remove an animal entry in the database


Story 2: In order to track wildlife sightings, as a user of the API, I need to manage animal sightings.

Branch: sighting-crud-actions

Acceptance Criteria

Create a resource for animal sightings with the following information: latitude, longitude, date
Hint: An animal has_many sightings (rails g resource Sighting animal_id:integer ...)
Hint: Date is written in Active Record as yyyy-mm-dd (“2022-07-28")
Can create a new animal sighting in the database
Can update an existing animal sighting in the database
Can remove an animal sighting in the database
Story 3: In order to see the wildlife sightings, as a user of the API, I need to run reports on animal sightings.

Branch: animal-sightings-reports

Acceptance Criteria

Can see one animal with all its associated sightings
Hint: Checkout this example on how to include associated records
Can see all the all sightings during a given time period
Hint: Your controller can use a range to look like this:

class SightingsController < ApplicationController
  def index
    sightings = Sighting.where(date: params[:start_date]..params[:end_date])
    render json: sightings
  end
end


Hint: Be sure to add the start_date and end_date to what is permitted in your strong parameters method
Hint: Utilize the params section in Postman to ease the developer experience
Hint: Routes with params