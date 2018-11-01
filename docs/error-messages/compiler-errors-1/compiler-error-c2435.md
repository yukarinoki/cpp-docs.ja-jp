---
title: コンパイラ エラー C2435
ms.date: 11/04/2016
f1_keywords:
- C2435
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
ms.openlocfilehash: 5cd7a83575da7ab2a30401406d0c2ccf6c1b603e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438534"
---
# <a name="compiler-error-c2435"></a>コンパイラ エラー C2435

> '*var*': 動的な初期化はマネージド CRT が必要です、/clr:safe でコンパイルできません。

## <a name="remarks"></a>Remarks

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

アプリケーションごとのドメインのグローバル変数の初期化には、CRT を使用してコンパイルが必要です。 `/clr:pure`、これは検証可能なイメージを生成しません。

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