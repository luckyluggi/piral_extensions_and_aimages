# Repro Steps
- `cd ./appshell` and run `npm i` and then `npm run build`
- `cd ../blazor-pilet1` and run `dotnet build`
- `cd ../blazor-pilet2` and run `dotnet build`
- `cd ../.piral~/blazor-pilet1` and run `pilet debug ./src/index.tsx ..\BlazorPilet2\src\index.tsx`

# Problems
1. When you visit `http://localhost:1234/image` you should see an image. It's loaded in blazor-pilet2\Pages\ImagePage.razor from `blazor-pilet2\wwwroot\images\image.jpg` using `IPiletService.GetUrl()` but that does not work anymore.
2. When you visit `http://localhost:1234/extension` you see the extension `blazor-pilet1\Components\TestExtension.razor` with the silver background. There a value should be shown.
   The Value is created in `blazor-pilet2\Pages\ExtensionPage.razor` and given to the extension via `[PiralParameter("params")]`. This does not work anymore.