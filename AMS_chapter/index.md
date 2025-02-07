---
title: Digital Innovation Graduate Chapter
layout: static_page_no_right_menu
permalink: /digital_grad_chapter/
nav_parent: Graduate
nav_nesting: true
nav_weight: 970
nav_id: Digital Innovation Graduate Chapter
---

### Digital Innovation Graduate Chapter

The mission of the DOGE University Graduate Digital Innovation Chapter is to foster excellence in digital technology, blockchain, and creative computing among our graduate community. Inspired by the rapid pace of digital transformation, our chapter brings together students and professionals to share innovative ideas, collaborate on projects, and organize events that drive progress in the digital realm.

To join our chapter and enjoy exclusive benefits such as subscriptions to our mailing list and access to special events, please fill out <a href="https://forms.gle/WRxuXZMt9JvpvvqAA">this form</a>. Membership is free!

### Executive Committee

The executive committee of the DOGE University Graduate Digital Innovation Chapter consists of:
<ul>
  <li>President: <a href="https://example.com/president">Alex Doe</a></li>
  <li>Vice President: <a href="https://example.com/vice-president">Jordan Smith</a></li>
  <li>Secretary: <a href="https://example.com/secretary">Taylor Lee</a></li>
  <li>Treasurer: <a href="https://example.com/treasurer">Riley Kim</a></li>
  <li>Member At Large: <a href="https://example.com/member">Casey Morgan</a></li>
</ul>
We welcome collaboration with similar digital innovation chapters from other institutions for joint events and initiatives!

### Calendar

<table class="table table-striped">
    <caption style="caption-side: top;"><a href="https://calendar.google.com/calendar/u/0/r?cid=c_60f1de561954223e1933f83f3bfb2520fd742ca85cbd6a02dade97379ec7fad3@group.calendar.google.com" rel="external noopener" target="_blank">Add to your calendar</a></caption>
    <tbody id="event-content">
        <tr class="font-weight-bold">
            <td>
                Loading calendar...
            </td>
        </tr>
    </tbody>
</table>

<script type="text/javascript">
    const API_KEY = 'AIzaSyA7Uka7Cbx7SPTWqDn52Nw9XPAe1kdQZxs';
    const DISCOVERY_DOC = 'https://www.googleapis.com/discovery/v1/apis/calendar/v3/rest';
    const CALENDAR_ID = 'c_60f1de561954223e1933f83f3bfb2520fd742ca85cbd6a02dade97379ec7fad3@group.calendar.google.com';


    function gapiLoaded() {
      gapi.load('client', initializeGapiClient);
    }

    async function initializeGapiClient() {
      try {
        await gapi.client.init({
          apiKey: API_KEY,
          discoveryDocs: [DISCOVERY_DOC],
        });
      } catch (err) {
        console.error(err.message)
        document.getElementById('event-content').innerHTML = `<tr class="font-weight-bold"><td>Failed to initialize calendar API</td></tr>`;
        return;
      }
      gapi.client.load('calendar', 'V3', listUpcomingEvents)
    }

    async function listUpcomingEvents() {
      let response;
      try {
        const request = {
          'calendarId': CALENDAR_ID,
          'timeMin': (new Date()).toISOString(),
          'showDeleted': false,
          'singleEvents': true,
          'maxResults': 5,
          'orderBy': 'startTime',
          'timeZone': 'America/New_York',
        };
        response = await gapi.client.calendar.events.list(request);
      } catch (err) {
        console.error(err.message)
        document.getElementById('event-content').innerHTML = `<tr class="font-weight-bold"><td>Failed to load calendar</td></tr>`;
        return;
      }

      const events = response.result.items;
      if (!events || events.length == 0) {
        document.getElementById('event-content').innerHTML = `<tr class="font-weight-bold"><td>No scheduled events</td></tr>`;
        return;
      }
      const dateFormatter = new Intl.DateTimeFormat("en-US", {weekday: "short", month:"short", day:"2-digit", year:"numeric"})
      const dateTimeFormatter = new Intl.DateTimeFormat("en-US", {weekday: "short", month:"short", day:"2-digit", year:"numeric", hour:"2-digit", minute:"2-digit", timeZone: 'America/New_York'})

      const output = events.map(
          (event) => `
            <tr>
                <td>
                  <a class="font-weight-bold" href=${event.htmlLink} rel="external noopener" target="_blank">
                    <time datetime=${(new Date(event.start.date ?? event.start.dateTime)).toISOString()}>${event.start.date ? dateFormatter.format(new Date(event.start.date)) : dateTimeFormatter.format(new Date(event.start.dateTime))}</time>
                  </a>
                  <h5>${event.summary}</h5>
                  ${event.location ? `${event.location}</br>` : ''}
                  ${event.description ? `<details style="white-space: pre-wrap;"><summary style="display: list-item">Details</summary>${event.description}</details>` : ''}
                </td>
            </tr>
          `).join('');
      document.getElementById('event-content').innerHTML = output;
    }

  </script>

<script async defer src="https://apis.google.com/js/api.js" onload="gapiLoaded()"></script>

### Digital Innovation Mission Statement

Our chapter is committed to advancing digital innovation through the promotion of interdisciplinary research and collaboration in areas such as blockchain, artificial intelligence, virtual reality, and creative coding. We strive to:
<ul>
  <li>Foster excellence in digital research and technology,</li>
  <li>Encourage collaboration between students, academia, and industry,</li>
  <li>Support professional development in emerging digital fields, and</li>
  <li>Enhance the impact of digital innovation on society.</li>
</ul>

Our goal is to create a vibrant intellectual and social community that drives the future of digital technology and transforms the landscape of digital innovation.
