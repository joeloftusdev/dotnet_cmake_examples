project(WpfApp VERSION 0.1.0 LANGUAGES CSharp)

include(CSharpUtilities)

add_executable(WpfApp
    ${CMAKE_SOURCE_DIR}/WpfApp/App.xaml.cs
    ${CMAKE_SOURCE_DIR}/WpfApp/AssemblyInfo.cs
    ${CMAKE_SOURCE_DIR}/WpfApp/MainWindow.xaml.cs
    ${CMAKE_SOURCE_DIR}/WpfApp/App.xaml
    ${CMAKE_SOURCE_DIR}/WpfApp/MainWindow.xaml
)

set_property(SOURCE App.xaml PROPERTY VS_XAML_TYPE "ApplicationDefinition")

SET_PROPERTY(TARGET WpfApp PROPERTY VS_PACKAGE_REFERENCES "Serilog_2.9.0;Serilog.Sinks.Console_3.1.1")

target_compile_options(WpfApp PRIVATE "/langversion:latest")

set_target_properties(WpfApp PROPERTIES
DOTNET_SDK "Microsoft.NET.Sdk"
    DOTNET_TARGET_FRAMEWORK "net6.0-windows"
    WIN32_EXECUTABLE TRUE
    VS_GLOBAL_UseWPF "true"
)

