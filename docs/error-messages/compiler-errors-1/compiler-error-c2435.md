---
title: コンパイラ エラー C2435
ms.date: 11/04/2016
f1_keywords:
- C2435
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
ms.openlocfilehash: 7ef22711884dabb83efa8c7ebfdb7648316c12ee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205414"
---
# <a name="compiler-error-c2435"></a>コンパイラ エラー C2435

> '*var*': 動的な初期化にはマネージ CRT が必要です。/clr: safe を使用してコンパイルすることはできません。

## <a name="remarks"></a>解説

**/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

グローバルなアプリケーションごとのドメイン変数を初期化するには、`/clr:pure`でコンパイルされた CRT が必要です。これは検証可能なイメージを生成しません。

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
