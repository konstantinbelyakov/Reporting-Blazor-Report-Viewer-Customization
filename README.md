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
| [RootCssClasses](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.DxReportViewer.RootCssClasses) |	Sets the component's height and width to 100%. |
| [Zoom](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.DxReportViewer.Zoom) |	Sets the initial zoom level to 125%. |
| [SizeMode](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.DxReportViewer.SizeMode) |	Specifies the medium size of the Report Viewer visual elements. |
| [TabPanelModel](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.DxReportViewer.TabPanelModel) |	Gets the Parameters tab in the Properties Panel to hide the tab and do not display the panel.|

The example uses the following method:

| Method | Result |
|---|---|
| [ParametersModel.OnSubmitParameters](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.Models.ParametersModel.OnSubmitParameters) |	Applies parameter values and builds the document. |


The following event is handled:

| Event | Result |
|---|---|
| [OnCustomizeToolbar](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.DxReportViewer.OnCustomizeToolbar) |	Adds a custom toolbar button that switches the Report Viewer to full-screen mode. |


## Example: Stand-Alone Parameter Editor
Related page: [StandAloneParametersPanel.razor](BlazorCustomization/Pages/StandAloneParametersPanel.razor).

The sample code creates a custom component that is composed of a combo box and a button. The component allows the user to specify the report parameter value.

The example uses the following properties:

| Property | Result |
|---|---|
| [ParametersModel](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.DxReportViewer.ParametersModel) |	Gets the report parameters model. |
| [ParametersModel.VisibleItems](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.Models.ParametersModel.VisibleItems) |	Provides access to the report parameters that the user can change. |

The example uses the following method:

| Method | Result |
|---|---|
| [OnAfterRender](https://docs.microsoft.com/en-us/aspnet/core/blazor/components/lifecycle?view=aspnetcore-5.0#after-component-render-onafterrenderasync) |	Gets access to the TabPanelModel property. |

The following events are handled:

| Event | Result |
|---|---|
| [OnCustomizeParameters](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.DxReportViewer.OnCustomizeParameters) |	Gets the Parameter model and stores it in a variable. |

## Example: Custom Parameter Editor
Related page: [CustomEditor.razor](BlazorCustomization/Pages/CustomEditor.razor).

The sample code specifies a custom template for the parameter editor in the Parameters panel.

The example uses the following properties:

| Property | Result |
|---|---|
| [ParametersModel](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.DxReportViewer.ParametersModel) |	Gets the report parameters model. |
| [ParametersModel.VisibleItems](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.Models.ParametersModel.VisibleItems)  |	Gets the specified parameter model from the parameter collection. |
| [ParameterModel.ValueTemplate](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.Models.ParameterModel.ValueTemplate) |	Specifies the editor template for the parameter in the current model. |

The following events are handled:

| Event | Result |
|---|---|
| [OnCustomizeParameters](https://docs.devexpress.com/XtraReports/DevExpress.Blazor.Reporting.DxReportViewer.OnCustomizeParameters) |	Retrieves a parameter from the Parameter model and specifies a template for the parameter editor. |

## How to Run the Example

1. Download the project and update the **DevExpress.Blazor.Reporting.Viewer** and **DevExpress.Blazor** NuGet packages.
2. Build and run the project.
