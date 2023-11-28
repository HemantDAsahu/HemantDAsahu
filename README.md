- 👋event-manager-app/
|-- src/
|   |-- components/
|       |-- EventForm.js
|       |-- EventList.js
|   |-- App.js
|   |-- index.js
|-- public/
|   |-- index.html
|-- package.json
|-- README.md
src/components/EventForm.js
import React, { useState } from 'react';

const EventForm = ({ onEventCreate }) => {
  const [eventName, setEventName] = useState('');
  const [eventDate, setEventDate] = useState('');

  const handleEventCreate = () => {
    if (eventName && eventDate) {
      onEventCreate({ name: eventName, date: eventDate });
      setEventName('');
      setEventDate('');
    } else {
      alert('Please fill in all fields');
    }
  };

  return (
    <div>
      <h2>Create Event</h2>
      <label htmlFor="eventName">Event Name:</label>
      <input
        type="text"
        id="eventName"
        value={eventName}
        onChange={(e) => setEventName(e.target.value)}
        required
      />

      <label htmlFor="eventDate">Event Date:</label>
      <input
        type="date"
        id="eventDate"
        value={eventDate}
        onChange={(e) => setEventDate(e.target.value)}
        required
      />

      <button onClick={handleEventCreate}>Create Event</button>
    </div>
  );
};

export default EventForm;

src/components/EventList.js
import React from 'react';

const EventList = ({ events }) => {
  return (
    <div>
      <h2>Event List</h2>
      <ul>
        {events.map((event, index) => (
          <li key={index}>{`${event.name} - ${event.date}`}</li>
        ))}
      </ul>
    </div>
  );
};

export default EventList;
src/App.js
import React, { useState } from 'react';
import EventForm from './components/EventForm';
import EventList from './components/EventList';

const App = () => {
  const [events, setEvents] = useState([]);

  const handleEventCreate = (event) => {
    setEvents([...events, event]);
  };

  return (
    <div>
      <EventForm onEventCreate={handleEventCreate} />
      <EventList events={events} />
    </div>
  );
};

export default App;
src/index.js
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);


 Hi, I’m @HemantDAsahu
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
HemantDAsahu/HemantDAsahu is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
