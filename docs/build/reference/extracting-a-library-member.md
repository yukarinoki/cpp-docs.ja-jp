---
description: 詳細については、「ライブラリメンバーの抽出」を参照してください。
title: ライブラリ メンバーの抽出
ms.date: 11/04/2016
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
ms.openlocfilehash: 8797db6baa08fc36cf288f5b23d73ff730edd973
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192318"
---
# <a name="extracting-a-library-member"></a>ライブラリ メンバーの抽出

LIB を使用して、既存のライブラリのメンバーのコピーを含むオブジェクト (.obj) ファイルを作成できます。 メンバーのコピーを抽出するには、次の構文を使用します。

```
LIB library /EXTRACT:member /OUT:objectfile
```

このコマンドは、ライブラリののコピーを含む *objectfile* という名前の .obj ファイルを作成します `member` 。  `member`名前は大文字と小文字が区別されます。 1つのコマンドで抽出できるのは1つのメンバーだけです。 /OUT オプションは必須です。既定の出力名はありません。 *Objectfile* という名前のファイルが、指定されたディレクトリ (または現在の *ディレクトリ) に* 既に存在する場合、抽出された *objectfile* は既存のファイルを置き換えます。

## <a name="see-also"></a>関連項目

[LIB リファレンス](lib-reference.md)
