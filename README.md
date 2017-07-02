[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://beta.webcomponents.org/element/PolymerElements/paper-input)

## &lt;friendly-animation&gt;

`<friendly-animation>` is a Polymer component that wraps the [Bodymovin'](https://github.com/bodymovin/bodymovin) After Effects plugin. It enables the user to render After Effects animations in browser as either html canvas or svg animations and comes with a handful of convenience methods to interact with your animation(s).

<!---
```
<custom-element-demo>
  <template>
    <script src="../webcomponentsjs/webcomponents-lite.js"></script>
    <link rel="import" href="friendly-animation.html">
    <style>
      friendly-animation {
        max-width: 400px;
        margin: auto;
      }
    </style>
  </template>
</custom-element-demo>
```
-->
The most simple setup is to pass your After Effects/Bodymovin' exported`.json` file to the `friendly-component` as it's `url` property and add `autoplay` to have your play on load.
```html
<friendly-animation url="../data.json" autoplay></friendly-animation>
```

A `friendly-animation` component can also recieve a list of element id's to control it's play state. Simply pass in the id's of the elements as triggers to the animation and make sure to set one of the four actions. `play`, `pause`, `stop`, or `play-toggle`.
```html
<friendly-animation url="../data.json" triggers="one, two, three, four"></friendly-animation>

<button id="one" action="play">Play</button>
<button id="two" action="pause">Pause</button>
<button id="three" action="stop">Stop</button>
<button id="four" action="play-toggle">Play-Toggle</button>
```

*For additional interactions and properties please see the API Docs*

### Requirements
 - install the Bodymovin' plugin for After Effects, from [here](http://aescripts.com/bodymovin/). Once you download the `.zxp` file i recommend installing [ZXP Installer](http://aescripts.com/learn/zxp-installer/), which will do a lot of the leg work in installing the **Bodymovin'** plugin for you.
 - once installed get animating! Create an after effects animation and save. Click on the `window` tab at the top, -> `extensions` -> `bodymovin'`, and then render to a location you choose. Your animation will be exported to your chosen location as a `.json` file. Simply place that `.json` into your app and reference it within you `<friendly-animation></friendly-animation>` component as the `url` property, pass the `autoplay` property to the component and boom!..you now have your After Effects animation playing in browser :) Don't forget to read the docs and see what properties are available for you to interact with your `friendly-animation`.

### Note 
The Bodymovin' library that underpins my component is where the magic happens. [Hernan](https://github.com/bodymovin) has done an incredible job and has been just so helpful in answering questions and improving his library. That said, After Effects is a beast, and while the Bodymovin' library supports a lot of AE animtaion, there are some features which are yet to be supported. E.g Particle Systems. I recommend testing an AE animation in its early stages. Save and render and then choose `preview` to see if your desired animation effect is supported. Hernan is a rockstar and updates to the Bodymovin' library are extremely regular. It's open all sourced and if anyone has the know how please give him a hand! 
