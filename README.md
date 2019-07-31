# OpenStreetMap Carto Italian

![screenshot](https://raw.github.com/ammatwain/openstreetmap-carto-italian/master/preview.png)

These are the CartoCSS map stylesheets for the Standard map layer on [OpenStreetMap.org](https://www.openstreetmap.org).

This version has been modified to represent geographic names giving priority to the following languages:
1) Italian
2) English
3) French
3) Local language (relative to the map)

These stylesheets can be used in your own cartography projects, and are designed
to be easily customised. They work with [Kosmtik](https://github.com/kosmtik/kosmtik)
 and also with the command-line [CartoCSS](https://github.com/mapbox/carto) processor.

Since August 2013 these stylesheets have been used on the OSMF tileservers (tile.openstreetmap.org), and
are updated from each point release. They supersede the previous [XML-based stylesheets](https://github.com/openstreetmap/mapnik-stylesheets).

# Installation

You need a PostGIS database populated with OpenStreetMap data along with auxillary shapefiles.
See [INSTALL.md](INSTALL.md).

# Database Import (with osm2pgsql)
<code><pre>
osm2pgsql -d gis \\
  --create --slim -G \\
  --hstore-all \\
  --tag-transform-script /your/path/openstreetmap-carto-italian/openstreetmap-carto.lua \\
  -C 2500 \\
  --number-processes 1 \\
  -S /your/path/openstreetmap-carto-italian/openstreetmap-carto.style \\
  /your/path/lebanon-latest.osm.pbf
</pre></code>
# Contributing

Contributions to this project are welcome, see [CONTRIBUTING.md](CONTRIBUTING.md)
for full details.

# Versioning

This project follows a MAJOR.MINOR.PATCH versioning system. In the context of a
cartographic project you can expect the following:

* PATCH: When a patch version is released, there would be no reason not to
  upgrade. PATCH versions contain only bugfixes e.g. stylesheets won't compile,
  features are missing by mistake, etc.
* MINOR: These are routine releases and happen every 2-5 weeks. They will
  contain changes to what's shown on the map, how they appear, new features
  added and old features removed. They may rarely contain changes to assets i.e.
  shapefiles and fonts but will not contain changes that require software or
  database upgrades.
* MAJOR: Any change the requires reloading a database, or upgrading software
  dependecies will trigger a major version change.

# Roadmap

## First Commit ( 2019-07-31)

This was a full re-implementation of the original OpenStreetMap Carto style,

( see  [openstreetmap-carto](https://github.com/gravitystorm/openstreetmap-carto) )

# Alternatives

There are many open-source stylesheets written for creating OpenStreetMap-based
maps using Mapnik, many based on this project. Some alternatives are:

* [openstreetmap-carto](https://github.com/gravitystorm/openstreetmap-carto)
* [OSM-Bright](https://github.com/mapbox/osm-bright)
* [XML-based stylesheets](https://trac.openstreetmap.org/browser/subversion/applications/rendering/mapnik)
* [osmfr-cartocss](https://github.com/cquest/osmfr-cartocss)
* [openstreetmap-carto-german](https://github.com/giggls/openstreetmap-carto-de)

# Maintainers
(for this version)

* Amedeo Sorpreso [@ammatwain](https://github.com/ammatwain/)

(for original version)

* Andy Allan [@gravitystorm](https://github.com/gravitystorm/)
* Matthijs Melissen [@matthijsmelissen](https://github.com/matthijsmelissen/)
* Paul Norman [@pnorman](https://github.com/pnorman/)
* Mateusz Konieczny [@matkoniecz](https://github.com/matkoniecz/)
* Daniel Koć [@kocio-pl](https://github.com/kocio-pl)
* Christoph Hormann [@imagico](https://github.com/imagico)
* Lukas Sommer [@sommerluk](https://github.com/sommerluk)
