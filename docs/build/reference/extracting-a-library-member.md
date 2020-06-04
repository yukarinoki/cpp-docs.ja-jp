---
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
ms.openlocfilehash: 874866627099eb5aeb318273db26a976e99bac7f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439871"
---
# <a name="extracting-a-library-member"></a>ライブラリ メンバーの抽出

LIB を使用して、既存のライブラリのメンバーのコピーを含むオブジェクト (.obj) ファイルを作成できます。 メンバーのコピーを抽出するには、次の構文を使用します。

```
LIB library /EXTRACT:member /OUT:objectfile
```

このコマンドにより、*ライブラリ*の `member` のコピーを含む*objectfile*という .obj ファイルが作成されます。 `member` 名は大文字と小文字が区別されます。 1つのコマンドで抽出できるのは1つのメンバーだけです。 /OUT オプションは必須です。既定の出力名はありません。 *Objectfile*という名前のファイルが、指定されたディレクトリ (または現在の*ディレクトリ) に*既に存在する場合、抽出された*objectfile*は既存のファイルを置き換えます。

## <a name="see-also"></a>参照

[LIB リファレンス](lib-reference.md)
