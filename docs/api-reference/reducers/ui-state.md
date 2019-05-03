<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### Table of Contents

-   [uiStateUpdaters][1]
    -   [addNotificationUpdater][3]
    -   [cleanupExportImage][5]
    -   [DEFAULT_EXPORT_DATA][7]
    -   [DEFAULT_EXPORT_IMAGE][9]
    -   [DEFAULT_MAP_CONTROLS][11]
    -   [hideExportDropdownUpdater][13]
    -   [INITIAL_UI_STATE][15]
    -   [openDeleteModalUpdater][17]
    -   [setExportDataTypeUpdater][19]
    -   [setExportDataUpdater][21]
    -   [setExportFilteredUpdater][23]
    -   [setExportImageDataUri][25]
    -   [setExportSelectedDatasetUpdater][27]
    -   [setRatioUpdater][29]
    -   [setResolutionUpdater][31]
    -   [showExportDropdownUpdater][33]
    -   [startExportingImage][35]
    -   [toggleLegendUpdater][37]
    -   [toggleMapControlUpdater][39]
    -   [toggleModalUpdater][41]
    -   [toggleSidePanelUpdater][43]
-   [DEFAULT_EXPORT_HTML][45]
-   [setUserMapboxAccessTokenUpdater][47]

## uiStateUpdaters

Updaters for `uiState` reducer. Can be used in your root reducer to directly modify kepler.gl's state.
Read more about [Using updaters][49]

**Examples**

```javascript
import keplerGlReducer, {uiStateUpdaters} from 'kepler.gl/reducers';
// Root Reducer
const reducers = combineReducers({
 keplerGl: keplerGlReducer,
 app: appReducer
});

const composedReducer = (state, action) => {
 switch (action.type) {
   // click button to close side panel
   case 'CLICK_BUTTON':
     return {
       ...state,
       keplerGl: {
         ...state.keplerGl,
         foo: {
            ...state.keplerGl.foo,
            uiState: uiStateUpdaters.toggleSidePanelUpdater(
              uiState, {payload: null}
            )
         }
       }
     };
 }
 return reducers(state, action);
};

export default composedReducer;
```

### addNotificationUpdater

Add a notification to be displayed

-   **Action**: [`addNotification`][50]

**Parameters**

-   `state` **[Object][51]** `uiState`
-   `action` **[Object][51]** 
    -   `action.payload` **[Object][51]** 

Returns **[Object][51]** nextState

### cleanupExportImage

Delete cached export image

-   **Action**: [`cleanupExportImage`][52]

**Parameters**

-   `state` **[Object][51]** `uiState`

Returns **[Object][51]** nextState

### DEFAULT_EXPORT_DATA

Default initial `exportData` settings

Type: [Object][51]

#### Properties

-   `selectedDataset` **[string][53]** Default: `''`,
-   `dataType` **[string][53]** Default: `'csv'`,
-   `filtered` **[boolean][54]** Default: `true`,
-   `config` **[boolean][54]** deprecated
-   `data` **[boolean][54]** used in modal config export. Default: `false`

### DEFAULT_EXPORT_IMAGE

Default image export config

Type: [Object][51]

#### Properties

-   `ratio` **[string][53]** Default: `'SCREEN'`,
-   `resolution` **[string][53]** Default: `'ONE_X'`,
-   `legend` **[boolean][54]** Default: `false`,
-   `imageDataUri` **[string][53]** Default: `''`,
-   `exporting` **[boolean][54]** Default: `false`

### DEFAULT_MAP_CONTROLS

A list of map control visibility and whether is it active.

Type: [Object][51]

#### Properties

-   `visibleLayers` **[Object][51]** Default: `{show: true, active: false}`
-   `mapLegend` **[Object][51]** Default: `{show: true, active: false}`
-   `toggle3d` **[Object][51]** Default: `{show: true}`
-   `splitMap` **[Object][51]** Default: `{show: true}`

### hideExportDropdownUpdater

Hide side panel header dropdown, activated by clicking the share link on top of the side panel

-   **Action**: [`hideExportDropdown`][55]

**Parameters**

-   `state` **[Object][51]** `uiState`

Returns **[Object][51]** nextState

### INITIAL_UI_STATE

Default initial `uiState`

Type: [Object][51]

#### Properties

-   `readOnly` **[boolean][54]** Default: `false`
-   `activeSidePanel` **[string][53]** Default: `'layer'`
-   `currentModal` **([string][53] | null)** Default: `'addData'`
-   `datasetKeyToRemove` **([string][53] | null)** Default: `null`
-   `visibleDropdown` **([string][53] | null)** Default: `null`
-   `exportImage` **[Object][51]** Default: [`DEFAULT_EXPORT_IMAGE`][9]
-   `exportData` **[Object][51]** Default: [`DEFAULT_EXPORT_DATA`][7]
-   `mapControls` **[Object][51]** Default: [`DEFAULT_MAP_CONTROLS`][11]

### openDeleteModalUpdater

Toggle active map control panel

-   **Action**: [`openDeleteModal`][56]

**Parameters**

-   `state` **[Object][51]** `uiState`
-   `action` **[Object][51]** 
    -   `action.payload` **[string][53]** dataset id

Returns **[Object][51]** nextState

### setExportDataTypeUpdater

Set data format for exporting data

-   **Action**: [`setExportDataType`][57]

**Parameters**

-   `state` **[Object][51]** `uiState`
-   `action` **[Object][51]** 
    -   `action.payload` **[string][53]** one of `'text/csv'`

Returns **[Object][51]** nextState

### setExportDataUpdater

Whether to including data in map config, toggle between `true` or `false`

-   **Action**: [`setExportData`][58]

**Parameters**

-   `state` **[Object][51]** `uiState`

Returns **[Object][51]** nextState

### setExportFilteredUpdater

Whether to export filtered data, `true` or `false`

-   **Action**: [`setExportFiltered`][59]

**Parameters**

-   `state` **[Object][51]** `uiState`
-   `action` **[Object][51]** 
    -   `action.payload` **[boolean][54]** 

Returns **[Object][51]** nextState

### setExportImageDataUri

Set `exportImage.setExportImageDataUri` to a image dataUri

-   **Action**: [`setExportImageDataUri`][60]

**Parameters**

-   `state` **[Object][51]** `uiState`
-   `action` **[Object][51]** 
    -   `action.payload` **[string][53]** export image data uri

Returns **[Object][51]** nextState

### setExportSelectedDatasetUpdater

Set selected dataset for export

-   **Action**: [`setExportSelectedDataset`][61]

**Parameters**

-   `state` **[Object][51]** `uiState`
-   `action` **[Object][51]** 
    -   `action.payload` **[string][53]** dataset id

Returns **[Object][51]** nextState

### setRatioUpdater

Set `exportImage.ratio`

-   **Action**: [`setRatio`][62]

**Parameters**

-   `state` **[Object][51]** `uiState`
-   `action` **[Object][51]** 
    -   `action.payload` **[string][53]** one of `'SCREEN'`, `'FOUR_BY_THREE'` and `'SIXTEEN_BY_NINE'`

Returns **[Object][51]** nextState

### setResolutionUpdater

Set `exportImage.resolution`

-   **Action**: [`setResolution`][63]

**Parameters**

-   `state` **[Object][51]** `uiState`
-   `action` **[Object][51]** 
    -   `action.payload` **[string][53]** one of `'ONE_X'`, `'TWO_X'`

Returns **[Object][51]** nextState

### showExportDropdownUpdater

Hide and show side panel header dropdown, activated by clicking the share link on top of the side panel

-   **Action**: [`showExportDropdown`][64]

**Parameters**

-   `state` **[Object][51]** `uiState`
-   `action` **[Object][51]** 
    -   `action.payload` **[string][53]** id of the dropdown

Returns **[Object][51]** nextState

### startExportingImage

Set `exportImage.exporting` to `true`

-   **Action**: [`startExportingImage`][65]

**Parameters**

-   `state` **[Object][51]** `uiState`

Returns **[Object][51]** nextState

### toggleLegendUpdater

Set `exportImage.legend` to `true` or `false`

-   **Action**: [`toggleLegend`][66]

**Parameters**

-   `state` **[Object][51]** `uiState`

Returns **[Object][51]** nextState

### toggleMapControlUpdater

Toggle active map control panel

-   **Action**: [`toggleMapControl`][67]

**Parameters**

-   `state` **[Object][51]** `uiState`
-   `action` **[Object][51]** action
    -   `action.payload` **[string][53]** map control panel id, one of the keys of: [`DEFAULT_MAP_CONTROLS`][11]

Returns **[Object][51]** nextState

### toggleModalUpdater

Show and hide modal dialog

-   **Action**: [`toggleModal`][68]

**Parameters**

-   `state` **[Object][51]** `uiState`
-   `action` **[Object][51]** 
    -   `action.payload` **([string][53] | null)** id of modal to be shown, null to hide modals. One of:-   [`DATA_TABLE_ID`][69]
        -   [`DELETE_DATA_ID`][70]
        -   [`ADD_DATA_ID`][71]
        -   [`EXPORT_IMAGE_ID`][72]
        -   [`EXPORT_DATA_ID`][73]
        -   [`ADD_MAP_STYLE_ID`][74]

Returns **[Object][51]** nextState

### toggleSidePanelUpdater

Toggle active side panel

-   **Action**: [`toggleSidePanel`][75]

**Parameters**

-   `state` **[Object][51]** `uiState`
-   `action` **[Object][51]** 
    -   `action.payload` **([string][53] | null)** id of side panel to be shown, one of `layer`, `filter`, `interaction`, `map`. close side panel if `null`

Returns **[Object][51]** nextState

## DEFAULT_EXPORT_HTML

Type: [Object][51]

### Properties

-   `exportMapboxAccessToken` **[string][53]** Default: null, this is used when we provide a default mapbox token for users to take advantage of
-   `userMapboxToken` **[string][53]** Default: '', mapbox token provided by user through input field

## setUserMapboxAccessTokenUpdater

whether to export a mapbox access to HTML single page

-   **Action**: [`setUserMapboxAccessToken`][76]

**Parameters**

-   `state` **[Object][51]** `uiState`
-   `action` **[Object][51]** 
    -   `action.payload` **[string][53]** 

Returns **[Object][51]** nextState

[1]: #uistateupdaters

[2]: #examples

[3]: #addnotificationupdater

[4]: #parameters

[5]: #cleanupexportimage

[6]: #parameters-1

[7]: #default_export_data

[8]: #properties

[9]: #default_export_image

[10]: #properties-1

[11]: #default_map_controls

[12]: #properties-2

[13]: #hideexportdropdownupdater

[14]: #parameters-2

[15]: #initial_ui_state

[16]: #properties-3

[17]: #opendeletemodalupdater

[18]: #parameters-3

[19]: #setexportdatatypeupdater

[20]: #parameters-4

[21]: #setexportdataupdater

[22]: #parameters-5

[23]: #setexportfilteredupdater

[24]: #parameters-6

[25]: #setexportimagedatauri

[26]: #parameters-7

[27]: #setexportselecteddatasetupdater

[28]: #parameters-8

[29]: #setratioupdater

[30]: #parameters-9

[31]: #setresolutionupdater

[32]: #parameters-10

[33]: #showexportdropdownupdater

[34]: #parameters-11

[35]: #startexportingimage

[36]: #parameters-12

[37]: #togglelegendupdater

[38]: #parameters-13

[39]: #togglemapcontrolupdater

[40]: #parameters-14

[41]: #togglemodalupdater

[42]: #parameters-15

[43]: #togglesidepanelupdater

[44]: #parameters-16

[45]: #default_export_html

[46]: #properties-4

[47]: #setusermapboxaccesstokenupdater

[48]: #parameters-17

[49]: ../advanced-usage/using-updaters.md

[50]: ../actions/actions.md#addnotification

[51]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object

[52]: ../actions/actions.md#cleanupexportimage

[53]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String

[54]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean

[55]: ../actions/actions.md#hideexportdropdown

[56]: ../actions/actions.md#opendeletemodal

[57]: ../actions/actions.md#setexportdatatype

[58]: ../actions/actions.md#setexportdata

[59]: ../actions/actions.md#setexportfiltered

[60]: ../actions/actions.md#setexportimagedatauri

[61]: ../actions/actions.md#setexportselecteddataset

[62]: ../actions/actions.md#setratio

[63]: ../actions/actions.md#setresolution

[64]: ../actions/actions.md#showexportdropdown

[65]: ../actions/actions.md#startexportingimage

[66]: ../actions/actions.md#togglelegend

[67]: ../actions/actions.md#togglemapcontrol

[68]: ../actions/actions.md#togglemodal

[69]: ../constants/default-settings.md#data_table_id

[70]: ../constants/default-settings.md#delete_data_id

[71]: ../constants/default-settings.md#add_data_id

[72]: ../constants/default-settings.md#export_image_id

[73]: ../constants/default-settings.md#export_data_id

[74]: ../constants/default-settings.md#add_map_style_id

[75]: ../actions/actions.md#togglesidepanel

[76]: ../actions/actions.md#setusermapboxaccesstoken