# redux-raven-middleware

Redux middleware for sending error reports to Sentry through raven-js.

Will automatically send an error report upon encountering a Javascript error
on dispatching any action. redux-raven-middleware will pass in the error as
well as extra information such as the action that caused the error and the
entire Redux application state.

## RavenMiddleware(sentryDSN, sentryConfig)

Creates a Raven Middleware.

- sentryDSN -- string representing your Sentry instance.
- sentryConfig -- object that will be passed into Raven.config.

```js
import {applyMiddleware, createStore} from 'redux';
import RavenMiddleware from 'redux-raven-middleware';


const createStoreWithMiddleware = applyMiddleware(
  RavenMiddleware('my-sentry-dsn')
)(createStore);
```