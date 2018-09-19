---
title: セクション (C/C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- SECTIONS
dev_langs:
- C++
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ecd8d6050df7a4d30b0a37cad28e030d1cd63cf0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722898"
---
# <a name="sections-cc"></a>SECTIONS (C/C++)

1 つ以上の概説`definitions`プロジェクトの出力ファイル内のセクションで、アクセス指定子であります。

```
SECTIONS
definitions
```

## <a name="remarks"></a>Remarks

各定義は個別の行に指定する必要があります。 `SECTIONS`キーワードは、最初の定義と同じ行または前の行を指定できます。 .Def ファイルは、1 つまたは複数含めることができます`SECTIONS`ステートメント。

これは、`SECTIONS`ステートメントが、イメージ ファイルのセクションでは 1 つまたは複数の属性を設定し、セクションの各種類の既定の属性をオーバーライドするために使用できます。

形式`definitions`は。

`.section_name specifier`

場所`.section_name`プログラム イメージ内のセクションの名前を指定し、`specifier`は次のアクセス修飾子の 1 つ以上。

|修飾子|説明|
|--------------|-----------------|
|`EXECUTE`|セクションが実行可能ファイル|
|`READ`|データの読み取り操作します。|
|`SHARED`|イメージを読み込むすべてのプロセス間でセクションを共有します|
|`WRITE`|データの書き込み操作します。|

指定子の名前はスペースで区切ります。 例えば:

```
SECTIONS
.rdata READ WRITE
```

`SECTIONS` セクションの一覧の先頭をマーク`definitions`します。 各`definition`別々 の行にある必要があります。 `SECTIONS`キーワードは、1 番目と同じ行に配置できます`definition`または前の行。 .Def ファイルは、1 つまたは複数含めることができます`SECTIONS`ステートメント。 `SEGMENTS`のシノニムとしてキーワードがサポートされている`SECTIONS`します。

Visual C の以前のバージョンがサポートされています。

```
section [CLASS 'classname'] specifier
```

`CLASS`キーワードは互換性のため、サポートされているは無視されます。

セクションの属性を指定することは、 [/section](../../build/reference/section-specify-section-attributes.md)オプション。

## <a name="see-also"></a>関連項目

[モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)