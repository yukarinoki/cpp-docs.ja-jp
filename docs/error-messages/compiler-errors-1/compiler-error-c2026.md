---
title: コンパイラエラー C2026
ms.date: 11/04/2016
f1_keywords:
- C2026
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
ms.openlocfilehash: 9747b1edadc76ceeb502b2c6fd03496b91769f5a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208066"
---
# <a name="compiler-error-c2026"></a>コンパイラエラー C2026

文字列が大きすぎます。末尾の文字が切り捨てられました

文字列が、16380の1バイト文字の制限を超えています。

隣接する文字列を連結する前に、文字列を16380の1バイト文字より長くすることはできません。

この長さの約半分の Unicode 文字列でも、このエラーが発生します。

文字列を次のように定義している場合は、C2026 が生成されます。

```
char sz[] =
"\
imagine a really, really \
long string here\
";
```

次のように分割できます。

```
char sz[] =
"\
imagine a really, really "
"long string here\
";
```

非常に大きな文字列リテラル (32K 以上) をカスタムリソースまたは外部ファイルに格納することができます。 詳細について[は、「新しいカスタムリソースまたはデータリソースの作成](../../windows/creating-a-new-custom-or-data-resource.md)」を参照してください。
