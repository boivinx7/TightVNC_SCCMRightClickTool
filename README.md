# TightVNC_SCCMRightClickTool

Information from how and where to Put Action Files in I found installing the Powershell Right Click tools and then deleting folders by folders. But Having Looked a bit more I might have found this http://eddiejackson.net/wp/?p=16094
Which would have saved me a lot of time.

![alt text](https://i.imgur.com/bBGBcM8.png)

I suggest that you use the MSI to install this.
So The Files that Are called by the Extentions are going to
C:\Program Files (X86)\MB_tools\TightVNC_SCCMRightClickTool


The XML Actions Extentions will go to 
C:\Program Files (x86)\Microsoft Configuration Manager\AdminConsole\XmlStorage\Extensions\Actions\3fd01cd1-9e01-461e-92cd-94866b8d1f39
C:\Program Files (x86)\Microsoft Configuration Manager\AdminConsole\XmlStorage\Extensions\Actions\ed9dee86-eadd-4ac8-82a1-7234a4646e62

![alt text](https://i.imgur.com/0E7BoLD.png)

Content of the XML File
```
<ActionDescription Class="Executable" DisplayName="VNC Connection" MnemonicDisplayName="VNC Connection" Description="Created by Maxime Bilodeau">
		<ShowOn>
			<string>ContextMenu</string>
		</ShowOn>
<ImagesDescription>
	<ResourceAssembly>
		<Assembly>C:\Program Files\MB_tools\VNC_SCCMRightClickTool\Icons.DLL</Assembly>
		<Type>Icons.Properties.Resources.resources</Type>
	</ResourceAssembly>
	<ImageResourceName>TightVNC</ImageResourceName>
</ImagesDescription>
		<Executable>
			<FilePath>"C:\Program Files\MB_tools\TightVNC_RightClickTool\Start-VNCConnection.exe"</FilePath>
			    <Parameters>-SiteServer "##SUB:__Server##" -ResourceID "##SUB:ResourceID##"</Parameters>
		</Executable>
</ActionDescription>



```

Also, Disclaimer,
If i'm using any Icon that I should not use, please tell me,
I can remove it or add a reference if you want. This is 100% a free project that I did mainly for myself and tought that I would Share.
Thanks
