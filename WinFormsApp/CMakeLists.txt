project(WinFormsApp VERSION 0.1.0 LANGUAGES CSharp)

include(CSharpUtilities)

add_executable(WinFormsApp
    ${CMAKE_SOURCE_DIR}/WinFormsApp/Form1.cs
    ${CMAKE_SOURCE_DIR}/WinFormsApp/Form1.Designer.cs
    ${CMAKE_SOURCE_DIR}/WinFormsApp/Form1.resx
    ${CMAKE_SOURCE_DIR}/WinFormsApp/Program.cs
)

set_property(SOURCE App.xaml PROPERTY VS_XAML_TYPE "ApplicationDefinition")

SET_PROPERTY(TARGET WinFormsApp PROPERTY VS_PACKAGE_REFERENCES "Serilog_2.9.0;Serilog.Sinks.Console_3.1.1")

target_compile_options(WinFormsApp PRIVATE "/langversion:latest")

set_target_properties(WinFormsApp PROPERTIES
DOTNET_SDK "Microsoft.NET.Sdk"
    DOTNET_TARGET_FRAMEWORK "net6.0-windows"
    WIN32_EXECUTABLE TRUE
    VS_GLOBAL_UseWindowsForms "true"
    VS_GLOBAL_ImplicitUsings "enable"
)

