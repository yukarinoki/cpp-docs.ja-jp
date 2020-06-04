---
title: /SECTION (EDITBIN)
ms.date: 11/04/2016
f1_keywords:
- /section_editbin
helpviewer_keywords:
- -SECTION editbin option
- SECTION editbin option
- alignment characters in sections
- /SECTION editbin option
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
ms.openlocfilehash: 770e1d1c1cf288a7fe68f5bd076791d43f5b8572
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438911"
---
# <a name="section-editbin"></a>/SECTION (EDITBIN)

```
/SECTION:name[=newname][,attributes][alignment]
```

## <a name="remarks"></a>コメント

このオプションは、セクションの属性を変更して、セクションのオブジェクトファイルがコンパイルまたはリンクされたときに設定された属性をオーバーライドします。

コロン ( **:** ) の後に、セクションの*名前*を指定します。 セクション名を変更するには、*名前*の後に等号 (=) と*newname*を指定します。

セクションの `attributes`を設定または変更するには、コンマ ( **,** ) の後に1つ以上の属性文字を指定します。 属性を否定するには、その文字の前に感嘆符 (!) を付けます。 次の文字では、メモリ属性が指定されています。

|属性|設定|
|---------------|-------------|
|c|コード|
|d|アンドゥ|
|e|実行可能ファイル (executable)|
|i|初期化されたデータ|
|k|キャッシュされた仮想メモリ|
|m|リンクの削除|
|o|リンク情報|
|p|ページング仮想メモリ|
|r|読み取り|
|s|shared|
|u|初期化されていないデータ|
|w|write|

*配置*を制御するには、次のように、文字**A**の後に次の文字のいずれかを指定して、アラインメントのサイズをバイト単位で設定します。

|文字|配置サイズ (バイト単位)|
|---------------|-----------------------------|
|1|1|
|2|2|
|4|4|
|8|8|
|p|16|
|t|32|
|s|64|
|x|配置なし|

`attributes` と*配置*文字を、空白のない文字列として指定します。 文字の大文字と小文字は区別されません。

## <a name="see-also"></a>参照

[EDITBIN オプション](editbin-options.md)
