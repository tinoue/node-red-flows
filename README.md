# Backups of my node-red flow

## google-home-notifier

### Feature

- Requrires customized google-home-notifier: https://github.com/noelportugal/google-home-notifier/pull/44
- Supports volume level of notification.
- Supports audio url.
- Synchronize successive notification request.

### Installation

- Install node-red plug-in - node-red-contrib-credentials and node-red-contrib-semaphore.
- Import [google-home-notifier.json](./google-home-notifier/google-home-notifier.json) into node-red.
- Set "Google Home IP Address" if necessary.
- Open "google-home-notifier wrapper" then edit language and volume.

## talk-line-message

### Feature

- Talks line message by using goole-home-notifier.
- Supports audio message.

### Installation

- Import talk-line-message into node-red.
- Import google-home-notifier.json above.

### Installation

- Install node-red plug-in - node-red-contrib-credentials and node-red-contrib-hostip.
- Import [talk-line-message.json](./talk-line-message/talk-line-message.json) into node-red.
- Create /home/pi/.node-red/line_users.json. See [sample file](./talk-line-message/line_users.json.sample).

## License

MIT
