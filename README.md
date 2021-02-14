# Defining the Open Game Asset Data Definition
The dataformat for the Open Game Assets can be YAML, JSON, XML or even INI file, because it is determined by the code that uses it.
The data contained in the dataformat must be defined as it describes the assets for filtering and links to where they can be found.

## Being able to convert an ID to a Path
The most important functionality of the data structure is a key-value map, where an ID key can be matched to a value path.
* The Uuid is a Universal unique Idenfier similar to GUID on Windows systems.
* The ID is an unique integer number generaly creating by addind 1 to the last used number
* The Code is a string containing a hashed human readable version of the path.
* The Path is a string containing the actual path starting in the asset folder.

## Loading from a OS or ZIP folder structure
The path to the asset can be directly in the asset folder of the file system, but should also be able to be navigated as the folder structure in a Zip file. The Zip format is specificaly usefull as github standard creates zip files of repositories, making it easy to dowload outside of Git. Other container formats may also be possible to navigate as a .BIG file is often used to save disk space, as many small files do not fill up the disk sectors completely. A BIG file generaly offers security by obscurity as it's not readable for normal users, thus it's not in the Open spirit of things.

Modern developments in hardware have lead to reading compressed data from disk and decrompressing it with the CPU, being faster then reading uncompressed data from disk. The CPU generaly being overpowered and underutilized.

## Loading based on version
It should be possible to determin to witch version the asset link belongs to, either by an attribute on the asset link or containing the asset link in a version. container. The versioning should be done by Mayor.Minor.Bugfix.Build wich is common on Windows systems.

## Loading based on Culture and Language
Similar to version the Culture and Language should be able to be determined for the asset link, either by an attribute on the asset link or containing the asset link in a Culture and language structure. Culture and Language should be denoted by the Country-Language standart like Be-NL, Be-Fr.

## Loading complete scenes
It should be possible to define a group of assets to load them as a scene in one go. The variables to use the assets should either be dynamicly created or predefined by generating them in code based on the asset definition. 

It would be preferable to have the variables of one scene on a scene object, but it might depend on the situation.

Alternatively the multiple asset variable problem could be ignored and just fill the cache and then do straightforward individual requests for assets.

## Generating variables usable in game code
It should be possible to generate variables in code based on the hints added to the asset links. The hints should be language specific, as the same file may be used by multiple code bases.

