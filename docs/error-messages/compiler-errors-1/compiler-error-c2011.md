---
title: コンパイラ エラー C2011
ms.date: 11/04/2016
f1_keywords:
- C2011
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
ms.openlocfilehash: 14969c9cdf4b00844d2001bf4817ea7ffc9bfba6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361556"
---
# <a name="compiler-error-c2011"></a>コンパイラ エラー C2011

'identifier' : 'type' 型の再定義

この識別子は、既に `type` として定義されています。 識別子の再定義をチェックします。

ヘッダー ファイルまたはタイプ ライブラリを同じファイルに 2 回以上インポートすると、C2011 が生成される場合もあります。 ヘッダー ファイルで定義された型の複数回のインクルードを防ぐためには、使用して include guard または`#pragma`[したら](../../preprocessor/once.md)ヘッダー ファイルでディレクティブ。

使用することができます、再定義された型の最初の宣言を検索する必要がある場合、 [/P](../../build/reference/p-preprocess-to-a-file.md)前処理済み出力を生成するコンパイラ フラグは、コンパイラに渡されます。 テキスト検索ツールを使用して、出力ファイル内の再定義された識別子のインスタンスを見つけることができます。

次の例では、C2011 を生成し、その修正方法を示しています。

```
// C2011.cpp
// compile with: /c
struct S;
union S;   // C2011
union S2;   // OK
```