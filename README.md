![Microsoft OpenXR for Unreal Engine](Docs/Images/Banner.png)

> Note : This is a fork of the original Microsoft repository. As it is not maintained anymore by microsoft, I've ported the plugin to Unreal Engine 5.3.
> Some minor features are currently disabled.
>
> Please note that it's not possible to build an embeded app anymore as Epic Game removed the Hololens plateform from the engine. However it will still work by using remoting like before !


# What is the Microsoft OpenXR plugin?
The Microsoft OpenXR plugin is an Unreal Engine game plugin which provides additional features
available on Microsoft's Mixed Reality devices like the HoloLens 2 when using OpenXR.
OpenXR is an open royalty-free API standard from Khronos that provides engines with native access to
a wide range of devices from vendors across the mixed reality spectrum. While Unreal Engine supports
OpenXR natively, some additional functionality specific to Microsoft's Mixed Reality platforms is
only available through this plugin.

| NOTE: The Microsoft OpenXR plugin requires **Unreal 4.26.0+**. |
| --- |

# Feature Summary

Unreal Engine 4.26 with OpenXR provides the following built-in functionality:
* Eye tracking
* Hand joint tracking
* Hand and controller input action mapping

The Microsoft OpenXR plugin provides the following additional functionality:
* Keyboard input routing
* Dynamic hand mesh rendering
* Spatial anchoring
* Holographic Remoting from the PC
* Photo/Video (PV) camera access
* QR code tracking
* Spatial mapping providing a mesh of the physical world
* Voice input
* Azure Spatial Anchors
* Secondary View Configuration (requires 4.26.2+)

If you're new to Mixed Reality development in Unreal, visit the
[Unreal development journey](https://docs.microsoft.com/windows/mixed-reality/unreal-development-overview)
in the Microsoft Docs. The Unreal development journey is specifically tailored to walk new developers
through the installation, core concepts, and usage of the Microsoft OpenXR plugin.

# Using the Microsoft OpenXR plugin

## Use the plugin from GitHub source

1. If you have the MicrosoftOpenXR plugin installed from the Unreal Engine Marketplace, first uninstall that plugin so it will not collide with the source version.
2. Copy MsftOpenXRGame/Plugins/MicrosoftOpenXR to your game's Plugins directory.  Skip this step if using the example MsftOpenXRGame project.
3. This plugin maintains compatibility with older engine versions, so using the source directly may not work as expected in the latest engine release.  
    If you see this message prompt, you *must* retarget the plugin to match your engine version:
    ![The 'MicrosoftOpenXR' plugin was designed for build 4.26.0. Attempt to load it anyway?](Docs/Images/InvalidVersion.png)   

    Modify the ["EngineVersion"](https://github.com/microsoft/Microsoft-OpenXR-Unreal/blob/fccb12a31070bab0d45e8e948f809e6dbdde5937/MsftOpenXRGame/Plugins/MicrosoftOpenXR/MicrosoftOpenXR.uplugin#L13) string in Plugins/MicrosoftOpenXR/MicrosoftOpenXR.uplugin to match the engine version you are using.
    For example, if you are using UE **4.27**, change the line to: **"EngineVersion": "4.27.0"**
4. Reopen the project and the plugin will load correctly.

## Install the plugin from the Unreal Marketplace

1. Install the [Microsoft OpenXR](https://www.unrealengine.com/marketplace/product/ef8930ca860148c498b46887da196239) plugin from the Unreal Engine Marketplace to your engine. 
1. Open Unreal Engine, go to **Project Settings** > **Plugins** and search for "Microsoft OpenXR". Verify that the plugin has been enabled. You may need to restart the engine for changes to take effect.
   > :warning: The "Microsoft Windows Mixed Reality" plugin must be disabled in your project for OpenXR to work.

## Try the example project

If you want to see how each of the features available in OpenXR can be used, check out the example project (/MsftOpenXRGame) contained in this repository. This project has examples of how to use each of the features listed above, as well as a copy of the Microsoft OpenXR plugin in the MsftOpenXRGame/Plugins directory.

> :warning: This example project embeds the source code for the Microsoft OpenXR plugin which conflicts with the Microsoft OpenXR plugin installed from the Unreal Marketplace. The Microsoft OpenXR plugin from the Unreal Marketplace must be uninstalled before opening the example project. This can be done by clicking the "Installed Plugins" link below the engine in your library.

1. Clone this repository.
2. Navigate to the MsftOpenXRGame folder and double-click MsftOpenXRGame.uproject to open the project in Unreal Engine. 
3. See the documention for instructions on how to [stream](https://docs.microsoft.com/en-us/windows/mixed-reality/develop/unreal/unreal-streaming?tabs=openxr) or [package and deploy](https://docs.microsoft.com/en-us/windows/mixed-reality/develop/unreal/unreal-deploying) to device

# Feedback and contributions
If you have a feature request or run into issues using the plugin, please [file an issue](https://github.com/microsoft/Microsoft-OpenXR-Unreal/issues). 

This project welcomes contributions and suggestions. Most contributions require you to agree to a Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the Microsoft Open Source Code of Conduct. For more information see the Code of Conduct FAQ or contact opencode@microsoft.com with any additional questions or comments.
