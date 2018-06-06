---
title: コンパイラ エラー C3278 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3278
dev_langs:
- C++
helpviewer_keywords:
- C3278
ms.assetid: 56f818f5-85a6-4792-843b-54fe16327658
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b993aaaee0e50eacf47ce594b4c5efa47f83dd18
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705076"
---
# <a name="compiler-error-c3278"></a>コンパイラ エラー C3278

> インターフェイス メソッドまたはピュア メソッドの呼び出しを直接 '*メソッド*' は、実行時に失敗

## <a name="remarks"></a>コメント

インターフェイス メソッドまたはピュア メソッドが呼び出されましたが、このような呼び出しは許可されていません。

## <a name="example"></a>例

次の例では C3278 が生成されます。

```cpp
// C3278_2.cpp
// compile with: /clr
using namespace System;
interface class I
{
   void vmf();
};

public ref class C: public I
{
public:
   void vmf()
   {
      Console::WriteLine( "In C::vmf()" );
      I::vmf(); // C3278
   }

};

int main()
{
   C^ pC = gcnew C;
   pC->vmf();
}
```