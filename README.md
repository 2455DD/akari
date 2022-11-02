<h3 align="center"><img src="https://i.imgur.com/Tyi3Bq5.png" width="200px"></h3>
<p align="center">Tag your anime photos effortlessly</p>

<p align="center">
<a href="https://github.com/mananapr/akari/blob/master/LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg"></a>
<a href="https://github.com/mananapr/akari/releases"><img src="https://img.shields.io/github/release/mananapr/akari/all.svg"></a>
<a href="https://pypi.python.org/pypi/akari/"><img src="https://img.shields.io/pypi/v/akari.svg"></a>
</p>

<img src="https://i.imgur.com/i4OH7aI.png" align="right" alt="img" width="400px">

`akari` is a work in progress python program to manage anime artwork
 - It uses [iqdb](https://iqdb.org) to reverse-search images and tags your images automatically
 - You can add new tags or remove tags manually
 - You can select some tags and filter your images accordingly
 - Has a built in image viewer for fullscreen viewing

## Requirements
 - requests
 - BeautifulSoup 4
 - PyQt5

## Installation
For user installation, simply run:

    pip3 install --user akari
    
Then add `$HOME/.local/bin` to your `$PATH`:

    echo PATH=\"\$PATH:\$HOME/.local/bin\" >> $HOME/.bashrc
    source $HOME/.bashrc

Alternatively, you can do a system wide installation:

    sudo pip3 install akari

## Usage
    usage: akari [-h] [-s /path/to/dir] [-g] [-v] [-r] [-f]

    optional arguments:
      -h, --help            show this help message and exit
      -s /path/to/dir, --scan /path/to/dir
                            Scan directory for new images
      -g, --gui             Start the GUI
      -v, --version         Displays the version
      -r, --rename          Rename the image if tags are detected
      -f, --force           force akari to identify the image

## Configuration
The configuration file is in 
- Linux/Mac:`$HOME/.config/akari/config.conf`
- Windows:`C:\Users\${Username}\.config\akari`
  - change ``${Username}`` to your PC's username

Including the following section:

### Common
Common section is under the title of ``[Common]``

| Key                 | Description                               | Default              |
|---------------------|-------------------------------------------|----------------------|
| `http_proxy`        | your http proxy server's url              | `none`               |
| `https_proxy`       | your https proxy server's url             | `none`               |
| `format`            | rename format,only active when using `-r` | `${char}+${general}` |
| `general_num_limit` | the limit of amount of tag `general`      | `5`                  |

#### Format Placeholder

| Placeholder    | Description                   | Example          |
|----------------|-------------------------------|------------------|
| `${character}` | Placeholder for Character tag | `inui_toko`      |
| `${general}`   | Placeholder for General tag   | `1girl`          |
| `${artist}`    | Placeholder for Artist tag    | `mizuki_hitoshi` |
| `${copyright}` | Placeholder for Copyright tag | `touhou`         |
| `${meta}`      | Placeholder for Meta tag      | `translated`     |
| `${rating}`    | Placeholder for Rating        | `sensitive`      |

### Rating
Rating section is under the title of ``[Rating]``

this section is used to save your settings about the ratings.
See [Danbooru Wiki about rating](https://danbooru.donmai.us/wiki_pages/howto%3Arate) to see how 
rating is tagged.

| Key         | Description                                               | Default |
|-------------|-----------------------------------------------------------|---------|
| `sfw_path`  | not implemented   |   |
| `nsfw_path` | not implemented    ||

#### Subsection: general
under the title of ``[Rating.general]`` 

| Key           | Description                                               | Default |
|---------------|-----------------------------------------------------------|---------|
| `type`        | the type you think this rating is, including `nsfw`,`sfw` | `sfw`     |


#### Subsection: sensitive
under the title of ``[Rating.sensitive]`` 

| Key           | Description                                               | Default |
|---------------|-----------------------------------------------------------|---------|
| `type`        | the type you think this rating is, including `nsfw`,`sfw` | `sfw`     |

#### Subsection: questionable
under the title of ``[Rating.questionable]`` 

| Key           | Description                                               | Default |
|---------------|-----------------------------------------------------------|---------|
| `type`        | the type you think this rating is, including `nsfw`,`sfw` | `nsfw`  |

#### Subsection: explicit
under the title of ``[Rating.explicit]`` 

| Key           | Description                                               | Default |
|---------------|-----------------------------------------------------------|---------|
| `type`        | the type you think this rating is, including `nsfw`,`sfw` | `nsfw`  |

## TODO
[TODO in original repo](https://github.com/mananapr/akari/issues/1)

For the TODO in this fork, See [the issue](https://github.com/2455DD/akari/issues)