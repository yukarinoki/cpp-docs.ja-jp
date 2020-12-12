---
description: 詳細については、「リンカーツールの警告 LNK4254」を参照してください。
title: リンカー ツールの警告 LNK4254
ms.date: 11/04/2016
f1_keywords:
- LNK4254
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
ms.openlocfilehash: 410a904af6af2015a817ac9e254dff7f09811b72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244473"
---
# <a name="linker-tools-warning-lnk4254"></a>リンカー ツールの警告 LNK4254

セクション ' section1 ' (オフセット) が異なる属性を持つ ' section2 ' (オフセット) にマージされました

1つのセクションの内容が別のセクションにマージされましたが、2つのセクションの属性は異なります。 プログラムから予期しない結果が返される可能性があります。 たとえば、読み取り専用のデータは書き込み可能なセクションに存在する可能性があります。

LNK4254 を解決するには、マージ要求を変更または削除します。

Visual C++ で x86 マシンと Windows CE ターゲット (ARM、MIPS、SH4、Thumb) を対象とする場合は、「」を使用します。CRT セクションは読み取り専用です。 コードが以前の動作 () に依存している場合は。CRT セクションは読み取り/書き込み)、予期しない動作が発生する可能性があります。

詳細については、次のトピックを参照してください。

- [/MERGE (セクションの結合)](../../build/reference/merge-combine-sections.md)

- [コメント (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>例

次の例では、LNK4254 が生成されます。

```cpp
// LNK4254.cpp
// compile with: /W1 /link /WX
// LNK4254 expected
#pragma comment(linker, "/merge:.data=.text")
int main() {}
```
