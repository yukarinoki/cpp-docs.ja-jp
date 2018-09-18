---
title: リンカー ツールの警告 LNK4253 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4253
dev_langs:
- C++
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d26d688825f504cbce8224adc9a5766a555d2fc8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016820"
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