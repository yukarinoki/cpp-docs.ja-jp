---
title: コンパイラエラー C2026
description: Microsoft C/c + + コンパイラエラー C2026、その原因、およびそれらの解決方法について説明します。
ms.date: 09/25/2020
f1_keywords:
- C2026
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
ms.openlocfilehash: 39195568f964f07c6131fa43ef4a0f06121795da
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414049"
---
# <a name="compiler-error-c2026"></a>コンパイラエラー C2026

> 文字列が大きすぎます。末尾の文字が切り捨てられました

文字列が、16380の1バイト文字の制限を超えています。

## <a name="remarks"></a>解説

隣接する文字列を連結する前に、文字列を16380の1バイト文字より長くすることはできません。

この長さの約半分の Unicode 文字列でも、このエラーが発生します。

## <a name="example"></a>例

文字列を次のように定義している場合は、C2026 が生成されます。

```C
char sz[] =
"\
imagine a really, really \
long string here\
";
```

次のように分割できます。

```C
char sz[] =
"\
imagine a really, really "
"long string here\
";
```

非常に大きな文字列リテラル (32K 以上) をカスタムリソースまたは外部ファイルに格納することができます。 詳細については、「 [新しいカスタムリソースまたはデータリソースを作成するには」を](../../windows/binary-editor.md#to-create-a-new-custom-or-data-resource)参照してください。
