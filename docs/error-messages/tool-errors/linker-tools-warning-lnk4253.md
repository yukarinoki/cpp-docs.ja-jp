---
title: リンカー ツールの警告 LNK4253
ms.date: 11/04/2016
f1_keywords:
- LNK4253
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
ms.openlocfilehash: d2fd7238a3f57b11b91813bd40b66cb3e9f47202
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628827"
---
# <a name="linker-tools-warning-lnk4253"></a>リンカー ツールの警告 LNK4253

セクション '「section1」' 'セクション 2'; にマージされていないセクション '3' に既にマージ

リンカーが複数検出された競合のマージを要求します。 リンカーは、要求の 1 つでは無視します。

A **/merge**オプションまたはディレクティブが検出された、`from`セクションは既に別のセクションにより、以前にマージされました **/merge**オプションまたはディレクティブ (またはからの暗黙的なマージのためリンカー)。

LNK4253 を解決するには、マージ要求の 1 つを削除します。

X86 を対象とするときにマシンと Windows CE ターゲット (ARM、MIPS、SH4、およびつまみ) Visual c にします。CRT セクションはこれで読み取り専用です。 コードは、以前の動作に依存している場合 (します。CRT のセクションでは、読み取り/書き込み)、予期しない現象が発生する可能性があります。

詳細については、次のトピックを参照してください。

- [/MERGE (セクションのマージ)](../../build/reference/merge-combine-sections.md)

- [コメント (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>例

次の例では、リンカーはマージするように指示、`.rdata`セクション 2 回ではなくさまざまなセクションです。 次の例では、LNK4253 が生成されます。

```
// LNK4253.cpp
// compile with: /W1 /link /merge:.rdata=text2
// LNK4253 expected
#pragma comment(linker, "/merge:.rdata=.text")
int main() {}
```