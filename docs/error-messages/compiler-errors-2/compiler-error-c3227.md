---
description: 詳細については、「コンパイラエラー C3227」を参照してください。
title: コンパイラ エラー C3227
ms.date: 11/04/2016
f1_keywords:
- C3227
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
ms.openlocfilehash: 26d66bf3e0c3bc3a6f391d66608f3e6790b2d11d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304143"
---
# <a name="compiler-error-c3227"></a>コンパイラ エラー C3227

' parameter ': ジェネリック型を割り当てるために ' keyword ' を使用することはできません

型をインスタンス化するには、適切なコンストラクターが必要です。 ただし、コンパイラは適切なコンストラクターが使用可能であることを確認できません。

ジェネリックではなくテンプレートを使用してこのエラーを解決することも、複数のメソッドのいずれかを使用して型のインスタンスを作成することもできます。

## <a name="example"></a>例

次の例では、C3227 が生成されます。

```cpp
// C3227.cpp
// compile with: /clr /c
generic<class T> interface class ICreate {
   static T Create();
};

generic <class T>
where T : ICreate<T>
ref class C {
   void f() {
      T t = new T;   // C3227

      // OK
      T t2 = ICreate<T>::Create();
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );
   }
};
```
