---
title: new (新規のスロット vtable) (C +/cli および C++/cli CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
ms.openlocfilehash: 852538396627a3005fe20a2e66bbb6995842e4a9
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422274"
---
# <a name="new-new-slot-in-vtable--ccli-and-ccx"></a>new (新規のスロット vtable) (C +/cli および C++/cli CX)

**新しい**キーワードは、仮想メンバーが vtable の新しいスロットを取得することを示します。

## <a name="all-runtimes"></a>すべてのランタイム

(この言語機能にはランタイムに適用される特記事項がありません。)

## <a name="windows-runtime"></a>Windows ランタイム

Windows ランタイムでサポートされていません。

## <a name="common-language-runtime"></a>共通言語ランタイム

### <a name="remarks"></a>Remarks

`/clr`コンパイル、**新しい**仮想メンバーが vtable の新しいスロットを取得するは、関数が基底クラスのメソッドをオーバーライドしていないことを示します。

**新しい**により、関数の IL に追加する newslot 修飾子。  newslot の詳細については、次のトピックを参照してください。

- <xref:System.Reflection.MethodInfo.GetBaseDefinition?displayProperty=nameWithType>

- <xref:System.Reflection.MethodAttributes?displayProperty=nameWithType>

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/clr`

### <a name="examples"></a>使用例

次の例は、の効果を示しています。**新しい**します。

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

## <a name="see-also"></a>関連項目

[.NET および UWP でのコンポーネント拡張](../windows/component-extensions-for-runtime-platforms.md)<br/>

[オーバーライド指定子](../windows/override-specifiers-cpp-component-extensions.md)