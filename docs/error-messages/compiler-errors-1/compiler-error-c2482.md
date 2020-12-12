---
description: 詳細については、「コンパイラエラー C2482」を参照してください。
title: コンパイラ エラー C2482
ms.date: 09/15/2017
f1_keywords:
- C2482
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
ms.openlocfilehash: 1ffde4d7ea9f4eccdd643b3ac6efe0545775816a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123930"
---
# <a name="compiler-error-c2482"></a>コンパイラ エラー C2482

>'*identifier*': マネージド/WinRT コードでは、' thread ' データの動的な初期化は許可されていません

## <a name="remarks"></a>解説

マネージまたは WinRT コードでは、 [__declspec (スレッド)](../../cpp/thread.md) ストレージクラス修飾子属性または [thread_local](../../cpp/storage-classes-cpp.md#thread_local) ストレージクラス指定子を使用して宣言された変数を、実行時の評価が必要な式で初期化することはできません。 `__declspec(thread)`これらのランタイム環境で、またはデータを初期化するには、静的な式が必要です **`thread_local`** 。

## <a name="example"></a>例

次の例では、マネージ (**/clr**) コードと WinRT (**/ZW**) コードで C2482 が生成されます。

```cpp
// C2482.cpp
// For managed example, compile with: cl /EHsc /c /clr C2482.cpp
// For WinRT example, compile with: cl /EHsc /c /ZW C2482.cpp
#define Thread __declspec( thread )
Thread int tls_i1 = tls_i1;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i2 = sizeof( tls_i2 );   // Okay in C and C++
```

この問題を解決するには、定数、 **`constexpr`** 、または静的な式を使用して、スレッドローカルストレージを初期化します。 スレッド固有の初期化は、個別に実行します。
