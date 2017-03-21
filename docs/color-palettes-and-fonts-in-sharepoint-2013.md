---
title: Color palettes and fonts in SharePoint 2013
ms.prod: SHAREPOINT
ms.assetid: c17d375b-151f-48ae-ac32-f2ce9e68d63f
---


# Color palettes and fonts in SharePoint 2013
Use this reference to define the color palette or font scheme that is used in a SharePoint 2013 site. 
## Color palettes
<a name="color"> </a>

A color palette is the combination of colors that are used in a SharePoint site. The color palette for a SharePoint site is defined in a color palette file. Color slots are also used by the master page preview file to generate thumbnail and preview images of a site. The following describes the structure of the color palette file and the master page preview file: 
  
    
    

- **Color palette file (.spcolor)**
    
    Color palette files are used in the **Change the look** wizard, which enables users to change the look and feel of their site by using the SharePoint themes user interface. By default, 32 color palette files are installed with SharePoint 2013. You can also create additional color palette files. The following example shows the format of a color palette file.
    


  ```XML
  
<s:colorPalette isInverted="InvertedSetting" previewSlot1="Slot1" previewSlot2="Slot2" previewSlot3="Slot3" xmlns:s="http://schemas.microsoft.com/sharepoint/">
    <s:color name="ColorSlot" value="Color" />
    <!--additional color slots-->
</s:colorPalette>
  ```


    In a color palette file, the following placeholders are replaced: 
    
  -  _InvertedSetting_ is a Boolean value. **true** if the color palette is generally light text on a dark background. **false** if the color palette is generally dark text on a light background.
    
  
  -  _Slot1_ is the annotation name of the color slot to use as the first block of the palette icon in the color palette picker of the theming experience.
    
  
  -  _Slot2_ is the annotation name of the color slot to use as the second block of the palette icon in the color palette picker of the theming experience.
    
  
  -  _Slot3_ is the annotation name of the color slot to use as the third block of the palette icon in the color palette picker of the theming experience.
    
  
  -  _ColorSlot_ is the annotation name of the color slot that you are defining (for example, SiteTitle).
    
  
  -  _Color_ is the hexadecimal value of the color to use for the specified color slot. This may be in 6 digits (RRGGBB) or 8 digits (AARRGGBB). If the hexadecimal value is 8 digits, the first two digits represent the opacity level (00-FF, which maps to 0-255). If the hexadecimal value is 6 digits, the default opacity is 100% or FF.
    
  

    The color palette files are located in the Theme Gallery of the root site, in the site collection in the **15** folder (http:// _SiteCollectionName_/_catalogs/theme/15/). To access the Theme Gallery from the SharePoint user interface, on the **Site Settings** page, under **Web Designer Galleries**, select **Themes**, and then select **15**. 
    
  
- **Master page preview file (.preview)**
    
    Master page preview files are used to generate thumbnail images and preview images when you use the **Change the look** wizard. A master page must have a corresponding preview file to be used in the **Change the look** wizard. A preview file is a specially formatted file that has sections for the default color palette, default font scheme, tokenized CSS, and tokenized HTML. It uses string tokens to get the value of color slots, font names, and localized UI strings. The following example shows color slots being used in the master page preview file.
    


  ```HTML
  
[ID] #dgp-pageContainer
{
    background-color: [T_THEME_COLOR_PAGEBACKGROUND];
    color: [T_THEME_COLOR_BODYTEXT];
    width: 100%;
    height:100%;     
    background-image: url('[T_IMAGE]');       
    background-size: cover;
    font-family: [T_BODY_FONT];   
}
  ```


    For more information, see  [How to: Create a master page preview file in SharePoint 2013](how-to-create-a-master-page-preview-file-in-sharepoint-2013.md)
    
  

> [!TIP]  
> You can use the SharePoint color palette tool to help you create SharePoint designs. You can  [download the SharePoint color palette tool](http://www.microsoft.com/en-us/download/details.aspx?id=38182) from the Microsoft Download Center.
  
    
    


### Color slot mapping
<a name="colorSlots"> </a>

Table 1 describes the color slots that are available and where color slots are used in a SharePoint site. 
  
    
    

> [!NOTE]  
>  When discussing navigation items,pressed applies to when a user clicks or touches a navigation item.Selected applies to when a user is navigated to the page.
>  The following summarizes a normal flow of actions and the color slot that applies to the navigation item link at each step:
>  The base text of a navigation item link: HeaderNavigationText
>  A user hovers the cursor over the navigation item link: HeaderNavigationHoverText
>  A user clicks, touches, or chooses the navigation item link: HeaderNavigationPressedText
>  The user is navigated to the chosen page. The color slot that applies to the navigation item for the page the user is now on: HeaderNavigationSelectedText
  
    
    


**Table 1. Color slots**


|**Annotation Name**|**Where the Color Is Used in the UI**|**Token Name**|
|:-----|:-----|:-----|
|BodyText |Normal body text. |[T_THEME_COLOR_BODYTEXT] |
|SubtleBodyText |Body text that must be lighter than normal. An example is metadata text. |[T_THEME_COLOR_SUBTLEBODYTEXT] |
|StrongBodyText |Body text color for text that must stand out from normal body text. |[T_THEME_COLOR_STRONGBODYTEXT] |
|DisabledText |Disabled text. For example, unavailable items in menus. |[T_THEME_COLOR_DISABLEDTEXT] |
|SiteTitle |The text color of the page title. |[T_THEME_COLOR_SITETITLE] |
|WebPartHeading |Text color for Web Part headings. |[T_THEME_COLOR_WEBPARTHEADING] |
|ErrorText |The main error color that is used for error text, borders, and backgrounds, as needed. |[T_THEME_COLOR_ERRORTEXT] |
|AccentText |Text color for accented body text. |[T_THEME_COLOR_ACCENTTEXT] |
|SearchURL |Text color for the URL found in search results. Also used to highlight new items or successful status notifications. |[T_THEME_COLOR_SEARCHURL] |
|Hyperlink |Text color for hyperlinks. |[T_THEME_COLOR_HYPERLINK] |
|HyperlinkFollowed |Text color for followed hyperlinks. |[T_THEME_COLOR_HYPERLINKFOLLOWED] |
|HyperlinkActive |Hyperlink color when pressed. |[T_THEME_COLOR_HYPERLINKACTIVE] |
|CommandLinks |Large command links that must be a bit lighter than body text because of their size. |[T_THEME_COLOR_COMMANDLINKS] |
|CommandLinksSecondary |Command link color for links that are smaller, and therefore have a stronger color to stand out. |[T_THEME_COLOR_COMMANDLINKSSECONDARY] |
|CommandLinksHover |Command link color on hover. |[T_THEME_COLOR_COMMANDLINKSHOVER] |
|CommandLinksPressed |Command link color when pressed. |[T_THEME_COLOR_COMMANDLINKSPRESSED] |
|CommandLinksDisabled |Command link color when command link is disabled. |[T_THEME_COLOR_COMMANDLINKSDISABLED] |
|BackgroundOverlay |The main background color that is visible between the optional background image and the page content. |[T_THEME_COLOR_BACKGROUNDOVERLAY] |
|DisabledBackground |Background for disabled elements such as browser controls, for example, input box or select box (except buttons). |[T_THEME_COLOR_DISABLEDBACKGROUND] |
|PageBackground |The background color of the page. Appears behind the optional background image. |[T_THEME_COLOR_PAGEBACKGROUND] |
|HeaderBackground |The background color for the header area of the page. |[T_THEME_COLOR_HEADERBACKGROUND] |
|FooterBackground |The background color for the footer area of the page. |[T_THEME_COLOR_FOOTERBACKGROUND] |
|SelectionBackground |The background color for selected list items and drop-down menu items. |[T_THEME_COLOR_SELECTIONBACKGROUND] |
|HoverBackground |The background color for list items and drop-down menu items on hover. |[T_THEME_COLOR_HOVERBACKGROUND] |
|RowAccent |The accented left border on selected list items. |[T_THEME_COLOR_ROWACCENT] |
|StrongLines |Borders for browser controls on hover. |[T_THEME_COLOR_STRONGLINES] |
|Lines |Borders for browser controls. |[T_THEME_COLOR_LINES] |
|SubtleLines |Subtle border color. For example, gridlines for inline editing. |[T_THEME_COLOR_SUBTLELINES] |
|DisabledLines |Border color for disabled browser controls such as input boxes and select boxes. |[T_THEME_COLOR_DISABLEDLINES] |
|AccentLines |Focused border color for selected browser controls. |[T_THEME_COLOR_ACCENTLINES] |
|DialogBorder |Dialog box border color. |[T_THEME_COLOR_DIALOGBORDER] |
|Navigation |Text color for horizontal and vertical navigation items. |[T_THEME_COLOR_NAVIGATION] |
|NavigationAccent |Text color for a selected horizontal navigation item. |[T_THEME_COLOR_NAVIGATIONACCENT] |
|NavigationHover |Navigation text color on hover. Applies to top navigation, and to Quick Launch in horizontal mode. |[T_THEME_COLOR_NAVIGATIONHOVER] |
|NavigationPressed |Text color of navigation item when pressed. Applies to top navigation, and to Quick Launch in horizontal mode. |[T_THEME_COLOR_NAVIGATIONPRESSED] |
|NavigationHoverBackground |Background color of Quick Launch items in vertical mode on hover over the navigation item. |[T_THEME_COLOR_NAVIGATIONHOVERBACKGROUND] |
|NavigationSelectedBackground |Background color of Quick Launch items in vertical mode after the navigation item is selected. |[T_THEME_COLOR_NAVIGATIONSELECTEDBACKGROUND] |
|EmphasisText |The text color that appears on top of emphasis background. |[T_THEME_COLOR_EMPHASISTEXT] |
|EmphasisBackground |The accented background color that appears directly behind emphasis text. |[T_THEME_COLOR_EMPHASISBACKGROUND] |
|EmphasisHoverBackground |Background color on hover, for elements that are using emphasis background. |[T_THEME_COLOR_EMPHASISHOVERBACKGROUND] |
|EmphasisBorder |Border color for elements that are using emphasis background. |[T_THEME_COLOR_EMPHASISBORDER] |
|EmphasisHoverBorder |Border color on hover for elements that are using emphasis background. |[T_THEME_COLOR_EMPHASISHOVERBORDER] |
|SubtleEmphasisText |Text that appears on top of subtle emphasis background. |[T_THEME_COLOR_SUBTLEEMPHASISTEXT] |
|SubtleEmphasisCommandLinks |Command link color for links that appear on top of subtle emphasis background. |[T_THEME_COLOR_SUBTLEEMPHASISCOMMANDLINKS] |
|SubtleEmphasisBackground |Background that appears directly behind subtle emphasis text. |[T_THEME_COLOR_SUBTLEEMPHASISBACKGROUND] |
|TopBarText |Text and glyph color for the welcome menu, quick access toolbar icons, and closed ribbon tabs. |[T_THEME_COLOR_TOPBARTEXT] |
|TopBarBackground |The background color for the top bar, which is seen below and to the right of the suite navigation. |[T_THEME_COLOR_TOPBARBACKGROUND] |
|TopBarHoverText |Text and glyph color on hover for the welcome menu, quick access toolbar icons, and closed ribbon tabs. |[T_THEME_COLOR_TOPBARHOVERTEXT] |
|TopBarPressedText |Text and glyph color for when the welcome menu, quick access toolbar icons, or closed ribbon tabs are pressed. |[T_THEME_COLOR_TOPBARPRESSEDTEXT] |
|HeaderText |The base text color for anything in the header area. |[T_THEME_COLOR_HEADERTEXT] |
|HeaderSubtleText |Helper text for the search box when in the header area. |[T_THEME_COLOR_HEADERSUBTLETEXT] |
|HeaderDisableText |Text for the search box, if the search box is disabled when in the header area. |[T_THEME_COLOR_HEADERDISABLETEXT] |
|HeaderNavigationText |Base text color for navigation links in the header area. |[T_THEME_COLOR_HEADERNAVIGATIONTEXT] |
|HeaderNavigationHoverText |Text color for navigation links in the header area when you hover over the link. |[T_THEME_COLOR_HEADERNAVIGATIONHOVERTEXT] |
|HeaderNavigationPressedText |Text color for navigation links in the header area when you press the link. |[T_THEME_COLOR_HEADERNAVIGATIONPRESSEDTEXT] |
|HeaderNavigationSelectedText |Text color for navigation links in the header area after the link is selected. |[T_THEME_COLOR_HEADERNAVIGATIONSELECTEDTEXT] |
|HeaderLines |Search box lines when the search box is in the header area. |[T_THEME_COLOR_HEADERLINES] |
|HeaderStrongLines |Search box lines on hover when the search box is in the header area. |[T_THEME_COLOR_HEADERSTRONGLINES] |
|HeaderAccentLines |Search box lines on focus when the search box is in the header area. |[T_THEME_COLOR_HEADERACCENTLINES] |
|HeaderSublteLines |Subtle lines found inside the header area. Not used in default CSS. |[T_THEME_COLOR_HEADERSUBTLELINES] |
|HeaderDisabledLines |Search box lines if the search box is disabled when it's in the header area. |[T_THEME_COLOR_HEADERDISABLEDLINES] |
|HeaderDisabledBackground |Search box background if the search box is disabled when it's in the header area. |[T_THEME_COLOR_HEADERDISABLEDBACKGROUND] |
|HeaderFlyoutBorder |Border for drop-down menus when originating from the header area. |[T_THEME_COLOR_HEADERFLYOUTBORDER] |
|HeaderSiteTitle |Text color for the site title when in the header area. |[T_THEME_COLOR_HEADERSITETITLE] |
|SuiteBarBackground |Background color for the suite navigation. |[T_THEME_COLOR_SUITEBARBACKGROUND] |
|SuiteBarHoverBackground |Background color on hover for the suite navigation. |[T_THEME_COLOR_SUITEBARHOVERBACKGROUND] |
|SuiteBarText |Text and glyph color for the suite navigation items. |[T_THEME_COLOR_SUITEBARTEXT] |
|SuiteBarDisabledText |Text and glyph color for disabled suite items. Not used in default CSS. |[T_THEME_COLOR_SUITEBARDISABLEDTEXT] |
|ButtonText |Text color for buttons. |[T_THEME_COLOR_BUTTONTEXT] |
|ButtonDisabledText |Text color for disabled buttons. |[T_THEME_COLOR_BUTTONDISABLEDTEXT] |
|ButtonBackground |Background color for buttons. |[T_THEME_COLOR_BUTTONBACKGROUND] |
|ButtonHoverBackground |Background color for buttons on hover. |[T_THEME_COLOR_BUTTONHOVERBACKGROUND] |
|ButtonPressedBackground |Background color for buttons while pressed. |[T_THEME_COLOR_BUTTONPRESSEDBACKGROUND] |
|ButtonDisabledBackground |Background color for disabled buttons. |[T_THEME_COLOR_BUTTONDISABLEDBACKGROUND] |
|ButtonBorder |Border color for buttons. |[T_THEME_COLOR_BUTTONBORDER] |
|ButtonHoverBorder |Border color for buttons on hover. |[T_THEME_COLOR_BUTTONHOVERBORDER] |
|ButtonPressedBorder |Border color for buttons while pressed. |[T_THEME_COLOR_BUTTONPRESSEDBORDER] |
|ButtonDisabledBorder |Border color for buttons that are disabled. |[T_THEME_COLOR_BUTTONDISABLEDBORDER] |
|ButtonGlyph |Glyph color for a glyph that appears in a button. |[T_THEME_COLOR_BUTTONGLYPH] |
|ButtonGlyphActive |Glyph color on hover, for a glyph that appears in a button. |[T_THEME_COLOR_BUTTONGLYPHACTIVE] |
|ButtonGlyphDisabled |Glyph color for a disabled button. |[T_THEME_COLOR_BUTTONGLYPHDISABLED] |
|TileText |The text that appears on top of the tile background overlay. |[T_THEME_COLOR_TILETEXT] |
|TileBackgroundOverlay |The background overlay color for tiles. |[T_THEME_COLOR_TILEBACKGROUNDOVERLAY] |
|ContentAccent1 |The first accent color that a user can select from the Rich Text Editor color picker. |[T_THEME_COLOR_CONTENTACCENT1] |
|ContentAccent2 |The second accent color that a user can select from the Rich Text Editor color picker. |[T_THEME_COLOR_CONTENTACCENT2] |
|ContentAccent3 |The third accent color that a user can select from the Rich Text Editor color picker. |[T_THEME_COLOR_CONTENTACCENT3] |
|ContentAccent4 |The fourth accent color that a user can select from the Rich Text Editor color picker. |[T_THEME_COLOR_CONTENTACCENT4] |
|ContentAccent5 |The fifth accent color that a user can select from the Rich Text Editor color picker. |[T_THEME_COLOR_CONTENTACCENT5] |
|ContentAccent6 |The sixth accent color that a user can select from the Rich Text Editor color picker. |[T_THEME_COLOR_CONTENTACCENT6] |
   

## Font schemes
<a name="font"> </a>

Fonts are defined in the font scheme (.spfont file) and the master page preview (.preview file) for a given SharePoint site. The font scheme defines the fonts that are used in four areas: title, navigation, heading, and body. Seven font schemes are included in SharePoint 2013. You can create additional font schemes. The font scheme files are located in the **15** subfolder of the Theme Gallery of the root site of the site collection (http:// _SiteCollectionName_/_catalogs/theme/15/). To access the Theme Gallery from the SharePoint user interface, on the **Site Settings** page, under **Web Designer Galleries**, select **Themes**, and then select **15**. 
  
    
    
The following example describes the format for an .spfont file. 
  
    
    



```XML

<?xml version="1.0" encoding="utf-8"?>
<s:fontScheme name="FontSchemeName" previewSlot1="Slot1" previewSlot2="Slot2" xmlns:s="http://schemas.microsoft.com/sharepoint/">
  <s:fontSlots>
    <s:fontSlot name="FontSlotName">
      <s:latin typeface="LatinScriptFont" />
      <s:ea typeface="EAScriptFont"/>
      <s:cs typeface="CSFont" />
      <s:font script="Language" typeface="ScriptFont" />
      <!--Additional fonts-->
  </s:fontSlots>
  <!--Additional font slots-->
</s:fontScheme>
```

In an .spfont file, the following placeholders are replaced: 
  
    
    

-  _FontSchemeName_ is the name of the font scheme.
    
  
-  _Slot1_ is the name of the font slot that you want to use as the first block of the font icon in the font scheme picker in the **Change the look** wizard.
    
  
-  _Slot2_ is the name of the font slot that you want to use as the second block of the font icon in the font scheme picker in the **Change the look** wizard.
    
  
-  _FontSlotName_ is the name of the font slot that you are defining (for example, title).
    
  
-  _LatinScriptFont_ is the font to use for Latin scripts. This font is also the fallback font. That is, this is the font that is used for a language that does not have a script that is explicitly set in the font scheme.
    
    > [!NOTE]  
> You must provide additional information to use web fonts in your font scheme. For more information, see the  [Web fonts](#webFont) section in this article.
-  _EAScriptFont_ is the font to use for East Asia scripts. The **<s:ea>** element is not currently used by SharePoint. But, the **<s:ea>** element is still required in the font scheme.
    
  
-  _CSFont_ is the font to use for complex scripts. The **<s:cs>** element is not currently used by SharePoint. But, the **<s:cs>** element is still required in the font scheme.
    
  
-  _Language_ is the language script.
    
  
-  _ScriptFont_ is the font to use for the specified language script.
    
  
The following example shows a portion of an .spfont file. 
  
    
    



```XML

<s:fontScheme name="Georgia" previewSlot1="title" previewSlot2="body" xmlns:s="http://schemas.microsoft.com/sharepoint/">
    <s:fontSlots>
        <s:fontSlot name="title">
            <s:latin typeface="Georgia"/>
            <s:ea typeface=""/>
            <s:cs typeface="Segoe UI Light" />
            <s:font script="Arab" typeface="Tahoma" />
            <s:font script="Deva" typeface="Mangal" />
            <s:font script="Grek" typeface="Segoe UI Light" />
            <s:font script="Hang" typeface="Malgun Gothic" />
            <s:font script="Hans" typeface="Microsoft YaHei" />
            <s:font script="Hant" typeface="Microsoft JhengHei" />
            <s:font script="Hebr" typeface="Tahoma" />
            <s:font script="Hira" typeface="Meiryo" />
            <s:font script="Thai" typeface="Tahoma" />
            <s:font script="Armn" typeface="Tahoma" />
            <s:font script="Beng" typeface="Vrinda" />
            <s:font script="Cher" typeface="Plantagenet Cherokee" />
            <s:font script="Ethi" typeface="Nyala" />
            <s:font script="Geor" typeface="Sylfaen" />
            <s:font script="Gujr" typeface="Shruti" />
            <s:font script="Guru" typeface="Raavi" />
            <s:font script="Knda" typeface="Tunga" />
            <s:font script="Khmr" typeface="DaunPenh" />
            <s:font script="Laoo" typeface="DokChampa" />
            <s:font script="Mlym" typeface="Kartika" />
            <s:font script="Mymr" typeface="Myanmar Text" />
            <s:font script="Orya" typeface="Kalinga" />
            <s:font script="Sinh" typeface="Iskoola Pota" />
            <s:font script="Syrc" typeface="Estrangelo Edessa" />
            <s:font script="Taml" typeface="Latha" />
            <s:font script="Telu" typeface="Gautami" />
            <s:font script="Thaa" typeface="MV Boli" />
            <s:font script="Tibt" typeface="Cordia New" />
            <s:font script="Yiii" typeface="Microsoft Yi Baiti" />
        </s:fontSlot>
…
```

SharePoint 2013 includes support for web fonts. You must provide additional information to use web fonts in your font scheme. For more information, see the  [Web fonts](#webFont) section in this article.
  
    
    

### Web-safe fonts
<a name="websafeFont"> </a>

Web-safe fonts are a set of fonts that are widely used and available on most devices by default. To specify a web-safe font in the font scheme, include the name of the font in the **typeface** attribute of the font slot. The following example shows a web-safe font used in a font scheme.
  
    
    

```XML

<s:fontSlot name="title">
  <s:latin typeface="Georgia"/>
…
</s:fontSlot>
```


### Web fonts
<a name="webFont"> </a>

Web fonts are fonts that are available on the Internet. When a user views a site that uses web fonts, the web browser downloads the necessary font files along with the rest of the page. To specify a web font, you must provide the URL to your web font files in four font formats (for support across browsers), and a small and large thumbnail image to use to render the font names in the font scheme picker. 
  
    
    
The following example describes the information that is required to use a web font in an **<s:latin>** element.
  
    
    



```XML

<s:latin typeface="FontName"
  eotsrc="EotFile"
  woffsrc="WoffFile"
  ttfsrc="TtfFile"
  svgsrc="SvgFile"
  largeimgsrc="LargeImgFile"
  smallimgsrc="SmallImgFile" />

```

In this example of using a web font, the following placeholders would be replaced: 
  
    
    

-  _FontName_ is the name of the web font.
    
  
-  _EotFile_ is the relative URL to the Embedded Open Type font file.
    
  
-  _WoffFile_ is the relative URL to the Web Open Font Format font file.
    
  
-  _TtfFile_ is the relative URL to the TrueType font file.
    
  
-  _SvgFile_ is the relative URL to the Scalable Vector Graphics font file.
    
  
-  _LargeImgFile_ is the relative URL to the large thumbnail image that you want to use in the font scheme picker.
    
  
-  _SmallImgFile_ is the relative URL to the small thumbnail image that you want to use in the font scheme picker.
    
  

### Font slots
<a name="fontSlot"> </a>

Table 1 describes the available font slots and where they are used in a page. 
  
    
    

**Table 1. Font slots**


|**Font Slot Name**|**Description**|
|:-----|:-----|
|title |Used for the page title. |
|navigation |Used for the horizontal and vertical navigation elements on the page. |
|large-heading |Used for the H1 heading. |
|heading |Used for H2 and H3 headings, Web Part titles, dialog box titles, and callout titles. |
|small-heading |Used for H4 headings. |
|large-body |Used for large body text (15 pixels and 19 pixels). |
|body |The base font that is used everywhere else on the page. |
   

## Additional resources
<a name="bk_addresources"> </a>


-  [Themes overview for SharePoint 2013](themes-overview-for-sharepoint-2013.md)
    
  
-  [How to: Deploy a custom theme in SharePoint 2013](how-to-deploy-a-custom-theme-in-sharepoint-2013.md)
    
  
-  [Upgrade custom themes and CSS to SharePoint 2013](upgrade-custom-themes-and-css-to-sharepoint-2013.md)
    
  
-  [How to: Create a master page preview file in SharePoint 2013](how-to-create-a-master-page-preview-file-in-sharepoint-2013.md)
    
  
-  [SharePoint Team Blog: Show off your style with SharePoint theming](http://blogs.office.com/b/sharepoint/archive/2012/10/29/show-off-your-style-with-sharepoint-theming.aspx)
    
  
-  [SharePoint 2013 Design Manager branding and design capabilities](sharepoint-2013-design-manager-branding-and-design-capabilities.md)
    
  

  
    
    

