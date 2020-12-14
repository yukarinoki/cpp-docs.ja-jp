---
description: 詳細については、「コンパイラエラー C2011」を参照してください。
title: コンパイラエラー C2011
ms.date: 11/04/2016
f1_keywords:
- C2011
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
ms.openlocfilehash: c310495c570a2259cf5abe6acea951ca996bfb26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221021"
---
# <a name="compiler-error-c2011"></a>コンパイラエラー C2011

'identifier' : 'type' 型の再定義

この識別子は、既に `type` として定義されています。 識別子の再定義をチェックします。

ヘッダー ファイルまたはタイプ ライブラリを同じファイルに 2 回以上インポートすると、C2011 が生成される場合もあります。 ヘッダーファイルで複数の型が定義されていないようにするには、ヘッダーファイルで include ガードまたは `#pragma` [once](../../preprocessor/once.md)ディレクティブを使用します。

再定義された型の初期宣言を検索する必要がある場合は、 [/p](../../build/reference/p-preprocess-to-a-file.md) コンパイラフラグを使用して、コンパイラに渡されるプリプロセスされた出力を生成できます。 テキスト検索ツールを使用して、出力ファイル内の再定義された識別子のインスタンスを見つけることができます。

次の例では、C2011 を生成し、その修正方法を示しています。

```cpp
// C2011.cpp
// compile with: /c
struct S;
union S;   // C2011
union S2;   // OK
```
