---
description: '詳細情報: セクション (C/c + +)'
title: SECTIONS (C/C++)
ms.date: 11/04/2016
f1_keywords:
- SECTIONS
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
ms.openlocfilehash: aaebeb19c921dfb389c55209c7a371f49043cb56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224765"
---
# <a name="sections-cc"></a>SECTIONS (C/C++)

`definitions`プロジェクトの出力ファイル内のセクションのアクセス指定子である1つ以上のセクションを導入します。

```
SECTIONS
definitions
```

## <a name="remarks"></a>解説

各定義は個別の行に指定する必要があります。 キーワードは、 `SECTIONS` 最初の定義または前の行と同じ行に配置できます。 .Def ファイルには、1つまたは複数のステートメントを含めることができます `SECTIONS` 。

この `SECTIONS` ステートメントは、イメージファイル内の1つ以上のセクションの属性を設定し、セクションの各種類の既定の属性をオーバーライドするために使用できます。

の形式 `definitions` は次のとおりです。

`.section_name specifier`

`.section_name`は、プログラムイメージ内のセクションの名前であり、は `specifier` 次のアクセス修飾子の1つまたは複数です。

|修飾子|説明|
|--------------|-----------------|
|`EXECUTE`|セクションは実行可能です|
|`READ`|データの読み取り操作を許可します|
|`SHARED`|イメージを読み込むすべてのプロセス間でセクションを共有します|
|`WRITE`|データに対する書き込み操作を許可します|

指定子名をスペースで区切ります。 次に例を示します。

```
SECTIONS
.rdata READ WRITE
```

`SECTIONS` セクションのリストの先頭をマークし `definitions` ます。 各 `definition` は別々の行に配置する必要があります。 キーワードは、 `SECTIONS` 最初の行または前の行と同じ行に配置でき `definition` ます。 .Def ファイルには、1つまたは複数のステートメントを含めることができます `SECTIONS` 。 キーワードは、 `SEGMENTS` のシノニムとしてサポートされてい `SECTIONS` ます。

以前のバージョンの Visual C++ はサポートされています。

```
section [CLASS 'classname'] specifier
```

`CLASS`キーワードは互換性のためにサポートされていますが、無視されます。

Section 属性の指定方法は、 [/SECTION](section-specify-section-attributes.md) オプションを使用する場合と同じです。

## <a name="see-also"></a>関連項目

[Module-Definition ステートメントの規則](rules-for-module-definition-statements.md)
