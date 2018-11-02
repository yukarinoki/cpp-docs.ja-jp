---
title: ライブラリ メンバーの抽出
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
ms.openlocfilehash: 2975ef584b0244a16b556232b6939308d2e1bd14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447035"
---
# <a name="extracting-a-library-member"></a>ライブラリ メンバーの抽出

LIB を使用して、既存のライブラリのメンバーのコピーを含むオブジェクト (.obj) ファイルを作成することができます。 メンバーのコピーを抽出するには、次の構文を使用します。

```
LIB library /EXTRACT:member /OUT:objectfile
```

このコマンドと呼ばれる .obj ファイルを作成します。 *objectfile*のコピーを格納している、`member`の、*ライブラリ*します。 `member`名は大文字小文字を区別します。 1 つのコマンドで 1 つだけのメンバーを抽出することができます。 /OUT オプションが必要です。既定の出力名はありません。 ファイルが呼び出された場合*objectfile* 、指定したディレクトリに既に存在します (または現在のディレクトリにディレクトリが指定されていない場合*objectfile*)、抽出した*objectfile*既存のファイルを置き換えます。

## <a name="see-also"></a>関連項目

[LIB リファレンス](../../build/reference/lib-reference.md)