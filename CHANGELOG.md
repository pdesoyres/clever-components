---
kind: 🏠 Home
title: Changelog
---
# Clever Components changelog

## Unreleased (????-??-??)

...

## 7.4.0 (2021-10-14)

* `<cc-pricing-table>`: add new `temporality` type `1000-minutes`

## 7.3.0 (2021-10-07)

* `<cc-pricing-table>`: add `temporality` feature
* `<cc-pricing-product>`:
  * add `temporality` feature
  * add plans and features for Jenkins runner (hard coded in the smart definition)
* `<cc-pricing-product-consumption>`: fix plan name for non bytes with cc-pricing-product:add-plan event
* `<cc-input-text>`: fix tags underline

### For devs

* Add an env param to disable generating docs on each change

## 7.2.1 (2021-09-30)

* `<cc-jenkins-info>`: Update documentation URL

## 7.2.0 (2021-09-27)

* `<cc-addon-backups>`: Add support for PostgreSQL, MySQL, MongoDB, Redis and Jenkins add-ons.

## 7.1.0 (2021-09-15)

* `<cc-env-var-form>`: fix small issues in exposed-config smart definition
* `<cc-pricing-product-consumption>`:
  * consider empty number values as `0`
  * add `progressive` support
  * add support for users (non byte type) and `secability`
  * add support for Heptapod in smart definition

### For devs

* with-resize-observer: remove "resize-observer-polyfill" dependency
* `<cc-input-text>`: remove "clipboard-copy" dependency
* refactor: use `??` instead of `||` when it makes more sense
* refactor: try to use `?.` when it's a bit simpler
* i18n: use Intl.PluralRules instead of custom code
* refactor: move sub render methods `_renderFoo()` below the main `render()` method
* refactor: use code folding regions in CSS (especially for responsive with COMMON/BIG/SMALL modes)
* pricing:
  * fix tests for PricingConsumptionSimulator
  * rename and update documentation for PricingConsumptionSimulator
  * add `progressive` to PricingConsumptionSimulator
  * add `secability` to PricingConsumptionSimulator
* product: refactor data API extraction for consumption based products

## 7.0.0 (2021-09-03)

### ⚠️ BREAKING CHANGES

* Browser support updated (Safari >=14), see [browser support reference](https://github.com/CleverCloud/clever-components/blob/7.0.0/docs/references/browser-support.reference.md) for details (BREAKING CHANGE). 
* `<cc-pricing-product-cellar>`: delete component and replace it with a more generic component (BREAKING CHANGE)
* `<cc-pricing-table>`:
  * rename `items` to `plans` (BREAKING CHANGE)
  * replace `currencyCode` with `currency` in smart definition (BREAKING CHANGE)
* `<cc-pricing-product>`:
  * rename `items` to `plans` (BREAKING CHANGE)
  * replace `currencyCode` with `currency` in smart definition (BREAKING CHANGE)

### Components

* `<cc-beta>`: replace rem with em
* `<cc-button>`: replace rem with em
* `<cc-img>`: replace rem with em
* `<cc-input-number>`: replace rem with em
* `<cc-input-text>`: replace rem with em
* `<cc-loader>`: replace rem with em
* `<cc-toggle>`: replace rem with em
* `<cc-block>`: introduce a ribbon and a noHead property
* `<cc-zone>`:
  * add CSS custom properties to customize colors
  * replace rem with em
* `<cc-zone-input>`:
  * fix zone list sort
  * move `sortZones` out in a lib
* New components:
  * `<cc-pricing-product-consumption>` (with smart definition)
    * this is the replacement for `<cc-pricing-product-cellar>`, it works for Cellar, FS Bucket, Pulsar
  * `<cc-pricing-header>`
  * `<cc-pricing-estimation>`
  * `<cc-pricing-page>` (with smart definition)
  * `<cc-jenkins-info>` (with smart definition)

### For devs

* Replace `aws-sdk` with `@aws-sdk/s3-client` so we can stop relying on `s3cmd` for previews
  * You no longer need the `.clever-components-previews.s3cfg` but you will need env vars (see docs)

## 6.10.0 (2021-07-08)

* `<cc-toggle>`: add `--cc-text-transform` CSS custom property
* New component:
  * `<cc-pricing-product-cellar>` (with smart definition)

## 6.9.1 (2021-06-30)

* Release a `custom-elements.json` following the new CEM format on npm

## 6.9.0 (2021-06-30)

### For devs

* Replace WCA with OpenWC's CEM analyzer
  * This includes a few simplifications on how we write JSDoc

## 6.8.1 (2021-06-25)

* Improve display of `preview:list` task
* `events.js`:
  * removed the `options` parameter as it was not used anymore
  * add the possibility to provide a suffix instead of just being able to provide an event name => It gives the possibility to create a suffix with a `tagName:suffix` directly if needed
* Remove exports from package.json

## 6.8.0 (2021-06-01)

* Introduce new custom esbuild WDS plugin (experimental)
* `<cc-tile-status-codes>`: add smart definition
* `<cc-tile-requests>`: fix label position

## 6.7.2 (2021-05-22)

* Fix Leaflet ESM treeshaking (handle side effects)

## 6.7.1 (2021-05-21)

* Internalize leaflet.heat (and simpleheat) and transform them into ESM

## 6.7.0 (2021-05-20)

* `<cc-map>`: use leaflet from ESM source to improve treeshaking
* Update chart.js v2 => v3 (with ESM and treeshaking)

## 6.6.0 (2021-05-19)

* Add new custom ESLint rules to enforce conventions over translation files
* cc-toggle: remove padding when legend is empty
* Introduce new docs template/system for smart components
* `<cc-pricing-table>`:
  * replace `rem` with `em` units (it's a fix)
  * add action property (add/none)
* `<cc-pricing-product>`:
  * replace `rem` with `em` units (it's a fix)
  * add action property (add/none)
  * add head slot to override the whole head section

## 6.5.1 (2021-05-07)

* Fix: the new pricing components where not correctly packaged

## 6.5.0 (2021-05-07)

* `<cc-button>`: Add a circle form when in hide-text with an image
* New component:
  * `<cc-pricing-table>`
  * `<cc-pricing-product>` (with smart definition for add-ons and runtimes)

### For devs

* i18n: simplify formatter system and add JSDoc
* i18n: remove country flags (it makes no sense for a language)
* Update deps

## 6.4.0 (2021-04-21)

* Introduce a preview system
* `<cc-html-frame>`:
  * call `revokeObjectURL` when the component is disconnected
  * add `loading` feature
* `<cc-invoice>`: use `loading` feature from `<cc-html-frame>`

## 6.3.0 (2021-04-13)

* Introduce `defaultThemeStyles` with monospace font-family
* `<cc-invoice>`: adjust spacing around "Download PDF" for narrow mode
* `<cc-invoice-table>`: introduce a responsive system (big/small render modes)
* Update `@clevercloud/client` (new billing/payment API endpoints)

## 6.2.4 (2021-04-09)

* `<cc-input-number>`
  * When in controls mode and in a disabled state the buttons also appear in a disabled state
    with a slight opacity change
  * Fixed a bug that allowed to change the value of the input in controls mode
    when the component was in a readonly state
  * The buttons in controls mode now get the state of disabled when min or max value is reached
    (e.g: If we have a value of `0` and the min is `0` the `decrement` button will change to `disabled`. The same would
    happen  for the `increment` button if we had a value of `10` and a max of `10`)


## 6.2.3 (2021-04-01)

* `<cc-invoice-table>`: fix pending statuses

## 6.2.2 (2021-04-01)

* `<cc-invoice-table>`: change sort order to desc

## 6.2.1 (2021-04-01)

* `<cc-invoice-table>`: fix i18n for emission date

## 6.2.0 (2021-03-31)

* New components:
  * `<cc-html-frame>`
  * `<cc-invoice>` (with smart definition)
  * `<cc-invoice-list>` (with smart definition)
  * `<cc-invoice-table>`

## 6.1.0 (2021-03-25)

* New component:
  * `<cc-input-number>`

## 6.0.1 (2021-03-15)

* `<cc-addon-linked-apps>`: fix CSS alignment

## 6.0.0 (2021-03-15)

### ⚠️ BREAKING CHANGES

* `<cc-addon-linked-apps>`: use `<cc-zone>` instead of just zone name (BREAKING CHANGE)

### Components

* Add check on `apiConfig` in cc-env-var-form.smart-exposed-config
* `<cc-addon-linked-apps>`: add smart definition
* `<cc-env-var-form>`:
  * add env-var-addon context
  * add smart definition (env-var-addon)

## 5.6.0 (2021-03-09)

* Introduce smart components system
* Update @clevercloud/client
* Pin Node.js and npm versions with volta and update lock to v2
* Add smart definition for `<cc-env-var-form>` (exposed config)

## 5.5.0 (2021-01-27)

* New components:
  * `<cc-addon-redis-options>`
  * `<cc-addon-jenkins-options>`

* `<cc-addon-elasticsearch-options>`
  * Add encryption at rest option

* `cc-addon-encryption-at-rest-option` template
  * Drop documentation URL parameter

...

## 5.4.0 (2020-12-08)

* `<cc-addon-credentials>`
  * Add `"pulsar"` type
  * Add `"url"` credential type

### For devs

* Use `@web/rollup-plugin-import-meta-assets` for assets instead of `rollup-plugin-copy`
* Replace `assetUrl()` helper with raw `new URL('../asset.svg', import.meta.url).href`
* Move rollup configs to specific dir and rework plugin usage
* Introduce rollup-plugin-deps-manifest to list dependencies for CDN
* Add new npm script `components:build-cdn` to prepare files for CDN
* Add new npm script `components:publish-cdn` to published files to Cellar
* Add manual CSS to style not yet defined components (will be reworked and automated later)
* Add new npm script `components:build-cdn:versions-list` to update the list of available versions (published on CDN)
* Add Jenkinsfile to automate CDN publication on new tag

## 5.3.1 (2020-11-16)

* `<cc-tile-requests>`: fix broken display when value is 0

## 5.3.0 (2020-11-10)

* `<cc-zone-input>`: fix scrolling behaviour (again)

## 5.2.0 (2020-11-09)

* `<cc-zone-input>`: fix scrollIntoView behaviour
* `<cc-zone-input>`: center the map
* `<cc-map>`: fix race conditions on view-zoom update (and other attrs)

## 5.1.0 (2020-11-03)

* `<cc-zone-input>`: change default internal `view-zoom` to `1`

## 5.0.0 (2020-11-03)

### ⚠️ BREAKING CHANGES

* `<cc-map>`: rework the API to place markers with something more generic
* `<cc-heptapod-info>`:
  * rename `statistics` properties
  * set default display to `block`
  * remove max-width
  * rework `loading`/`skeleton` logic
* Remove `<cc-elasticsearch-options>`, replaced by `<cc-addon-elasticsearch-options>`
  * Merge many attrs/props into `options`

### Components

* New components:
  * `<cc-addon-option>`
  * `<cc-addon-option-form>`
  * `<cc-addon-elasticsearch-options>`
  * `<cc-addon-postgresql-options>`
  * `<cc-addon-mysql-options>`
  * `<cc-addon-mongodb-options>`
  * `<cc-map-marker-dot>`
  * `<cc-map-marker-server>`
  * `<cc-zone>`
  * `<cc-zone-input>`
* `<cc-header-app>`: add `zone` details
* `<cc-img>`: add CSS custom prop `--cc-img-fit` to customize object-fit (default is cover)
* `<cc-env-var-form>`: fix restart button margin
* `<cc-flex-gap>`: add `--cc-align-items` CSS property
* Rework the way we format bytes and use it in `<cc-heptapod-info>`, `<cc-tile-scalability>` and `<cc-addon-elasticsearch-options>`

### For devs

* Update @clevercloud/client to 7.0.0
* docs: add some details about properties/attributes in cc-example-component.js
* Replace cypress by web-test-runner (and fix a test)
* Add tests for `prepareNumberUnitFormatter()`, refine implementation and adapt tests
* Refactor:
  * `<cc-logsmap>`: absorb logic that was in `<cc-map>` and use `<cc-map-marker-dot>`
  * `<cc-map>`: simplify setters and remove useless country property in point object
  * `<cc-heptapod-info>`: fix small issues (lint, CSS, story, API...)

## 4.1.2 (2020-08-14)

### Components

* `<cc-heptapod-info>`: Fix heptapod about link href

## 4.1.1 (2020-08-13)

### Components

* `<cc-heptapod-info>`:
  * Fix price translations
  * Change default width from 500px to 600px

## 4.1.0 (2020-08-13)

### Components

* New component: `<cc-heptapod-info>`

## 4.0.0 (2020-07-16)

### ⚠️ BREAKING CHANGES

* We moved our internal build to rollup and changed the way we link to images from non-standard syntax to `import.meta.url`.
  * Depending on the way you bundle our components, you may need some config to support this.
* We removed the outter margin on `:host` of several components:
  * `<cc-toggle>`
  * `<cc-input-text>`
  * `<cc-button>`
* We renamed all `<env-var-*>` components to `<cc-env-var-*>`
* `<cc-button>`: always display text when `image` is used
* We removed `index.js`, if you were using it, you now need to import the components one by one with their direct paths

### Components

* You can now set objects and arrays via attributes (as JSON)
* New components:
  * `<cc-flex-gap>`
  * `<cc-tcp-redirection-form>`
  * `<cc-tcp-redirection>`
* `<cc-addon-admin>`: simplify i18n (fix #103)
* `<cc-block>`: align icon on top (flex-start)
* `<cc-button>`:
  * Add `waiting` state
  * Handle `delay=0`
  * Fix image height with new inner grid system
  * Fix JSDoc
  * Fix story doc
* `<cc-env-form>`: fix overflow pb with inner button focus rings
* `<cc-env-var-form>`: fix overflow behaviour with inner input focus rings
* `<cc-env-var-input>`: fix story data (was broken for ages...)
* `<cc-expand>`: fix spring effect
* `<cc-header-orga>`: fix vertical alignment
* `<cc-input-text>`:
  * Adjust tag border-radius
  * Display placeholders in italics
  * Fix undefined behaviour
  * Force white background
* `<cc-link>`: fix lint issue
* `<cc-toggle>`:
  * Add multiple mode (with checkboxes)
  * Add color story and rework examples
  * Add subtle display mode
  * Add image feature (and image only feature)
  * Add `--cc-toggle-img-filter*` custom props and a toolbar story
  * Add a legend to describe the whole group
  * Add active state with small change on background size
  * Enhance backgroud display (hover & selected)
  * Fix component's and stories' docs
  * Fix CSS order
  * Fix JSDoc for event `cc-toggle:input-multiple`
  * Fix vertical text alignement
  * Only show focus ring when not hovered
  * Refactor CSS and move borders on labels
  * Refactor CSS to group and comment sections
  * Remove box-shadow when hovered (we already have a cursor:pointer)
  * Revert to button like border-radius
  * Show boolean example with "activated" choice on the right in the story
  * Switch layout strategy (txt+padding => height+line-height)

### Docs

* Update CONTRIBUTING.md
* Storybook
  * Show list of images used by a component in docs page
  * Add link to source for each component in docs page
  * Add details about component default CSS `display` in docs page
  * Force white background in preview (iPad gets dark auto mode)
  * Improve show code display (and remove hack)
* Startup examples/docs:
  * Rename `ExampleComponent.js` to `cc-example-component.js` and improve examples and docs
  * Introduce `cc-example-component.stories.js` with examples and docs

### For devs

* Update deps
* Update gitlab-ci scaling config
* build: use rollup to build the components
* Storybook
  * Remove useless hacks
  * Simplify i18n-knob hack
  * Use proper story root separator "/" ("|" is deprecated)
  * Load event names from custom-elements.json (addon action)
  * Simplify markdown docs loading
* Refactor:
  * Rename "skeleton" to "skeletonStyles" (fix #92)
  * Rename "instanceDetails" to "instanceDetailsStyles" (fix #92)
  * Change the way we declare skeleton constant data
  * Move all assets (svg icons and geojson) into "assets" dir
  * Big bang rename from `components` to `src`
  * Remove dead code in `<cc-button>` method `_cancelClick()`
  * Add `.cc-waiting` for subtle blinking animations
* ESLint:
  * add custom rule "sort-lit-element-css-declarations"
  * add lit-html specific rules
  * add ES import rules (sort, extensions, dev deps...)
* Add `component:check-lit` task using lit-analyzer to lint/check our components

## 3.0.2 (2020-03-27)

* Update @clevercloud/client to 5.0.1

## 3.0.1 (2020-03-26)

* Change `<cc-beta>` default to `display:grid` so it fixes `<cc-overview>` in Safari with `<cc-logsmap>`

## 3.0.0 (2020-03-14)

### Components

* New component: `<env-var-linked-services>`
* `<env-var-form>`:
  * center overlay blocks in env editor
  * introduce `context` (and `appName`) to provide several translated heading & descriptions
  * pause skeleton on loading errors
  * remove `@env-var-form:dismissed-error` for loading errors
  * just mention "variables" without environment in i18n
  * add docs for default slot
  * remove promise based API

### For devs

* Add Apache 2 license
* Update dev deps (build, tasks...)
* Update to Storybook 5.3.17

### ⚠️ BREAKING CHANGES

* `<env-var-full>`: remove component

NOTE: This component was a bit too high level and the composition was hard to struggle with

## 2.0.2 (2020-03-06)

* `<env-var-form>`: fix parsing/serialization pb with simple/export mode

NOTE: This is a bug fix but if you copy/paste stuffs in the expert mode that was serialized in the old version you could have some problems.

## 2.0.1 (2020-03-05)

* `<cc-elasticsearch-options>`: fix translations/wording
* `<cc-elasticsearch-info>`: fix translations/wording

## 2.0.0 (2020-03-04)

* Update `@clevercloud/client` to `2.3.1`
* New component: `<cc-elasticsearch-options>`
* `<cc-toggle>`:
  * reflect attribute `value`
  * allow `choices` as JSON attribute
  * expose and document cc-toggle-color

### ⚠️ BREAKING CHANGES

* `<cc-elasticsearch-info>`: make all links optional

## 1.4.0 (2020-02-11)

### Components

#### New components for add-ons:

* New component: `<cc-header-addon>`
* New component: `<cc-elasticsearch-info>`
* New component: `<cc-addon-credentials>`
* New component: `<cc-addon-features>`
* New component: `<cc-addon-admin>`
* New component: `<cc-addon-backups>`
* New component: `<cc-addon-linked-apps>`

#### New molecules for all our components:

* New component: `<cc-block>` and `<cc-block-section>`
* New component: `<cc-error>` (and remove `iconStyles`)
* New template: `ccLink()` (with `linkStyles`)

#### Existing components

* `<cc-button>`:
  * add `.focus()` method
  * add `link` feature
  * fix image alignement
  * prevent native click events from propagating/bubbling
  * unset `font-size`
* `<cc-input-text>`:
  * add `tags` feature
  * add `label` feature
  * add `requestimplicitsubmit` event
  * fix hover behaviour on clipboard/secret buttons
* `<cc-logsmap>`: add `<strong>` tags in i18n strings to highlight orga/app name in legend
* `<cc-map>`: don't display no heatmap points when there is an error
* `<cc-overview>`: allow multiple heads with `--cc-overview-head-count`
* `<cc-tile-requests>`: add `<strong>` tags in i18n strings to highlight time window in help
* `<env-var-create>`: add `<code>` tags in i18n strings to highlight error messages
* `<env-var-create>`: use `cc-input-text:requestimplicitsubmit`
* `<env-var-editor-expert>`: add `<code>` tags in i18n strings to highlight error messages
* `<env-var-form>`: use `cc-input-text:requestimplicitsubmit`
* `<env-var-input>`: fix alignment between name and value

### For devs

* Skeleton: add paused state
* Add `sanitize` tag template function to be used in i18n strings containing HTML
  * With cypress test runner
* i18n: Add "Missing lang" to help identify hard coded strings
* Add ADR describing our Storybook migration
* Storybook: update to Storybook 5.3.x ;-)
* Storybook: reload stories when translations are updated
* Tasks: add total count to tasks size
* Removed twemoji depencendy
* Update deps

## 1.3.0 (2019-12-21)

### Components

- New component: `<cc-beta>`
- New component: `<cc-datetime-relative>`
- New component: `<cc-img>`
- New component: `<cc-logsmap>`
- New component: `<cc-map>`
- New component: `<cc-header-app>`
- New component: `<cc-header-orga>`
- New component: `<cc-overview>`
- New component: `<cc-tile-consumption>`
- New component: `<cc-tile-deployments>`
- New component: `<cc-tile-instances>`
- New component: `<cc-tile-requests>`
- New component: `<cc-tile-scalability>`
- New component: `<cc-tile-status-codes>`
- New mixin: `withResizeObserver()`
- `<cc-button>`
  * move away from native click event to custom event `cc-button:click`
  * add warning mode
  * add delay mechanism
- `<cc-input-text>`
  * add copy-to-clipboard feature with `clipboard`
  * add show/hide secret feature with `secret`

### For devs

- New task: `size`
- New i18n system
- New dependencies:
  * [chart.js](https://www.npmjs.com/package/chart.js)
  * [chartjs-plugin-datalabels](https://www.npmjs.com/package/chartjs-plugin-datalabels)
  * [clipboard-copy](https://www.npmjs.com/package/clipboard-copy)
  * [leaflet](https://www.npmjs.com/package/leaflet)
  * [leaflet.heat](https://www.npmjs.com/package/leaflet.heat)
  * [resize-observer-polyfill](https://www.npmjs.com/package/resize-observer-polyfill)
  * [statuses](https://www.npmjs.com/package/statuses)
  * [twemoji](https://www.npmjs.com/package/twemoji)

### Storybook

- Update storybook to 5.3.0-rc
- Update stories to CSF (with a `makeStory` helper) and some MDX documents
- Move from `@storybook/html` to `@storybook/web-components`
- Add a11y addon
- Add viewport addon

## 1.2.0 (2019-07-25)

- Use @clevercloud/client utils to handle env vars

## 1.1.0 (2019-07-15)

- env-var-create: rename button "create" => "add"

## 1.0.7 (2019-07-10)

- cc-toggle: fix isolation of name in shadow DOM for Safari
- cc-input-text: remove Safari box-shadow

## 1.0.6 (2019-07-10)

- cc-input-text: update monospace font

## 1.0.5 (2019-07-10)

- env-var-input: fix button alignment
- env-var-create: fix button alignment
- env-var-input: switch outline for delete/keep button

## 1.0.4 (2019-07-10)

- env-var-input: switch colors for delete/keep button

## 1.0.3 (2019-07-09)

- env-var-input: fix keep/delete
- env-var-form: fix reset form
- env-var-create: fix focus after click on create

## 1.0.2 (2019-07-09)

- cc-input-text: stop propagation on keypress as well

## 1.0.1 (2019-07-09)

- Update npm scripts (move stuffs from `install` to `prestart`)

## 1.0.0 (2019-07-09)

First public stable release

- Expose env-var utils
- Expose i18n helper (with fr and en translations)
- New component: `cc-button`
- New component: `cc-expand`
- New component: `cc-input-text`
- New component: `cc-loader`
- New component: `cc-toggle`
- New component: `env-var-create`
- New component: `env-var-editor-expert`
- New component: `env-var-editor-simple`
- New component: `env-var-form`
- New component: `env-var-full`
- New component: `env-var-input`
