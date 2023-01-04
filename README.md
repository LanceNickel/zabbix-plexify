# Plexify Zabbix
This theme does not deviate too far from the normal "Zabbix Blue" theme. If you are anything like me, you agree that IBM Plex Sans and IBM Plex Mono are the best UI fonts there are. I created this theme to change the UI fonts to IBM Plex, and also made a few small improvements along the way.

Currently there is only a light variant of the theme, but adapting it for dark shouldn't be anything more than changing which base styles this theme imports.

## Installation instructions
#### Requirements:
- Zabbix 6.2
- Root/super user access to your Zabbix Frontend server via SSH
- Administration privileges in Zabbix Frontend
- Permission to do this :)

#### Add the stylesheet:
1. SSH into your Zabbix Server with Frontend
2. Navigate to `/usr/share/zabbix/assets/styles` and create the file `plexify.css`
3. In that file, paste the contents of plexify.css using your favourite text editor (like Vim) and write the file

#### Add the theme to Zabbix:
1. With your favourite text editor (such as Vim), open the Zabbix APP class at `/usr/share/zabbix/include/classes/core/APP.php`
2. Before the closing brace, add the following code (in the APP class):
```
    public static function getThemes() {
        return array_merge(parent::getThemes(), [
            'plexify' => _('Plexify')
        ]);
    }
```

#### Activate the theme globally:
1. In Zabbix Frontend, navigate to **Administration > General > GUI**
2. Change **Default theme** to **Plexify**
3. Click **Update**

#### Or, activate the theme for your profile only:
1. In Zabbix Frontend, navigate to **User settings > Profile**
2. Change **Theme** to **Plexify**
3. Click **Update**

Congratulations, you should now have Plexify installed and activated on your Zabbix Frontend, enjoy!

## Reporting issues
Found a problem with this theme? Please feel free to open an issue/propose a fix. This is some quick CSS I whipped up in 20 minutes with some limited testing of the full UI. Any improvements are greatly appreciated!
