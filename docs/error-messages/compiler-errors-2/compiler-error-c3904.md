---
title: コンパイラ エラー C3904
ms.date: 11/04/2016
f1_keywords:
- C3904
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
ms.openlocfilehash: 8c7f4a2861825a35d676328b5e283a5e4087d85b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519783"
---
# <a name="compiler-error-c3904"></a>コンパイラ エラー C3904

'property_accessor': パラメーター番号を指定する必要があります

パラメーターの数を確認、`get`と`set`ディメンションのプロパティに対してメソッド。

- パラメーターの数、`get`メソッドのプロパティの次元の数と一致またはインデックスのプロパティを 0 にする必要があります。

- パラメーターの数、`set`メソッドは、いずれかを指定する必要があります、プロパティの次元数よりも詳細です。

詳細については、「 [property](../../windows/property-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3904 が生成されます。

```
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

## <a name="example"></a>例

次の例では、C3904 が生成されます。

```
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