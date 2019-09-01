# 中州韻輸入法引擎配置 - A personalized Rime config

This configuration:

- Optimized for simplified Chinese;
- Implement 朙月拼音 `luna-pinyin`, 微软双拼 `double-pinyin-mspy` and 地球拼音 `terra-pinyin` with 20+ dictionaries including symbols and emoji;
- Feature 地球双拼 `terra-double-pinyin-mspy`, a double pinyin input method supporting tone marks;
- Use 地球双拼 `terra-double-pinyin-mspy` to reverse lookup 吴语（苏州话）`wugniu_soutseu` with tone marks, toggled by `` ` ``;
- Use ASCII mode for several applications.

## Supported Rime Version

### MacOS

The config should run on Squarrel 0.14.0 or greater.

## Installation

### [鼠鬚管](https://rime.im) Squirrel (MacOS)

- via [Latest release](https://rime.im)

- via [source code](https://github.com/rime/squirrel): [Build instruction](https://github.com/rime/squirrel/blob/master/INSTALL.md)

- via [Homebrew](https://brew.sh): `brew cask install squirrel`

### [東風破](https://github.com/rime/plum) /plum/

Install /plum/, the configuration manager for Rime input method engine:

```sh
cd ~/Library/Rime
curl -fsSL https://git.io/rime-install | bash
```

Then install packages:

```
cd plum
bash rime-install :preset double-pinyin emoji NGLI/rime-wugniu_soutseu
```
/// Supported input methods ℞ ///

- **Essentials:** [`prelude`](https://github.com/rime/rime-prelude) 基础配置 / [`essay`](https://github.com/rime/rime-essay) 八股文
- **Phonetic-based:** [`luna-pinyin`](https://github.com/rime/rime-luna-pinyin) 朙月拼音 / [`terra-pinyin`](https://github.com/rime/rime-terra-pinyin) 地球拼音 / [`bopomofo`](https://github.com/rime/rime-bopomofo) 注音 / [`pinyin-simp`](https://github.com/rime/rime-pinyin-simp) 袖珍简化字拼音
- **Derivatives of Pinyin:** [`double-pinyin`](https://github.com/rime/rime-double-pinyin) 双拼 / [`combo-pinyin`](https://github.com/rime/rime-combo-pinyin) 宫保拼音 / [`stenotype`](https://github.com/rime/rime-stenotype) 打字速记法
- **Varieties of Chinese:** [`jyutping`](https://github.com/rime/rime-jyutping) 粤拼 / [`wugniu`](https://github.com/rime/rime-wugniu) 上海吴语 / [`soutzoe`](https://github.com/rime/rime-soutzoe) 苏州吴语 /[`middle-chinese`](https://github.com/rime/rime-middle-chinese): 中古汉语拼音
- **Shape-based:** [`stroke`](https://github.com/rime/rime-stroke) 笔画 /[`cangjie`](https://github.com/rime/rime-cangjie) 仓颉输入法 / [`quick`](https://github.com/rime/rime-quick) 速成 / [`wubi`](https://github.com/rime/rime-wubi) 五笔字型 / [`array`](https://github.com/rime/rime-array) 行列输入法 / [`scj`](https://github.com/rime/rime-scj) 快速仓颉
- **Miscellaneous:** [`emoji`](https://github.com/rime/rime-emoji) 颜文字 / [`ipa`](https://github.com/rime/rime-ipa): 国际音标

### Personalized configuration and dictionaries

To install, clone this repo to `~/Library/Rime`:

```sh
cd ~/Library/Rime
git init
echo -e "/*\n\!/README.md\n\!/dict\n\!/*.custom.yaml\n\!/*.extended.dict.yaml\n\!/terra_double_pinyin_mspy.*" >> .gitignore
git remote add origin https://github.com/ziyunch/Rime.git
git pull origin master
ln -s /Library/Input\ Methods/Squirrel.app/Contents/SharedSupport/opencc/* ./opencc/
```

## Deploy

Press `Control` + `Option` + `` ` `` to deploy current configuration.

Press `Control`+`` ` `` to select input method.

## Updates

To update /plum/ itself, run:

```sh
cd ~/Library/Rime/plum
bash rime-install plum
```

To update the /plum/ packages, run:

```sh
cd ~/Library/Rime/plum
bash rime-install :preset double-pinyin emoji NGLI/rime-wugniu_soutseu
```

To update the config, run:

```sh
cd ~/Library/Rime
git pull origin master
```

## Customerization

- Modify `default.custom.yaml` to select more input methods or comment out input methods no longer needed:

```
  schema_list:
    - schema: luna_pinyin          # 朙月拼音
    - schema: terra_pinyin         # 地球拼音 dì qiú pīn yīn
    - schema: terra_double_pinyin_mspy # 地球双拼
    - schema: double_pinyin_mspy   # 微软双拼
    - schema: double_pinyin        # 自然码双拼
    - schema: double_pinyin_abc    # 智能ABC双拼
    - schema: double_pinyin_flypy  # 小鹤双拼
    - schema: wugniu_soutseu       # 吴语（苏州话）
    - schema: stroke               # 笔画
    - schema: cangjie              # 仓颉输入法
    - schema: bopomofo             # 注音
    - schema: emoji                # 颜文字
```

- Delete `wugniu_soutseu.custom.yaml` to use the default 朙月拼音 `luna_pinyin` reverse lookup 吴语（苏州话）`wugniu_soutseu`.

- More guides:

  - [Official Customization Guide](https://github.com/rime/home/wiki/CustomizationGuide)
  - [Schema.yaml Customization Guide by LEOYoon-Tsaw](https://github.com/LEOYoon-Tsaw/Rime_collections/blob/master/Rime_description.md)


