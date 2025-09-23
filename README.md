# WebCal

A very simple CalDAV and iCal compatible calendar application.

## Features

- **CalDAV support:** Display events from any CalDAV server.
- **iCal support:** Display events from aniCal feed.  
- **Multiple calendars:** Add, edit, enable/disable, and color-code multiple calendars.
- **Views:** Month, week, day, and agenda (list) views.
- **Event management:** Create, edit, and delete events (if your CalDAV server supports it).
- **Import/Export:** Import/export calendar configurations as JSON.
- **No required backend:** Runs in the browser; your credentials are never sent to a third-party server.
- **Built-in Proxy:** Built in proxy server to work around CORS issues.

## Usage

Run as a docker container:

```
docker run -p 8080:8080 rhyst/webcal
```

Navigate to `localhost:8080` to see the interface. All information is stored in the browser. When adding CalDav or iCal calendars you can optionally use the built in proxy. This is actually required for most calendar providers as the CORS settings are often quite restrictive. The proxy is built into the container so even in this case nothing is sent via a third party.

## Why

I want a calendar interface that supports the main open standards (caldav/ical). I don't want it to be tightly coupled to other applications. I don't want the UI to look completely ancient. For some reason this did not seem to exist so I have created this.

## Caveat

My experience suggests that CalDav and iCal implementations are rife with non standard behaviour so I will not pretend this is a completely comprehensive solution. It will probably not work for some providers and there are likely many cases that display/editing/creating of events will not work.

## Development

### Local Development

```bash
npm install
npm run proxy # Optional
npm run dev
```

Visit [http://localhost:8080](http://localhost:8080) in your browser.

### Production Build

```bash
npm run build
npm run preview
```

Visit [http://localhost:8080](http://localhost:8080) in your browser.

### Docker

```bash
docker build -t webcal .
docker run -p 8080:80 webcal
```

Visit [http://localhost:8080](http://localhost:8080) in your browser.

## Thanks

Thanks to [Full Calendar](https://fullcalendar.io/) which is basically the entire UI of this application.