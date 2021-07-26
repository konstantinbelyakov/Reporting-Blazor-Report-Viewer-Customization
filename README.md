# Report Viewer for Blazor - Customization API

This project demonstrates how to use API to customize the Report Viewer 'native' server-side Blazor component.

## Overview
The Report Viewer API entry point is the [DxReportViewer](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.DxReportViewer) class. You can specify its properties and handle its events to adjust the Report Viewer appearance and behavior. 

## Example: UI Customization
Related pages: [Toolbar.razor](BlazorCustomization/Pages/Toolbar.razor), [StandAloneParametersPanel.razor](BlazorCustomization/Pages/StandAloneParametersPanel.razor).

The sample code sets the component's initial size and zoom level, adds a custom button to the toolbar, hides the Properties Panel.

The example uses the following properties:

| Property | Result |
|---|---|
| RootCssClasses |	Sets the component's height and width to 100%. |
| Zoom |	Sets the initial zoom level to 125%. |
| SizeMode |	Specifies the medium size of the Report Viewer visual elements. |
| TabPanelModel |	Gets the Parameters tab in the Properties Panel to hide the tab and do not display the panel.|

The example uses the following methods:

| Method | Result |
|---|---|
| ParametersModel.OnSubmitParameters() |	Applies parameter values and builds the document. |


The following events are handled:

| Event | Result |
|---|---|
| OnCustomizeToolbar |	Adds a custom toolbar button that switches the Report Viewer to full-screen mode. |
| OnAfterRender |	Gets access to the TabPanelModel property. |

## Example: Stand-Alone Parameter Editor
Related page: [StandAloneParametersPanel.razor](BlazorCustomization/Pages/StandAloneParametersPanel.razor).

The sample code creates a custom component that is composed of a combo box and a button. The component allows the user to specify the report parameter value.

The example uses the following properties:

| Property | Result |
|---|---|
| ParametersModel |	Gets the report parameters model. |
| ParametersModel.VisibleItems |	Provides access to the report parameters that the user can change. |

The following events are handled:

| Event | Result |
|---|---|
| OnCustomizeParameters |	Gets the Parameter model and stores it in a variable. |

## Example: Custom Parameter Editor
Related page: [CustomEditor.razor](BlazorCustomization/Pages/CustomEditor.razor).

The sample code specifies a custom template for the parameter editor in the Parameters panel.

The example uses the following properties:

| Property | Result |
|---|---|
| ParametersModel |	Gets the report parameters model. |
| ParametersModel.VisibleItems |	Gets the specified parameter model from the parameter collection. |
| ParameterModel.ValueTemplate |	Specifies the editor template for the parameter in the current model. |

The following events are handled:

| Event | Result |
|---|---|
| OnCustomizeParameters |	Retrieves a parameter from the Parameter model and specifies a template for the parameter editor. |

## How to Run the Example

1. Download the project and update the **DevExpress.Blazor.Reporting.Viewer** and **DevExpress.Blazor** NuGet packages.
2. Build and run the project.
