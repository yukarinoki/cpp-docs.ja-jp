---
description: 詳細については、「コンパイラエラー C2435」を参照してください。
title: コンパイラ エラー C2435
ms.date: 11/04/2016
f1_keywords:
- C2435
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
ms.openlocfilehash: d0ab5d8c7c45c9636a5e48acc17d3ac379c755a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189939"
---
# <a name="compiler-error-c2435"></a>コンパイラ エラー C2435

> '*var*': 動的な初期化にはマネージ CRT が必要です。/clr: safe を使用してコンパイルすることはできません。

## <a name="remarks"></a>解説

**/Clr: pure** および **/clr: safe** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

グローバルなアプリケーションごとのドメイン変数を初期化するには、でコンパイルされた CRT が必要です `/clr:pure` 。これは検証可能なイメージを生成しません。

詳細については、「 [appdomain](../../cpp/appdomain.md) 」および「 [process](../../cpp/process.md)」を参照してください。

## <a name="example"></a>例

次の例では、C2435 が生成されます。

```cpp
// C2435.cpp
// compile with: /clr:safe /c
int globalvar = 0;   // C2435

__declspec(process)
int globalvar2 = 0;
```
