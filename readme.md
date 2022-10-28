<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/431387329/21.1.5%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T1047381)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->
# Dashboard for ASP.NET Core - How to Recalculate Totals when You Filter a Grid

The Dashboard does not fully support Grid column filters out of the box. These filters can only be used to select which data to show in the Grid item and they do not affect Total values calculated by the dashboard data engine. As a result, the Grid item shows filtered data when you apply grid column filters, but Totals are unchanged.

The example shows how to recalculate totals when when you apply column filters to the Grid dashboard item.

> The example supports all the dashboard's [Total types](https://docs.devexpress.com/Dashboard/117302/web-dashboard/create-dashboards-on-the-web/dashboard-item-settings/grid/totals#totals-overview) except for "Auto". If you apply the "Auto" total type in the dashboard, "Not Supported" is shown instead of the total value.

## Example Overview
### Client

The [CustomGridTotalsExtension.js](./CS/AspNetCoreDashboard_RecalculateTotals/wwwroot/js/CustomGridTotalsExtension.js) custom extension implements the required functionality on the client. The `dxDataGrid`'s [Total Summary](https://js.devexpress.com/Documentation/Guide/UI_Components/DataGrid/Summaries/Total_Summary/) is used to modify the Grid item's underlying UI component. The [ViewerApiExtensionOptions.onItemWidgetOptionsPrepared](https://docs.devexpress.com/Dashboard/js-DevExpress.Dashboard.ViewerApiExtensionOptions?p=netframework#js_devexpress_dashboard_viewerapiextensionoptions_onitemwidgetoptionsprepared) event allows you to access the underlying `dxDataGrid` UI component and change its options.

### Server

The example also modifies Total values when you export data. The [DashboardConfigurator.CustomExport](https://docs.devexpress.com/Dashboard/DevExpress.DashboardWeb.DashboardConfigurator.CustomExport) event handler overrides the export procedure.

## Files to Review

* [CustomGridTotalsExtension.js](./CS/AspNetCoreDashboard_RecalculateTotals/wwwroot/js/CustomGridTotalsExtension.js)
* [_Layout.cshtml](./CS/AspNetCoreDashboard_RecalculateTotals/Pages/_Layout.cshtml)
* [Startup.cs](./CS/AspNetCoreDashboard_RecalculateTotals/Startup.cs)
* [CustomGridTotalsExportModule.cs](./CS/AspNetCoreDashboard_RecalculateTotals/Classes/CustomGridTotalsExportModule.cs)
* [GridTotal.cs](./CS/AspNetCoreDashboard_RecalculateTotals/Classes/GridTotal.cs)

<!-- default file list end -->

## Documentation

* [Totals](https://docs.devexpress.com/Dashboard/117302/web-dashboard/create-dashboards-on-the-web/dashboard-item-settings/grid/totals)
* [Manage Extensions in ASP.NET Core](https://docs.devexpress.com/Dashboard/403354/web-dashboard/aspnet-core-dashboard-control/manage-extensions)
* [Access to Underlying Widgets in ASP.NET Core](https://docs.devexpress.com/Dashboard/401090/web-dashboard/aspnet-core-dashboard-control/access-to-underlying-widgets)

## More Examples

- [Dashboard for WinForms - How to Recalculate Totals When You Filter a Grid](https://github.com/DevExpress-Examples/winforms-dashboard-recalculate-totals)
