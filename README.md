# GitHub Flavored Markdown for WordPress

wp-gfm is the WordPress plugin that convert from GitHub Flavored Markdown by using the PHP-Markdown or [GitHub Render API](http://developer.github.com/v3/markdown/).

## Dependencies

 * WordPress
 * PHP 5.3+
 * Optional: Render API: [GitHub Render API](http://developer.github.com/v3/markdown/) or https://github.com/makotokw/ruby-markdown-render-api

## How to work

The plugin has two convertion. 

``[markdown]`` as shortcode for PHP-Markdown, convert by using ``\Michelf\Markdown`` class **inside WordPress**.

``[gfm]`` as shortcode for GitHub Flavored Markdown, convert by using the Render API **outside WordPress**. Default Render API is GitHub Render API, limits requests to 60 per hour for unauthenticated requests. Alternatives Render API that works on heroku is here: https://github.com/makotokw/ruby-markdown-render-api


## Installation

Use git

    cd /path/to/wp-content/plugins
    git clone git://github.com/makotokw/wp-gfm.git


## PHP-Markdown (Recommended)

### Usage

Use ``[markdown][/markdown]`` as shortcode on entry.

    [markdown]
    | First Header  | Second Header |
    | ------------- | ------------- |
    | Content Cell  | Content Cell  |
    | Content Cell  | Content Cell  |
    [/markdown]

Since version 0.2, it supported **Fenced code blocks**.

    [markdown]
    ```ruby
    require 'redcarpet'
    markdown = Redcarpet.new("Hello World!")
    puts markdown.to_html
    ```
    [/markdown]

Output

    <pre class="prettyprint lang-ruby">require 'redcarpet'
    markdown = Redcarpet.new("Hello World!")
    puts markdown.to_html
    </pre>

You should use [google-code-prettify](https://code.google.com/p/google-code-prettify/) if you want to allow syntax highlighting.

## GitHub Render API

### Setup

 * Open ``WP GFM`` Settings and set ``Render URL``


### Usage

Use ``[gfm][/gfm]`` as shortcode on entry.

    [gfm]
    ```ruby
    require 'redcarpet'
    markdown = Redcarpet.new("Hello World!")
    puts markdown.to_html
    ```
    [/gfm]


## Result

![Result](https://dl.dropbox.com/u/8932138/screenshot/wp-gfm/wp-gfm_2013-04-08_2027.png)

## LICENSE

The MIT License

## Current Version

The line below is used for the updater API, please leave it untouched unless bumping the version up :)

~Current Version:0.4~