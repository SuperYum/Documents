# Work with CSS Styles

SlimGIS designed a serial format to design styles with CSS that you might already familiar with. It is very easy to understand and getting start to design your own map. And it also supports to adjust the styles on the fly.

Let's first take a look at a screenshot of the app. The projects are host on GitHub. [WPF](https://github.com/SlimGIS/BeautifyMapForWpf), [WinForms](https://github.com/SlimGIS/BeautifulMapForWinForms), [ASP.NET Core WebAPI](https://github.com/SlimGIS/BeautifyMap-WebAPI-DotNetCore).

![wpf-design-with-css](https://github.com/SlimGIS/BeautifyMapForWpf/raw/master/Screenshots/Screenshot-Preview.png)

### Code Snippet

The core code contains only two lines.

```
CssDocument doc = CssDocument.Parse(css);
overlay.LoadStyledLayers("../../../AppData/", doc);
```

What does thoes two lines code do? The css parameter is the CSS string we defined in another file (*.sgcss). Here is a snippet of the `css` parameter in the code.

```css
#cover {
	fill-color: #000000;
}

#cntry02 {
    fill-color: #111111;
    stroke-color: #0c0c0c;
    stroke-thickness: 1px;
}
```

The first line parses the css string into a `CssDocument` instance. In the second line, we load the css document into a `LayerOverlay` instance. The `LoadStyledLayers` method contains two parameters. 

- The first parameter is a folder name that contains the shapefiles, we will search the shapefiles inside the folder recursively.
- The second parameter is the `CssDocument` instance we have just created. 
 
It's pretty simple right?

### CSS introduction

The CSS is the primary part of this guide. It defines two very important information that help us to understand who to organize your data and rendering.

1. It defines the order of the shapefiles in the specified folder. 
    - **Example**: `#cover` in the CSS snippet above, that means their is a shapefile whoes file name is `cover.shp`. It is the first position in the file, which means it will be rendered at the first position. The other layers will render above it. Pretty straight forward. 

    - **An Extra Note**: If you want to define two styles onto the same layer, please use `--` and a suffix behind. A scenario of this is that, we have a point data `cities.shp`. As we mentioned above, the style name should be `#cities {...}`; we want to render the points as tiny spots; when zoom into a specific scale like the county level, we will render its cities name on top of the labels. We will define another style with the same layer name `#cities` + `--` + `[a extra name for this specific case, here we name it as "labels"]`, the finall style name is `#cities--labels`.
    
2. It also defines how the layers rendered. The format can be classified to the following cases.
    - **General declarations**. It means it can be applied to area, linear and point geometries.
    <table class="table table-bordered">
        <thead>
            <tr>
                <th>Name</th>
                <th>Demo</th>
                <th>Description</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>fill-color</td>
                <td>fill-color:#ff0000</td>
                <td>Fills color for area and point geometries. HTML color: `#ff0000`; RGBA color: `rgba(255, 0, 0, 0.5)`; RGB color: `rgb(255, 0, 0)`. This is also compatible with the other colors in this thread.</td>
            </tr>
            <tr>
                <td>stroke-color</td>
                <td>stroke-color:#000000</td>
                <td>The outline color for area and point geometries, and stroke color for the linear geometries.</td>
            </tr>
            <tr>
                <td>stroke-thickness</td>
                <td>stroke-thickness:1px</td>
                <td>The outline width for the area and point geometries and stroke width for linear geometries.</td>
            </tr>
            <tr>
                <td>margin</td>
                <td>margin:20px</td>
                <td>Enlarges the drawing area to avoid some symbol or label is being cut at the edge of the tile.</td>
            </tr>
            <tr>
                <td>upper-level</td>
                <td>upper-level:1</td>
                <td>The upper visible level bound. [0-19]</td>
            </tr>
            <tr>
                <td>lower-level</td>
                <td>lower-level:20</td>
                <td>The lower visible level bound. [0-19]</td>
            </tr>
        </tbody>
    </table>

    - **Point declarations** is only applied to point geometries. It contains:
    
|Name           |Demo                           |Description|
|-------------  |--------------------           |-----------|
|symbol         |symbol:circle                  |Defines the symbol type for point geometries. It supports `Circle` `Cross` `Square` `Triangle` `Diamond` `Hexagon` `Pentagon` `Star`|
|symbol-size    |symbol-size:30px               |Defines how large the symbol is. The default size is `0px`. Make sure it is set to a proper size if we want to make it visible.|
|marker-file    |marker-file:url(../icon.png)   | The marker image file path.|
|marker-width   |marker-width:20px              |The width of the marker image. It will resize image height by the width aspect ratio.|
|marker-offset-x|marker-offset-x:0px            |The marker horizontal offset.|
|marker-offset-y|marker-offset-y:0px            |The marker vertical offset.|
    
    - **Text declarations** can be applied on all geometries.
    
|Name                   |Demo                   |Description|
|-------------          |--------------------   |-----------|
|font-size              |font-size:12px         |The size of text.|
|font-color             |font-color:#000000     |The color of text.|
|font-weight            |font-weight:bold       |The weight of font. Only `bold` is supported now.|
|text-stroke            |text-stroke:1px        |The outline color of the text.|
|text-stroke-thickness  |text-stroke-thickness:2px|The thickness of the outline.|
|text-column            |text-column:name       |The data column name that is used to fetch data for labeling.|
|text-align             |text-align:center      |The text alignment. It supports `upper-left` `upper-center` `upper-right` `center-right` `center` `center-left` `lower-left` `lower-center` `lower-right`.|
|text-offset-x          |text-offset-x:0px      |The text horizontal offset.|
|text-offset-y          |text-offset-y:0px      |The text vertical offset.|
        
    > ### Color Reference: 
    > - HTML color: `#ff0000` 
    > - RGBA color: `rgba(255, 0, 0, 0.5)` 
    > - RGB color: `rgb(255, 0, 0)`
    
## Why not CartoCSS?
We mockup this format is because it is simple and slim. We don't want to waste too much time on complex expression, querying etc. When this is done, we can simply transfer some of our current project to this structure to make it easier debugging and designing the themes. 

As you already awared, most declarations are similar like the CartoCSS. So the next step is to make it compatible with CartoCSS. After that, we will make it fully support. That depends on how much resource we have right now.

How do you feel about this project? Please feel free to [leave us a message](mailto:support@slimgis.com).
