# International Telephone Number Input Formatting w/ Masking P.O.C.
This example provides a proof of concept for various improvements requested in ticket [CFDIT-6977](https://rdcdigital.atlassian.net/browse/CFDIT-6977). It properly handles the following improvements:
- Leveraging the *Preferred countries* field in the Drupal backend to control which countries are configured in the country-selector dropdown
- Presetting the initial country format to use for a particular input (e.g. set via the *Initial country* field in the Drupal backend)
- Adapt input mask to varying phone number formats
    - The placeholder format is dynamically set via the *National mode* option in the [`intl-tel-input`](https://intl-tel-input.com/) JS plugin and set as the placeholder field
    - The lightweight, [`imask.js`](https://imask.js.org/) JS plugin is used to handle masking of the user-entered phone numbers.
- Hides country-selector dropdown if only one country is defined in both the *Initial country* and *Preferred countries* backend fields
- Added a couple CSS classes (e.g. `.force-dropdown` & `.disable-mask`) that may be added via the backend to the *Element CSS classes* field. (See examples for proper use-case.)

Several examples are given in `index.html` that should cater towards the various 'states'/requirements as outlined in the user story.

## If you would like to run the development environment:

1. Run `npm install` from project root directory.
2. Next, run `npm run dev` to begin the ***light-server*** lightweight static http server. (This server watches files for changes and triggers livereloads.)