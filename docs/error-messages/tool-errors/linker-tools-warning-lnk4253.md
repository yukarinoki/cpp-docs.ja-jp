---
description: 詳細については、「リンカーツールの警告 LNK4253」を参照してください。
title: リンカー ツールの警告 LNK4253
ms.date: 11/04/2016
f1_keywords:
- LNK4253
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
ms.openlocfilehash: 764d7698da8d724842b8387c9c4356bfce951079
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244486"
---
# <a name="linker-tools-warning-lnk4253"></a>リンカー ツールの警告 LNK4253

セクション ' section1 ' は ' section2 ' にマージされていません。' section3 ' に既にマージされています

リンカーが複数の競合するマージ要求を検出しました。 リンカーは、要求の1つを無視します。

前 **の** `from` **/merge** オプションまたはディレクティブ (またはリンカーからの暗黙的なマージにより) が発生したため、このセクションは既に別のセクションにマージされています。

LNK4253 を解決するには、いずれかのマージ要求を削除します。

Visual C++ で x86 マシンと Windows CE ターゲット (ARM、MIPS、SH4、Thumb) を対象とする場合は、「」を使用します。CRT セクションが読み取り専用になりました。 コードが以前の動作 () に依存している場合は。CRT セクションは読み取り/書き込み)、予期しない動作が発生する可能性があります。

詳細については、次のトピックを参照してください。

- [/MERGE (セクションの結合)](../../build/reference/merge-combine-sections.md)

- [コメント (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>例

次の例では、 `.rdata` セクションを2回、異なるセクションにマージするようにリンカーに指示しています。 次の例では、LNK4253 が生成されます。

```cpp
// LNK4253.cpp
// compile with: /W1 /link /merge:.rdata=text2
// LNK4253 expected
#pragma comment(linker, "/merge:.rdata=.text")
int main() {}
```
