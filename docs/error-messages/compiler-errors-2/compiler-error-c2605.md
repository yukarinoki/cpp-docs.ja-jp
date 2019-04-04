---
title: コンパイラ エラー C2605
ms.date: 11/04/2016
f1_keywords:
- C2605
helpviewer_keywords:
- C2605
ms.assetid: a0e6f132-5acf-4e19-b277-ddf196d182bf
ms.openlocfilehash: c1a3f1132edb90e119d97061fbbfb293d364ef3a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676266"
---
# <a name="compiler-error-c2605"></a>コンパイラ エラー C2605

'name': このメソッドは、マネージド クラスまたは WinRT クラスで予約されています

内部関数用に、いくつかの名前がコンパイラによって予約されています。  詳細については、[デストラクターおよびファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)を参照してください。

## <a name="example"></a>例

次の例では C2605 が生成されます。

```
// C2605.cpp
// compile with: /clr /c
ref class R {
protected:
   void Finalize() {}   // C2605
};
```