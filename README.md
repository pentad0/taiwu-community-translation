# Community Translation Project for the Scroll of Taiwu

This is the prototype version, it WILL mess the game text layout.

Download the latest version from the releases. 

You can download the English Langauge files, the Chinese RAW langauge files, and the extraction tools to generate the files over at [TaiwuCommunityTranslation/taiwu-language-files-zh-hans](https://github.com/TaiwuCommunityTranslation/taiwu-language-files-zh-hans).

# Installation Instructions
1. Download the latest [release](https://github.com/TaiwuCommunityTranslation/taiwu-community-translation/releases) from the right side-bar.
2. Extract the contents to your Scroll Of Taiwu folder.
3. IMPORTANT: Go here [TaiwuCommunityTranslation/taiwu-language-files-zh-hans](https://github.com/TaiwuCommunityTranslation/taiwu-language-files-zh-hans) and get a copy of the repository.
4. Put the contents of the `Translations` inside the `Langauges` folder in your Scroll Of Taiwu folder.
5. You need to enable the mod from the game's main menu (Right most button, click the checkmark below the mod-name, and then click the blue button).

You can get the latest copies of the translation by simply repeating steps 3 and 4. Files that are 100% translated in the Transifex should automatically be updated.

NOTE: Event files are the only game files that get changed/replaced by this mod. If you're having issues, verify game files and rerun the mod. 

# Development Note
Builds are compiled against a publicized .DLL due to some problematic class nesting. 
https://github.com/CabbageCrow/AssemblyPublicizer

# taiwu-community-translation-jp
日本語表示用に下記を追加した。

<ol>
  <li>
    設定にlanguageを追加。
    
    MODがThe Scroll Of Taiwu\Languages\"languageの値"のフォルダからテキストを読むようにした。
  </li>
  <li>
    文字フォント縮小処理の回避分岐を追加。
    
    日本語表示の場合は不要と思われる文字フォント縮小処理はlanguage=enの時だけにしか動かないようにした。
    
    ただしenableAutoSizingで処理が切り替わる部分は修正しなかった。
  </li>
</ol>

これらの修正部分はlanguage=enにすると従来通りの動作をするようにしている。


# 注意点

このゲームはフォントが日本語を表示できるようになっていないので日本語テキストを読み込ませる場合はこのMODを入れた上でThe Scroll Of Taiwu\The Scroll of Taiwu_Data\GameResources\fonts.uabのフォントを差し替える必要がある。

またこのMODはThe Scroll Of Taiwu\The Scroll of Taiwu_Data\GameResources\views.uabに格納しているボタンなどのテキストや、The Scroll Of Taiwu\The Scroll of Taiwu_Data\Managed\Assembly-CSharp.dllのソースに直接書かれているテキストフィールドのデフォルト値などには対応していないので、完全に翻訳しようとすると別の手段が必要になる。


# AssemblyPublicizerの使い方

1. Drag and drop "The Scroll Of Taiwu/The Scroll of Taiwu_Data/Managed/Assembly-CSharp.dll" onto "AssemblyPublicizer.exe". This will create a new folder called "/publicized_assemblies/".
2. Move this folder to "taiwu-community-translation/src/bin/Debug/net481".
3. Replace the path of "Assembly-CSharp_publicized.dll" in "TaiwuCommunityTranslation.csproj" to the one above.
