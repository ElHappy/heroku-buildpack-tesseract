# Heroku Buildpack Tesseract

This package provide a custom Heroku buildpack providing the [Tesseract OCR](https://code.google.com/p/tesseract-ocr/) binary and all the required libraries to Heroku apps. Training data for English and Finnish language is provided. 

## Configuration

The first step consists in allowing your Heroku app to use multiple buildpacks. Heroku natively supports [multiple buildpacks per app](https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app).

1. setup your app as  
    ```
    heroku buildpacks:set heroku/LANG
    heroku buildpacks:add https://github.com/matteotiziano/heroku-buildpack-tesseract
    ```
	
    where `LANG` is the language used by your app (e.g., `ruby`, `python`, or `nodejs`). A complete list of Heroku buildpacks can be found [here](https://devcenter.heroku.com/articles/buildpacks).
2. you can use the `tesseract` binary in your Heroku app!
3. deploy :)

## Example
A minimal functioning Heroku app using this buildpack can be found [here](https://github.com/matteotiziano/secret-harbor). The app is coded in Python and provides a REST method that accept an image and return the Tesseract OCR output as a JSON object. The REST functionality is implemented through the [Flask web microframework](http://flask.pocoo.org/).

## Note
This fork solves the [issue](https://github.com/fouady/RoR-Tesseract-Heroku/issues/1) of the missing libraries `libtiff4` and `libjpeg62`.

## License
MIT License.

Original work Copyright (c) 2013 Marco Azimonti  
Modified work Copyright (c) 2015 Matteo Maggioni

