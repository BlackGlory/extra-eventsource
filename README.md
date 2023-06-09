# extra-sse
## Install
```sh
npm install --save extra-sse
# or
yarn add extra-sse
```

## API
```ts
interface IEvent {
  comment?: string
  event?: string
  data?: string
  id?: string
  retry?: number
}
```

### stringifyEvent
```ts
function stringifyEvent(event: IEvent): IterableIterator<string>
```

### fetchEvents
```ts
/**
 * @throws {HTTPClientError}
 * @throws {AbortError}
 */
function fetchEvents(
  input: string | URL | Getter<Request>
, options?: {
    lastEventId?: string

    autoReconnect?: boolean = true
    retry?: number = 0
  }
): AsyncIterableIterator<IEvent>
```
