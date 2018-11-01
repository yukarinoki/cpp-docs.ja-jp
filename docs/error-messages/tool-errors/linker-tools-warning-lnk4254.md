---
title: リンカー ツールの警告 LNK4254
ms.date: 11/04/2016
f1_keywords:
- LNK4254
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
ms.openlocfilehash: 2c68e49d58b0fd6b28607eb0ba78c092441f6f4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467016"
---
# <a name="linker-tools-warning-lnk4254"></a>リンカー ツールの警告 LNK4254

セクション '「section1」' (オフセット) がセクション '2' にマージが違います (オフセット)

1 つのセクションの内容は、別にマージされましたが、2 つのセクションの属性が異なります。 プログラムには、予期しない結果が得られる可能性があります。 たとえば、データを読み取るしたいだけようになりましたがあります書き込み可能なセクションでは。

LNK4254 を解決するには、変更またはマージ要求を削除します。

X86 を対象とするときにマシンと Windows CE ターゲット (ARM、MIPS、SH4、およびつまみ) Visual c にします。CRT のセクションでは、読み取り専用です。 コードは、以前の動作に依存する場合 (します。CRT のセクションでは、読み取り/書き込み)、予期しない現象が発生する可能性があります。

詳細については、次のトピックを参照してください。

- [/MERGE (セクションのマージ)](../../build/reference/merge-combine-sections.md)

- [コメント (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>例

次の例では、LNK4254 が生成されます。

```
// LNK4254.cpp
// compile with: /W1 /link /WX
// LNK4254 expected
#pragma comment(linker, "/merge:.data=.text")
int main() {}
```