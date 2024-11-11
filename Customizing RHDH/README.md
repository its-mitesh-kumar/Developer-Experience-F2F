### Customizing theme mode color palettes

```
branding:
    theme:
      light:
        palette:
          primary:
            main: <light_primary_color> 1
          navigation:
            indicator: <light_indicator_color> 2
        pageTheme:
          default:
            backgroundColor: [<light_background_color_1>, <light_background_color_2>] 3
            fontColor: "<default_light_font_color>" 4
            shape: none 5
          apis: 6
            backgroundColor: "<apis_light_background_color>"
            fontColor: "<apis_light_font_color>"
            shape: none


```
   1. The main primary color for the light color palette, for example, #ffffff or white
   2. The color of the navigation indicator for the light color palette, which is a vertical bar that indicates the selected tab in the navigation panel, for example, #FF0000 or red
   3. The background color for the default page theme for the light color palette, for example, #ffffff or white
   4. The color of the text in the page header, for example, #000000 or black
   5. The pattern on the page header, for example, wave, round, or none
   6. The yaml header for a specific page theme configuration, for example, apis, home

### Customizing Font 

```
      typography:
        fontFamily: "cursive"
        htmlFontSize: 11 #smaller is bigger
        h1:
          fontFamily: "cursive"
          fontSize: 40
        h2:
          fontFamily: "cursive"
          fontSize: 30
```

Example Config 

```
branding:
  theme:
    light:
      palette:
        primary:
          main: '#33ff8d'
        navigation:
          indicator: '#ffac33'
      pageTheme:
        default:
          backgroundColor: ['#ff33d4']
          fontColor: '#ff3352'
          shape: wave
      typography:
        fontFamily: "cursive"
        htmlFontSize: 11 #smaller is bigger
        h1:
          fontFamily: "cursive"
          fontSize: 40
        h2:
          fontFamily: "cursive"
          fontSize: 30
```

### Make your Developer Hub instance look like a standard Red Hat Developer Hub instance

```app:
  branding:
    theme:
      light:
        variant: "rhdh"
        mode: "light"
      dark:
        variant: "rhdh"
        mode: "dark"
```
### Make your Developer Hub instance look like a standard Backstage instance

```
app:
  branding:
    theme:
      light:
        variant: "backstage"
        mode: "light"
      dark:
        variant: "backstage"
        mode: "dark"
```

### Customizing Sidebar

```
dynamicPlugins:
  rootDirectory: dynamic-plugins-root
  frontend:
    default.main-menu-items:
      menuItems:
        default.list:
          title: References
          icon: bookmarks
        default.my-group:
          parent: default.list
        default.learning-path:
          parent: default.list
```

### Customize the cards on the homepage (add, rearrange).

[Guide](https://github.com/janus-idp/backstage-showcase/blob/main/plugins/dynamic-home-page/docs/customization.md)
```
    dynamicPlugins:
      rootDirectory: dynamic-plugins-root
      frontend:
        default.main-menu-items:
          menuItems:
            default.list:
              title: References
              icon: bookmarks
            default.my-group:
              parent: default.list
            default.learning-path:
              parent: default.list
        janus-idp.backstage-plugin-dynamic-home-page:
          mountPoints:
            - mountPoint: home.page/cards
              importName: SearchBar
              config:
                layouts:
                  xl: { w: 10, h: 1, x: 1 }
                  lg: { w: 10, h: 1, x: 1 }
                  md: { w: 10, h: 1, x: 1 }
                  sm: { w: 10, h: 1, x: 1 }
                  xs: { w: 12, h: 1 }
                  xxs: { w: 12, h: 1 }
            - mountPoint: home.page/cards
              importName: CatalogStarredEntitiesCard
              config:
                layouts:
                  xl: { w: 6, h: 4 }
                  lg: { w: 6, h: 4 }
                  md: { w: 6, h: 4 }
                  sm: { w: 12, h: 4 }
                  xs: { w: 12, h: 4 }
                  xxs: { w: 12, h: 4 }
            - mountPoint: home.page/cards
              importName: Placeholder
              config:
                layouts:
                  xl: { w: 1, h: 1 }
                  lg: { w: 1, h: 1 }
                  md: { w: 1, h: 1 }
                  sm: { w: 1, h: 1 }
                  xs: { w: 1, h: 1 }
                  xxs: { w: 1, h: 1 }
                props:
                  showBorder: true
                  debugContent: '1'
            - mountPoint: home.page/cards
              importName: Placeholder
              config:
                layouts:
                  xl: { w: 1, h: 1, x: 1 }
                  lg: { w: 1, h: 1, x: 1 }
                  md: { w: 1, h: 1, x: 1 }
                  sm: { w: 1, h: 1, x: 1 }
                  xs: { w: 1, h: 1, x: 1 }
                  xxs: { w: 1, h: 1, x: 1 }
                props:
                  showBorder: true
                  debugContent: '2'
            - mountPoint: home.page/cards
              importName: Placeholder
              config:
                layouts:
                  xl: { w: 1, h: 1 }
                  lg: { w: 1, h: 1 }
                  md: { w: 1, h: 1 }
                  sm: { w: 1, h: 1 }
                  xs: { w: 1, h: 1 }
                  xxs: { w: 1, h: 1 }
                props:
                  showBorder: true
                  debugContent: '3'

            - mountPoint: home.page/cards
              importName: Placeholder
              config:
                layouts:
                  xl: { w: 12, h: 1 }
                  lg: { w: 12, h: 1 }
                  md: { w: 12, h: 1 }
                  sm: { w: 12, h: 1 }
                  xs: { w: 12, h: 1 }
                  xxs: { w: 12, h: 1 }
                props:
                  showBorder: true
                  debugContent: '4'

            - mountPoint: home.page/cards
              importName: Placeholder
              config:
                layouts:
                  xl: { w: 1, h: 1 }
                  lg: { w: 1, h: 1 }
                  md: { w: 1, h: 1 }
                  sm: { w: 1, h: 1 }
                  xs: { w: 1, h: 1 }
                  xxs: { w: 1, h: 1 }
                props:
                  showBorder: true
                  debugContent: '5'
            - mountPoint: home.page/cards
              importName: Placeholder
              config:
                layouts:
                  xl: { w: 1, h: 1, x: 1 }
                  lg: { w: 1, h: 1, x: 1 }
                  md: { w: 1, h: 1, x: 1 }
                  sm: { w: 1, h: 1, x: 1 }
                  xs: { w: 1, h: 1, x: 1 }
                  xxs: { w: 1, h: 1, x: 1 }
                props:
                  showBorder: true
                  debugContent: '6'
            - mountPoint: home.page/cards
              importName: FeaturedDocsCard
            - mountPoint: home.page/cards
              importName: Headline
              config:
                layouts:
                  xl: { h: 1 }
                  lg: { h: 1 }
                  md: { h: 1 }
                  sm: { h: 1 }
                  xs: { h: 1 }
                  xxs: { h: 1 }
                props:
                  title: Important info
            - mountPoint: home.page/cards
              importName: Headline
              config:
                layouts:
                  xl: { h: 1 }
                  lg: { h: 1 }
                  md: { h: 1 }
                  sm: { h: 1 }
                  xs: { h: 1 }
                  xxs: { h: 1 }
                props:
                  title: Important info
                  align: right
            - mountPoint: home.page/cards
              importName: MarkdownCard
              config:
                layouts:
                  xl: { w: 6, h: 3 }
                  lg: { w: 6, h: 3 }
                  md: { w: 6, h: 3 }
                  sm: { w: 6, h: 3 }
                  xs: { w: 6, h: 3 }
                  xxs: { w: 6, h: 3 }
                props:
                  title: Company links
                  content: |
                    ### RHDH

                    * [Website](https://developers.redhat.com/rhdh/overview)
                    * [Documentation](https://docs.redhat.com/en/documentation/red_hat_developer_hub/)
                    * [GitHub Showcase](https://github.com/janus-idp/backstage-showcase)
                    * [GitHub Plugins](https://github.com/janus-idp/backstage-plugins)
                    * [Website](https://developers.redhat.com/rhdh/overview)
                    * [Documentation](https://docs.redhat.com/en/documentation/red_hat_developer_hub/)
                    * [GitHub Showcase](https://github.com/janus-idp/backstage-showcase)
                    * [GitHub Plugins](https://github.com/janus-idp/backstage-plugins)
            - mountPoint: home.page/cards
              importName: Markdown
              config:
                layouts:
                  xl: { w: 6, h: 3, x: 6 }
                  lg: { w: 6, h: 3, x: 6 }
                  md: { w: 6, h: 3, x: 6 }
                  sm: { w: 6, h: 3, x: 6 }
                  xs: { w: 6, h: 3, x: 6 }
                  xxs: { w: 6, h: 3, x: 6 }
                props:
                  title: Important company links
                  content: |
                    ### RHDH

                    * [Website](https://developers.redhat.com/rhdh/overview)
                    * [Documentation](https://docs.redhat.com/en/documentation/red_hat_developer_hub/)
                    * [GitHub Showcase](https://github.com/janus-idp/backstage-showcase)
                    * [GitHub Plugins](https://github.com/janus-idp/backstage-plugins)
                    * [Website](https://developers.redhat.com/rhdh/overview)
                    * [Documentation](https://docs.redhat.com/en/documentation/red_hat_developer_hub/)
                    * [GitHub Showcase](https://github.com/janus-idp/backstage-showcase)
                    * [GitHub Plugins](https://github.com/janus-idp/backstage-plugins)
            - mountPoint: home.page/cards
              importName: QuickAccessCard
              config:
                layouts:
                  xl: { h: 8 }
                  lg: { h: 8 }
                  md: { h: 8 }
                  sm: { h: 8 }
                  xs: { h: 8 }
                  xxs: { h: 8 }

```