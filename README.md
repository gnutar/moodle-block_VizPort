# VizPort #

## 説明/Summary ##
VizPortは、MoodleのDBに記録されたデータを可視化して表示するためのプラグイン（Block）です。

可視化の方法を、可視化ユニットを追加することで増やすことができるのが特徴です。可視化ユニットはJavascriptで記述します。Javascript内でインデックスをつけて特定の関数を呼び出すことで、MoodleのDBに記録されたデータを取り出してJavascriptのオブジェクトに入れることができますので、それを使って各利用者に必要な可視化をすることができます。

可視化ユニットはコース管理者レベルでアップロードできるようにしたいのですが、まだできていません。現在は vizport/js のディレクトリに通常ファイルとしておいておく形になっています。

DBのデータを読み込んでJavascript側に渡すところはモジュール化しておらず、プラグインの構成ファイルであるfetchdata.phpにハードコーディングしています。この部分はサーバファイルを変更できる権限を持った人だけが書き換えられれば良いという考えで、そのようにしています。

VizPort is a (Block Type) plugin for visualizing and displaying data recorded in Moodle's database. Its key feature is that visualization methods can be expanded by adding visualization units. Visualization units are written in JavaScript. By assigning an index and calling a specific function within the JavaScript, we can retrieve data recorded in Moodle's database and store it in a JavaScript object, which can then be used to draw whatever visualizations each user needs.

We would like to make it possible for course administrators to upload visualization units, but this has not been implemented yet. Currently, they need to be placed as regular files in the vizport/js directory.

The part that retrieve data from the database and passes it to the JavaScript side is not modularized; it is hardcoded in fetchdata.php, one of the plugin's constituent files. The reasoning behind this is that only those with permission to modify server files should be able to make changes to this part for security.

## 作者/Developer ##
中尾岳 (Gaku Nakao)

## 問い合わせ先/Contact ##
隅谷孝洋 (Takahiro Sumiya)
sumi[at]riise.hiroshima-u.ac.jp

## Installing via uploaded ZIP file ##

1. Log in to your Moodle site as an admin and go to _Site administration >
   Plugins > Install plugins_.
2. Upload the ZIP file with the plugin code. You should only be prompted to add
   extra details if your plugin type is not automatically detected.
3. Check the plugin validation report and finish the installation.

## Installing manually ##

The plugin can be also installed by putting the contents of this directory to

    {your/moodle/dirroot}/blocks/visport

Afterwards, log in to your Moodle site as an admin and go to _Site administration >
Notifications_ to complete the installation.

Alternatively, you can run

    $ php admin/cli/upgrade.php

to complete the installation from the command line.

## License ##

2024 Nakao Gaku <Admin@NGaku615.com>

This program is free software: you can redistribute it and/or modify it under
the terms of the GNU General Public License as published by the Free Software
Foundation, either version 3 of the License, or (at your option) any later
version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE.  See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with
this program.  If not, see <https://www.gnu.org/licenses/>.


