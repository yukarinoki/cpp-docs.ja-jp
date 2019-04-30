---
title: コンパイラ エラー C3904
ms.date: 11/04/2016
f1_keywords:
- C3904
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
ms.openlocfilehash: 4675bf95012c8e6662d7dba281c38ed2d684c448
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406770"
---
# <a name="compiler-error-c3904"></a>コンパイラ エラー C3904

'property_accessor': パラメーター番号を指定する必要があります

パラメーターの数を確認、`get`と`set`ディメンションのプロパティに対してメソッド。

- パラメーターの数、`get`メソッドのプロパティの次元の数と一致またはインデックスのプロパティを 0 にする必要があります。

- パラメーターの数、`set`メソッドは、いずれかを指定する必要があります、プロパティの次元数よりも詳細です。

詳細については、「 [property](../../extensions/property-cpp-component-extensions.md)」を参照してください。

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