---
description: 詳細については、「User-Defined 演算子 (C++/CLI)」を参照してください。
title: ユーザー定義の演算子 (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined operators under /clr
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
ms.openlocfilehash: e94a4d28517fc253fb8284a604b01a5f9d76de22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204226"
---
# <a name="user-defined-operators-ccli"></a>ユーザー定義の演算子 (C++/CLI)

マネージ型のユーザー定義演算子は、静的メンバーまたはインスタンスメンバーとして、またはグローバルスコープで許可されます。 ただし、Visual C++ 以外の言語で記述されたクライアントに対してメタデータを使用してアクセスできるのは、静的演算子だけです。

参照型では、静的なユーザー定義演算子のパラメーターの1つは次のいずれかである必要があります。

- `type`外側の型のインスタンスへのハンドル (^)。

- 参照型の間接参照 ( `type` ^& または型 ^%)外側の型のインスタンスへのハンドル。

値型では、静的なユーザー定義演算子のパラメーターの1つに、次のいずれかの値を指定する必要があります。

- 外側の値の型と同じ型の。

- 外側の型へのポインター型の間接参照 ( `type` ^)。

- 外側の型への参照型の間接参照 ( `type` % または `type`&)。

- ハンドルへの参照型の間接参照 ( `type` ^% または `type` ^&)。

次の演算子を定義できます。

|演算子|単項/バイナリ形式?|
|--------------|--------------------------|
|!|単項|
|!=|Binary|
|%|Binary|
|&|単項演算子および 2 項演算子|
|&&|2 項|
|*|単項演算子および 2 項演算子|
|+|単項演算子および 2 項演算子|
|++|単項|
|,|2 項|
|-|単項演算子および 2 項演算子|
|--|単項|
|->|単項|
|/|Binary|
|<|Binary|
|<<|Binary|
|\<=|Binary|
|=|Binary|
|==|Binary|
|>|Binary|
|>=|Binary|
|>>|Binary|
|^|Binary|
|false|単項|
|true|単項|
|&#124;|2 項|
|&#124;&#124;|2 項|
|~|単項|

## <a name="example-user-defined-operators"></a>例: ユーザー定義の演算子

```cpp
// mcppv2_user-defined_operators.cpp
// compile with: /clr
using namespace System;
public ref struct X {
   X(int i) : m_i(i) {}
   X() {}

   int m_i;

   // static, binary, user-defined operator
   static X ^ operator + (X^ me, int i) {
      return (gcnew X(me -> m_i + i));
   }

   // instance, binary, user-defined operator
   X^ operator -( int i ) {
      return gcnew X(this->m_i - i);
   }

   // instance, unary, user-defined pre-increment operator
   X^ operator ++() {
      return gcnew X(this->m_i++);
   }

   // instance, unary, user-defined post-increment operator
   X^ operator ++(int i) {
      return gcnew X(this->m_i++);
   }

   // static, unary user-defined pre- and post-increment operator
   static X^ operator-- (X^ me) {
      return (gcnew X(me -> m_i - 1));
   }
};

int main() {
   X ^hX = gcnew X(-5);
   System::Console::WriteLine(hX -> m_i);

   hX = hX + 1;
   System::Console::WriteLine(hX -> m_i);

   hX = hX - (-1);
   System::Console::WriteLine(hX -> m_i);

   ++hX;
   System::Console::WriteLine(hX -> m_i);

   hX++;
   System::Console::WriteLine(hX -> m_i);

   hX--;
   System::Console::WriteLine(hX -> m_i);

   --hX;
   System::Console::WriteLine(hX -> m_i);
}
```

```Output
-5
-4
-3
-2
-1
-2
-3
```

## <a name="example-operator-synthesis"></a>例: 演算子合成

次のサンプルは、 **/clr** を使用してコンパイルする場合にのみ使用できる演算子合成を示しています。 演算子合成は、二項演算子が定義されていない場合、代入形式を作成します (代入演算子の左辺に CLR 型がある場合)。

```cpp
// mcppv2_user-defined_operators_2.cpp
// compile with: /clr
ref struct A {
   A(int n) : m_n(n) {};
   static A^ operator + (A^ r1, A^ r2) {
      return gcnew A( r1->m_n + r2->m_n);
   };
   int m_n;
};

int main() {
   A^ a1 = gcnew A(10);
   A^ a2 = gcnew A(20);

   a1 += a2;   // a1 = a1 + a2   += not defined in source
   System::Console::WriteLine(a1->m_n);
}
```

```Output
30
```

## <a name="see-also"></a>関連項目

[クラスと構造体](../extensions/classes-and-structs-cpp-component-extensions.md)
