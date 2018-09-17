---
title: ライブラリ メンバーの抽出 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9207a77868b3257d09f0d9efe38e4765cb8f4906
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726519"
---
# <a name="extracting-a-library-member"></a>ライブラリ メンバーの抽出

LIB を使用して、既存のライブラリのメンバーのコピーを含むオブジェクト (.obj) ファイルを作成することができます。 メンバーのコピーを抽出するには、次の構文を使用します。

```
LIB library /EXTRACT:member /OUT:objectfile
```

このコマンドと呼ばれる .obj ファイルを作成します。 *objectfile*のコピーを格納している、`member`の、*ライブラリ*します。 `member`名は大文字小文字を区別します。 1 つのコマンドで 1 つだけのメンバーを抽出することができます。 /OUT オプションが必要です。既定の出力名はありません。 ファイルが呼び出された場合*objectfile* 、指定したディレクトリに既に存在します (または現在のディレクトリにディレクトリが指定されていない場合*objectfile*)、抽出した*objectfile*既存のファイルを置き換えます。

## <a name="see-also"></a>関連項目

[LIB リファレンス](../../build/reference/lib-reference.md)