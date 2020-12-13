---
description: 詳細については、「コンパイラエラー C3904」を参照してください。
title: コンパイラ エラー C3904
ms.date: 11/04/2016
f1_keywords:
- C3904
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
ms.openlocfilehash: 0b1564e609586318d23b4204242f0cb39034c4fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144184"
---
# <a name="compiler-error-c3904"></a>コンパイラ エラー C3904

' property_accessor ': 数値パラメーターを指定しなければなりません

`get`プロパティディメンションに対して、およびメソッドのパラメーターの数を確認し `set` ます。

- メソッドのパラメーターの数は、 `get` プロパティの次元数と同じであるか、またはインデックスが設定されていないプロパティの場合は0である必要があります。

- メソッドのパラメーターの数は、 `set` プロパティの次元数より1つ多くする必要があります。

詳細については、「 [property](../../extensions/property-cpp-component-extensions.md)」を参照してください。

## <a name="examples"></a>例

次の例では、C3904 が生成されます。

```cpp
// C3904.cpp
// compile with: /clr /c
ref class X {
   property int P {
      // set
      void set();   // C3904
      // try the following line instead
      // void set(int);

      // get
      int get(int, int);   // C3904
      // try the following line instead
      // int get();
   };
};
```

次の例では、C3904 が生成されます。

```cpp
// C3904b.cpp
// compile with: /clr /c
ref struct X {
   property int Q[double, double, float, float, void*, int] {
      // set
      void set(double, void*);   // C3904
      // try the following line instead
      // void set(double, double, float, float, void*, int, int);

      // get
      int get();   // C3904
      // try the following line instead
      // int get(double, double, float, float, void*, int);
   }
};
```
