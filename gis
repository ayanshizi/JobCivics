<!DOCTYPE html>
<html>
  <head>
    <meta http-equiv="content-type" content="text/html; charset=utf-8"/>
    <meta name="viewport" content="initial-scale=1.0, maximum-scale=1.0, user-scalable=no"/>
    <title></title>
    <link rel="stylesheet" type="text/css" href="//cdn-a.arcgis.com/cdn/1859746/js/arcgisonline/css/common.css">

    <link rel="stylesheet" type="text/css" href="//cdn-a.arcgis.com/cdn/1859746/js/arcgisonline/css/calcite.css">
    <link rel="stylesheet" type="text/css" href="//cdn-a.arcgis.com/cdn/1859746/js/arcgisonline/css/ago.css">
    <link rel="stylesheet" type="text/css" href="//cdn-a.arcgis.com/cdn/1859746/js/arcgisonline/css/widgets-1.css">
    <link rel="stylesheet" type="text/css" href="//cdn-a.arcgis.com/cdn/1859746/js/arcgisonline/css/widgets-2.css">

    <link rel="stylesheet" type="text/css" href="//cdn-a.arcgis.com/cdn/1859746/js/arcgisonline/css/jsapi-map.css">
    <link rel="stylesheet" type="text/css" href="//cdn-a.arcgis.com/cdn/1859746/js/arcgisonline/css/map.css">
    <link rel="stylesheet" type="text/css" href="//cdn-a.arcgis.com/cdn/1859746/js/jsapi/esri/dijit/css/Tags.css">
    <link rel="stylesheet" type="text/css" href="//cdn-a.arcgis.com/cdn/1859746/js/reusables/dist/ItemBrowser/mapviewer.css">
    <!--[if lte IE 9]>
    <link rel="stylesheet" type="text/css" href="//cdn-a.arcgis.com/cdn/1859746/js/jsapi/esri/dijit/geoenrichment/themes/common/main.css">
    <link rel="stylesheet" type="text/css" href="//cdn-a.arcgis.com/cdn/1859746/js/jsapi/esri/css/calcite/calcite.css">
    <![endif]-->
    <script type="text/javascript" src="../js/arcgisonline/config.js">
    </script>
    <script type="text/javascript" src="//cdn-a.arcgis.com/cdn/1859746/js/jsapi/dojo/dojo.js">
    </script>
    <script type="text/javascript" src="//cdn-a.arcgis.com/cdn/1859746/js/arcgisonline/base.js">
    </script>
    <script type="text/javascript" src="//cdn-a.arcgis.com/cdn/1859746/js/arcgisonline/mapmain.js">
    </script>
    <script>
      var isEmbedded = null, embeddedSource = null, embeddedOrigin = null; //globals in viewer?
      require(["arcgisonline/arcgisonline", "arcgisonline/viewer"], function() {
        require([
        "arcgisonline/esriGeowConfig",
        "arcgisonline/map/main",
        "dojo/dom",
        "dojo/dom-style",
        "dojo/has",
        "dojo/query",
        "dojo/sniff",
        "dijit/registry",
        "dojo/i18n!arcgisonline/nls/arcgisonline",
        "dojo/ready"
        ], function (esriGeowConfig, mapmain, dom, domStyle, has, query, sniff, registry, i18n, ready) {

          ready(init);

          function init(){

            if (has("ie") < 7) {
              window.location = "../ie6.html";
            }

            esri.i18nBundle = i18n;

            document.title = esriGeowConfig.portalName || "ArcGIS";
            dom.byId("newMapLabel").innerHTML = esri.i18nBundle.siteHeader.newMap;
            dom.byId("recentMapsLabel").innerHTML = esri.i18nBundle.siteHeader.newMap;
            dom.byId("webmap-recentMap-title").innerHTML = esri.i18nBundle.siteHeader.recentMaps;
            dom.byId("modifyMapLabel").innerHTML = esri.i18nBundle.siteHeader.modifyMap || "Modify Map";
            //dom.byId("webmap-title-edit").innerHTML = esri.i18nBundle.common.edit;
            dom.byId("webmap-title-edit").title = esri.i18nBundle.viewer.main.editMapTitle;
            dom.byId("webmap-title-edit-save").innerHTML = esri.i18nBundle.common.save;
            dom.byId("webmap-title-edit-cancel").innerHTML = esri.i18nBundle.common.cancel;

            registry.byId("webmap-details").set('label', esri.i18nBundle.viewer.detailsBtn);
            registry.byId("webmap-details").set('title', esri.i18nBundle.viewer.detailsHover);
            registry.byId("webmap-add").set('label', esri.i18nBundle.viewer.addBtn);
            registry.byId("webmap-add").set('title', esri.i18nBundle.viewer.addHover);
            registry.byId("webmap-search-layers").set('label', esri.i18nBundle.viewer.searchForLayers);
            registry.byId("webmap-add-mapnotes").set('label', esri.i18nBundle.viewer.addMapNotes);
            registry.byId("webmap-add-layer-file").set('label', esri.i18nBundle.viewer.addLayerFromFile);
            registry.byId("webmap-add-layer-url").set('label', esri.i18nBundle.viewer.addLayerFromWeb);
            registry.byId("webmap-add-esri-maplayers").set('label', esri.i18nBundle.viewer.browseForLayers);
            registry.byId("webmap-add-provisionedListings").set('label', esri.i18nBundle.viewer.browseProvisionedListings);
            registry.byId("webmap-edit").set('label', esri.i18nBundle.viewer.editBtn);
            registry.byId("webmap-edit").set('title', esri.i18nBundle.viewer.editHover);
            registry.byId("webmap-analysis").set('label', esri.i18nBundle.viewer.analysisBtn);
            registry.byId("webmap-analysis-analysis").set('label', esri.i18nBundle.viewer.analysisBtn);
            registry.byId("webmap-analysis-history").set('label', esri.i18nBundle.viewer.analysisHistory);
            registry.byId("webmap-analysis").set('title', esri.i18nBundle.viewer.analysisBtnHover);

            registry.byId("webmap-basemap").set('label', esri.i18nBundle.viewer.basemapBtn);
            registry.byId("webmap-basemap").set('title', esri.i18nBundle.viewer.basemapHover);
            registry.byId("webmap-save").set('label', esri.i18nBundle.viewer.saveBtn);
            registry.byId("webmap-save").set('title', esri.i18nBundle.viewer.saveHover);
            registry.byId("webmap-save-save").set('label', esri.i18nBundle.viewer.save);
            registry.byId("webmap-save-saveas").set('label', esri.i18nBundle.viewer.saveAs);
            registry.byId("webmap-share").set('label', esri.i18nBundle.viewer.shareBtn);
            registry.byId("webmap-share").set('title', esri.i18nBundle.viewer.shareHover);
            registry.byId("webmap-print").set('label', esri.i18nBundle.viewer.printBtn);
            registry.byId("webmap-print").set('title', esri.i18nBundle.viewer.printHover);
            registry.byId("webmap-print-templates").set('label', esri.i18nBundle.viewer.printBtn);
            registry.byId("webmap-print-templates").set('title', esri.i18nBundle.viewer.printHover);
            registry.byId("webmap-directions").set('label', esri.i18nBundle.viewer.directionsBtn);
            registry.byId("webmap-directions").set('title', esri.i18nBundle.viewer.directionsHover);
            registry.byId("webmap-measure").set('label', esri.i18nBundle.viewer.measureBtn);
            registry.byId("webmap-measure").set('title', esri.i18nBundle.viewer.measureHover);
            registry.byId("webmap-bookmarks").set('label', esri.i18nBundle.viewer.bookmarksBtn);
            registry.byId("webmap-bookmarks").set('title', esri.i18nBundle.viewer.bookmarksHover);
            dom.byId("noData1").innerHTML = esri.i18nBundle.viewer.noData;
            dom.byId("noData2").innerHTML = esri.i18nBundle.viewer.noData;
            dom.byId("noData3").innerHTML = esri.i18nBundle.viewer.noData;
            dom.byId("noData4").innerHTML = esri.i18nBundle.viewer.noData;
            registry.byId("timeSliderSettingsButton").set('title', esri.i18nBundle.viewer.configureTime);
            dom.byId("measureLabel").innerHTML = esri.i18nBundle.viewer.measureTitle;
            dom.byId("measureClose").title = esri.i18nBundle.common.close;
            dom.byId("measureClose").alt = esri.i18nBundle.common.close;
            dom.byId("bookmarksLabel").innerHTML = esri.i18nBundle.viewer.bookmarksTitle;
            dom.byId("bookmarksClose").title = esri.i18nBundle.common.close;
            dom.byId("bookmarksClose").alt = esri.i18nBundle.common.close;

            query(".homeHome", this.domNode)[0].innerHTML = esri.i18nBundle.siteHeader.home_link;
            query(".homeOverview", this.domNode)[0].innerHTML = esri.i18nBundle.siteHeader.overview;
            query(".homePricing", this.domNode)[0].innerHTML = esri.i18nBundle.siteHeader.pricing;
            query(".homeGallery", this.domNode)[0].innerHTML = esri.i18nBundle.siteHeader.gallery;
            query(".homeScene", this.domNode)[0].innerHTML = esri.i18nBundle.siteHeader.scene;
            query(".homeGroups", this.domNode)[0].innerHTML = esri.i18nBundle.siteHeader.groups;
            query(".homeMyContent", this.domNode)[0].innerHTML = esri.i18nBundle.siteHeader.myContent;
            query(".homeMyOrg", this.domNode)[0].innerHTML = esri.i18nBundle.siteHeader.myAccount;
            query(".homeHelp", this.domNode)[0].innerHTML = esri.i18nBundle.siteHeader.support;

            dom.byId("login-link").innerHTML = "<span class=\"profile-icon\"></span>" + esri.i18nBundle.siteHeader.signIn;
          //        dom.byId("logged-in-myProfile").innerHTML = esri.i18nBundle.siteHeader.myProfile;
            dom.byId("logged-in-help").innerHTML = esri.i18nBundle.siteHeader.help;
            query('#logged-in-help').removeClass('hide');
            // need to have self to decide if we show adminhelp
            dom.byId("logged-in-adminhelp").innerHTML = esri.i18nBundle.siteHeader.adminGuide;
            dom.byId("logged-in-signOut").innerHTML = esri.i18nBundle.siteHeader.signOut;
            domStyle.set(dom.byId("header-controls"),"display","inline-block");

            domStyle.set('page-border', 'visibility', 'visible');

            //For Septemper 2014 remove web scene, and scene layer from filters
            if (!esriGeowConfig.sceneViewerEnabled) {
              query(".homeScene", this.domNode).style("display", "none");
            }

            if (has("ios") || has("android")) {
              // no file browsing available
              domStyle.set(registry.byId("webmap-add-layer-file").domNode, "display", "none");
            }

            mapmain.init();
          }
      });
    });


    </script>
    <style type="text/css">
      #webmap-header, #toolbar, #leftDiv {
        -webkit-backface-visibility: hidden;
      }

      html, body {
        height: 100%;
        width: 100%;
        margin: 0;
        padding: 0;
        overflow: hidden;
      }

      body #page-border {
        min-width: 1200px; /* make it so big that all languages fit without the edit button */
        overflow: hidden;
      }

      #dijit_layout__Gutter_3, #dijit_layout__Gutter_2 {
        width: 0;
      }

      .esri #main-content {
        margin-bottom: 0;
      }

      /* default close icon is not very visible */
      .infowindow .window .top .right .user .titlebar .hide .sprite {
        margin-top: -908px;
      }

      #overviewMap .map .logo-sm, #overviewMap .map .logo-med, #overviewMap .map .bingLogo-lg {
        display: none;
      }

      /* dojo 1.8 patch for RTL TextInput */
      .dj_ie7 .dijitInputContainer {
          float: none !important;
      }

    </style>
    <!--[if lt IE 9]>
    <style type="text/css">
      .esriTags .dijitReset .dijitInputInner {
        line-height: 16px;
      }
    </style>
    <![endif]-->
 </head>
  <body class="soria esri mapviewer">
    <div id="page-border" dojotype="dijit.layout.BorderContainer" gutters="false" design="headline" class="noBorder" onClick="">
      <div id="headerBanner" dojotype="arcgisonline.sharing.dijit.ClassificationBanner" region="top">
      </div>
      <div id="main-content" dojotype="dijit.layout.BorderContainer" gutters="true" design="headline" region="center" style="padding:0 2px 1px 0;">
        <div id="webmap-header" class="webmapHeader top-nav" dojotype="dijit.layout.ContentPane" region="top" style="height:60px">

            <h1 id="webmap-title" class="avenir-light font-size-1 esriFloatLeading leader-1" style="width:100px;">
              <div id="webmap-title-tableDiv">
                <table id="webmap-title-table" cellpadding="0" cellspacing="0">
                  <tbody>
                  <tr>
                    <td>
                      <div id="webmap-title-text" class="text-ellipsis" style="visibility:hidden;"></div>
                    </td>
                    <td width="100%">
                      <button id="webmap-title-edit" class="icon-ui-edit" style="visibility:hidden; padding-top:5px;"></button>
                    </td>
                  </tr>
                  </tbody>
                </table>
              </div>
              <div id="webmap-title-edit-inputGrp" style="display:none;">
                <table cellpadding="0" cellspacing="0">
                  <tbody>
                  <tr>
                    <td style="line-height:1em;">
                      <input id="webmap-title-edit-input"/>
                    </td>
                    <td style="line-height:1em;">
                      <button id="webmap-title-edit-save" class="btn-green"></button>
                    </td>
                    <td style="line-height:1em;">
                      <button id="webmap-title-edit-cancel" class=""></button>
                    </td>
                  </tr>
                  </tbody>
                </table>
              </div>
              <span id="webmap-title-sizing" style="visibility:hidden;white-space: nowrap;"></span>
            </h1>

          <div class="siteHeader esriFloatTrailing">

            <!-- RTL + ul + IE doesn't work -->
            <div id="header-controls" class="esriFloatTrailing" style="display:none;">

              <div id="header_map_newMap" class="map_nav esriFloatLeading esriTrailingMargin1">
                <a id="webmap-newMap" class="top-nav-link" href="JavaScript:void(0);"><span id="newMapLabel"></span></a>
              </div>

              <div id="header_map_recentMaps" class="map_nav esriFloatLeading esriTrailingMargin1" style="display:none;">
                <div id="recentMaps-navigation" class="dropdown esriFloatTrailing">
                  <a id="webmap-recentMaps" class="dropdown-btn top-nav-link">
                    <span id="recentMapsLabel"></span>
                  </a>
                  <div class="dropdown-menu js-dropdown-menu dropdown-right">
                    <a id="webmap-recentMap-new-link" class="dropdown-link"></a>
                    <span id="webmap-recentMap-title" class="dropdown-link dropdown-title" style="display:none" href="#" ></span>
                    <a id="webmap-recentMap-0-link" class="webmapRecentMap dropdown-link" style="display:none"></a>
                    <a id="webmap-recentMap-1-link" class="webmapRecentMap dropdown-link" style="display:none"></a>
                    <a id="webmap-recentMap-2-link" class="webmapRecentMap dropdown-link" style="display:none"></a>
                    <a id="webmap-recentMap-3-link" class="webmapRecentMap dropdown-link" style="display:none"></a>
                    <a id="webmap-recentMap-4-link" class="webmapRecentMap dropdown-link" style="display:none"></a>
                  </div>
                </div>
              </div>

              <div id="header_map_modifyMap" class="map_nav esriFloatLeading esriTrailingMargin1" style="display:none;">
                <a id="webmap-modifyMap" class="top-nav-link" href="JavaScript:void(0);"><span id="modifyMapLabel"></span></a>
              </div>

              <div id="header_map_presentation" class="map_nav esriFloatLeading esriTrailingMargin1" style="display:none;">
                <a id="webmap-presentation" class="top-nav-link" href="JavaScript:void(0);"><span id="presentationLabel"></span></a>
              </div>

              <div id="header_map_signin" class="status esriFloatTrailing">

                <!-- Log in -->
                <div id="logged-out-navigation" class="dropdown-navigation hide esriFloatTrailing esriAlignTrailing">
                  <a id="login-link" class="top-nav-link icon-ui-user link-gray" href="JavaScript:void(0);">
                  </a>
                </div>

                <!-- User Menu -->
                <div class="dropdown right" id="logged-in-navigation">
                  <a href="#" id="logged-in-navigation-link" class="top-nav-link dropdown-btn top-nav-username text-ellipsis">
                    <img id="profileImgSmall" width="16" height="16" alt="">
                    <span id="username"></span>
                  </a>
                  <div class="dropdown-menu dropdown-right">
                    <a id="profileLink" class="dropdown-link">
                      <img id="dropdown-image" width="32" height="32" class="padding-right-half padding-left-0 left">
                      <div id="logged-in-myProfile" class="text-ellipsis dropdown-username"></div>
                    </a>
                    <a class="dropdown-link dropdown-link-external hide" id="esri-community-link"></a>
                    <a class="dropdown-link dropdown-link-external hide" id="my-esri-link"></a>
                    <a class="dropdown-link dropdown-link-external hide" id="training-link"></a>
                    <a class="dropdown-link hide" id="trial-download-link"></a>
                    <a class="dropdown-link hide" id="accountSwitcher-link"></a>
                    <a class="dropdown-link loggedInHelp" id="logged-in-help"></a>
                    <a class="dropdown-link loggedInAdminHelp hide" id="logged-in-adminhelp"></a>
                    <a class="dropdown-link loggedInSignout" id="logged-in-signOut"></a>
                  </div>
                </div>

              </div>
          	</div>
          </div>
        </div>
        <div id="webmap-viewer" dojotype="dijit.layout.BorderContainer" gutters="true" design="headline" region="center">
          <div id="toolbar" class="webmapToolbar" dojoType="dijit.layout.ContentPane" region="top">
            <div id="dijitToolbar" dojotype="dijit.Toolbar" class="esriToolbar">
              <div id="webmap-toolbar-leftCorner" class="webmapToolbarLeftCorner esriFloatLeading">
              </div>
              <div id="webmap-toolbar-left" class="esriFloatLeading">
                <button dojotype="dijit.form.ToggleButton" id="webmap-details" iconclass="esriContentsIcon" title="">
                </button>
                <button dojotype="dijit.form.DropDownButton" id="webmap-add" iconclass="esriAddContentIcon" title="" style="margin-top:1px;">
                  <div dojotype="dijit.Menu">
                    <div id="webmap-search-layers" dojoType="dijit.MenuItem" label="" onclick="arcgisonline.map.leftPanel.openLeftAddContentPanel()">
                    </div>
                    <div id="webmap-add-esri-maplayers" dojoType="dijit.MenuItem" label="" onclick="arcgisonline.map.main.browseLayers()" style="display:none;">
                    </div>
                    <div id="webmap-add-provisionedListings" dojoType="dijit.MenuItem" label="" onclick="arcgisonline.map.main.browseProvisionedListings()" style="display:none;">
                    </div>
                    <div id="webmap-add-layer-url" dojoType="dijit.MenuItem" label="" onclick="arcgisonline.map.main.addLayerFromUrl()">
                    </div>
                    <div id="webmap-add-layer-file" dojoType="dijit.MenuItem" label="" onclick="arcgisonline.map.main.addLayerFromFile()">
                    </div>
                    <div id="webmap-add-mapnotes" dojoType="dijit.MenuItem" label="" onclick="arcgisonline.map.mapNotes.addMapNotesLayer()">
                    </div>
                  </div>
                </button>
                <span class="dijit dijitReset dijitLeft dijitInline dijitToggleButton esriTrailingMargin02px" style="height:20px;border-right:1px solid #636c6c;margin-top:2px;"></span>

                <button dojotype="dijit.form.ToggleButton" id="webmap-edit" iconclass="esriEditIcon" title="" style="display:none;">
                </button>
                <button dojotype="dijit.form.ToggleButton" id="webmap-basemap" iconclass="esriBasemapIcon" title="">
                </button>
                <span id="webmap-spacer2" class="dijit dijitReset dijitLeft dijitInline dijitToggleButton esriTrailingMargin02px" style="height:20px;border-right:1px solid #636c6c;margin-top:2px;"></span>
               <button dojotype="dijit.form.DropDownButton" id="webmap-analysis" iconclass="menuIconPerformAnalysis" title="" style="margin-top:2px;;display:none;">
                  <div dojotype="dijit.Menu" id="webmap-analysis-menu">
                    <div id="webmap-analysis-analysis" dojoType="dijit.MenuItem" label="">
                    </div>
                    <div id="webmap-analysis-history" dojoType="dijit.MenuItem" label="">
                    </div>
                  </div>
                </button>
              </div>
              <div id="webmap-toolbar-rightCorner" class="webmapToolbarRightCorner esriFloatTrailing">
              </div>
              <div id="webmap-toolbar-right" class="webmapToolbarRight esriFloatTrailing">
                <div id="locationDiv" class="webmapLocationDiv esriFloatTrailing esriPositionRight0">
                </div>
              </div>
              <div id="webmap-toolbar-center" class="esriFloatTrailing" style="visibility:hidden;">
                <button dojotype="dijit.form.DropDownButton" id="webmap-save" iconclass="esriSaveIcon" title="" style="margin-top:1px;">
                  <div dojotype="dijit.Menu" id="webmap-save-menu">
                    <div id="webmap-save-save" dojoType="dijit.MenuItem" label="" onclick="arcgisonline.map.storage.saveWebMapClick('save')">
                    </div>
                    <div id="webmap-save-saveas" dojoType="dijit.MenuItem" label="" onclick="arcgisonline.map.storage.saveWebMapClick('saveAs')">
                    </div>
                  </div>
                </button>
                <button dojotype="dijit.form.Button" type="button" id="webmap-share" iconclass="esriLinkIcon" title="">
                </button>
                <button dojotype="dijit.form.Button" type="button" id="webmap-print" iconclass="esriPrintIcon" title="">
                </button>
                <button dojotype="dijit.form.DropDownButton" id="webmap-print-templates" iconclass="esriPrintIcon" title="" style="margin-top:1px;">
                  <div dojotype="dijit.Menu" id="webmap-print-templates-menu">
                  </div>
                </button>
                <span id="webmap-spacer3" class="dijit dijitReset dijitLeft dijitInline dijitToggleButton esriTrailingMargin02px" style="height:20px;border-right:1px solid #636c6c;margin-top:2px;"></span>
                <button dojotype="dijit.form.ToggleButton" id="webmap-directions" iconclass="esriDirectionsIcon" title="" style="display:none;">
                </button>
                <button dojotype="dijit.form.ToggleButton" id="webmap-measure" iconclass="esriMeasureIcon" title="">
                </button>
                <button dojotype="dijit.form.ToggleButton" id="webmap-bookmarks" iconclass="esriBookmarkIcon" title="">
                </button>
              </div>
            </div>
          </div>
          <!-- toolbar -->
          <div id="leftDiv" dojotype="dijit.layout.BorderContainer" region="leading" splitter="true" minSize="200">
            <div id="leftPanelDiv" dojotype="dijit.layout.BorderContainer" region="center">
              <div id="leftContentPanel" dojotype="dijit.layout.BorderContainer" jsid="stackContainer" region="center" style="left:0; top:28px; right:0; bottom:5px;">
                <div dojotype="arcgisonline.map.dijit.LeftPanel" region="top" jsid="leftPanel" style="width: 0px; height: 0px;">
                </div>
              </div>
            </div>
          </div>
          <div id="rightDiv" dojotype="dijit.layout.BorderContainer" region="center" design="headline" gutters="false">
            <div id="noDataDiv">
              <div id="noData1" class="noData">
              </div>
              <div id="noData2" class="noData">
              </div>
              <div id="noData3" class="noData">
              </div>
              <div id="noData4" class="noData">
              </div>
            </div>
            <div id="mapDiv" dojotype="dijit.layout.BorderContainer" region="center" gutters="false" design="headline">
              <!-- hard code to LTR -->
              <div id="map" dojotype="dijit.layout.ContentPane" region="center" style="overflow:hidden; top:33px;" dir="ltr" class="esriLtr">
                <div id="copyrightDiv">
                </div>
                <div id="mdSlider"></div>
              </div>
              <!-- hard code to LTR -->
              <div id="timeDiv" style="display:none;" dojotype="dijit.layout.ContentPane" region="bottom" dir="ltr">
                <table id="timeDivTable">
                  <tbody>
                    <tr>
                      <td>
                        <div id="timeSliderDiv">
                        </div>
                      </td>
                      <td>
                        <div id="timeSliderSettingsButton" dojoType="dijit.form.Button" type="button" iconclass="esriTimeConfigIcon" showLabel="false">
                          &nbsp;
                        </div>
                      </td>
                    </tr>
                    <tr>
                      <td colspan="2">
                        <div style="width:100%;">
                          <div id="timeSliderDesc" style="float:left">
                            &nbsp;
                          </div>
                        </div>
                      </td>
                    </tr>
                  </tbody>
                </table>
              </div>
            </div>
            <!-- mapDiv -->
            <div id="bottomDiv" dojotype="dijit.layout.BorderContainer" region="bottom" gutters="false" design="headline" splitter="true">
              <div id="tableDiv" dojotype="dijit.layout.BorderContainer" region="center" gutters="false" design="headline" splitter="false">
                <div id="tableContainer" dojotype="dijit.layout.ContentPane" region="center">
                  <div id="featureTable"></div>
                </div>
              </div>
              <div id="geocodeDiv" dojotype="dijit.layout.BorderContainer" region="center" gutters="false" design="headline" splitter="false">
                <div dojotype="dijit.layout.ContentPane" id="geocodeReviewContPane" region="center">
                  <div id="geocodeReviewDiv">
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <!-- webmap-viewer -->
      </div>
      <!-- main-content -->
      <div dojotype="dijit.layout.ContentPane" region="bottom" style="margin:0; padding:0;">
        <div id="footerBanner" dojotype="arcgisonline.sharing.dijit.ClassificationBanner">
        </div>
      </div>
    </div>
    <!-- page-border -->
    <div id="basemap-gallery" jsId="basemap-gallery" dojoType="arcgisonline.sharing.dijit.BasemapGalleryGrid" sortField="'name'" groupQuery="esriGeowConfig.basemapGalleryGroupQuery">
    </div>
    <div id="measureDiv">
      <div>
        <div class="esriFloatTrailing">
          <A id="measureClose" href="JavaScript:arcgisonline.map.main.hideMeasureTool('closeIcon');" title="" alt=""></A>
        </div>
        <div class="esriFloatLeading">
          <span style="font-weight: bold;" id="measureLabel"></span>
        </div>
      </div>
      <div style="clear:both;">
      </div>
      <div>
        <hr/>
      </div>
      <div id="measureToolDiv">
      </div>
    </div>
    <div id="bookmarksDiv">
      <div>
        <div class="esriFloatTrailing">
          <A id="bookmarksClose" href="JavaScript:arcgisonline.map.main.hideBookmarksTool('closeIcon');" title="" alt=""></A>
        </div>
        <div class="esriFloatLeading">
          <span style="font-weight: bold;" id="bookmarksLabel"></span>
        </div>
      </div>
      <div style="clear:both;">
      </div>
      <div>
        <hr/>
      </div>
      <div id="bookmarksToolDiv" class="esriTrailingMargin05">
      </div>
    </div>

    <div id="header" class="padding-right-1 header-map-home">
      <div id="home-navigation" class="">
        <div id="home-navigation-dropdown" class="dropdown">
          <a href="#" id="home-navigation-dropdown-link" class="top-nav-title dropdown-btn js-dropdown-toggle" tabindex="0"></a>
          <div class="dropdown-menu">
            <a class="dropdown-link homeHome hide" href="../index.html"></a>
            <a class="dropdown-link homeOverview hide" href="../../features/features.html"></a>
            <a class="dropdown-link homePricing hide" href="../../features/plans/pricing.html"></a>
            <a class="dropdown-link homeGallery hide" href="../gallery.html"></a>
            <a class="dropdown-link homeScene" href="../webscene/viewer.html"></a>
            <a class="dropdown-link homeGroups hide" href="../groups.html"></a>
            <a class="dropdown-link homeMyContent hide" href="../content.html"></a>
            <a class="dropdown-link homeMyOrg hide" href="../organization.html"></a>
            <a class="dropdown-link homeHelp" href="../support.html"></a>
          </div>
        </div>
      </div>
    </div>

    <img id="viewer_testImage" alt="" style="position:absolute;top:0;left:-3000px"/>
  </body>
</html>
 
