---
title: new (vtable の新しいスロット) (C++/CLI および C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
ms.openlocfilehash: 684c6149457f7b0306f3d444a3652ecda1636839
ms.sourcegitcommit: 8bb2bea1384b290b7570b01608a86c7488ae7a02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2019
ms.locfileid: "79544412"
---
# <a name="new-new-slot-in-vtable--ccli-and-ccx"></a>new (vtable の新しいスロット) (C++/CLI および C++/CX)

**new** キーワードは、仮想メンバーが vtable の新しいスロットを取得することを示します。

## <a name="all-runtimes"></a>すべてのランタイム

(この言語機能にはランタイムに適用される特記事項がありません。)

## <a name="windows-runtime"></a>Windows ランタイム

Windows ランタイムではサポートされません。

## <a name="common-language-runtime"></a>共通言語ランタイム

### <a name="remarks"></a>コメント

`/clr` のコンパイルでは、**new** は、仮想メンバーが vtable の新しいスロットを取得することを示します。つまり、関数で基底クラスのメソッドをオーバーライドしません。

**new** を指定すると、関数の IL に newslot 修飾子が追加されます。  newslot の詳細については、次のトピックを参照してください。

- <xref:System.Reflection.MethodInfo.GetBaseDefinition?displayProperty=nameWithType>

- <xref:System.Reflection.MethodAttributes?displayProperty=nameWithType>

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`

### <a name="examples"></a>例

**new** の効果の例を次に示します。

```cpp
// newslot.cpp
// compile with: /clr
ref class C {
public:
   virtual void f() {
      System::Console::WriteLine("C::f() called");
   }

   virtual void g() {
      System::Console::WriteLine("C::g() called");
   }
};

ref class D : public C {
public:
   virtual void f() new {
      System::Console::WriteLine("D::f() called");
   }

   virtual void g() override {
      System::Console::WriteLine("D::g() called");
   }
};

ref class E : public D {
public:
   virtual void f() override {
      System::Console::WriteLine("E::f() called");
   }
};

int main() {
   D^ d = gcnew D;
   C^ c = gcnew D;

   c->f();   // calls C::f
   d->f();   // calls D::f

   c->g();   // calls D::g
   d->g();   // calls D::g

   D ^ e = gcnew E;
   e->f();   // calls E::f
}
```

```Output
C::f() called

D::f() called

D::g() called

D::g() called

E::f() called
```

## <a name="see-also"></a>参照

[.NET および UWP でのコンポーネント拡張](component-extensions-for-runtime-platforms.md)<br/>
[オーバーライド指定子](override-specifiers-cpp-component-extensions.md)
