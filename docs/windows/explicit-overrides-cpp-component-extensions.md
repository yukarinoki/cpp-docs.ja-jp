---
title: 明示的なオーバーライド (C +/cli および C++/cli CX) |Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, override [C++]
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 689c8420c2526f94f88c8b2ba8433c2310281874
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328039"
---
# <a name="explicit-overrides--ccli-and-ccx"></a>明示的なオーバーライド (C +/cli および C++/cli CX)

このトピックでは、基底クラスまたはインターフェイスのメンバーを明示的にオーバーライドする方法について説明します。 (明示的) の名前付きオーバーライドを別の名前を持つ派生メソッドを使用してメソッドをオーバーライドする場合にのみ使用する必要があります。

## <a name="all-runtimes"></a>すべてのランタイム

### <a name="syntax"></a>構文

```cpp
overriding-function-declarator = type::function [,type::function] { overriding-function-definition }
overriding-function-declarator = function { overriding-function-definition }
```

### <a name="parameters"></a>パラメーター

*オーバーライドする関数宣言*<br/>
オーバーライド関数の戻り値の型、名、および引数リスト。  オーバーライドされる関数と同じ名前を指定する、オーバーライドする関数がないことに注意してください。

*type*<br/>
オーバーライドする関数を含む基本型。

*function*<br/>
オーバーライドする 1 つまたは複数の関数名のコンマ区切りのリスト。

*オーバーライドする関数定義*<br/>
オーバーライドする関数を定義する関数本体のステートメント。

### <a name="remarks"></a>Remarks

明示的な使用には、メソッドのシグネチャのエイリアスを作成する、またはメソッドで、同じシグネチャのさまざまな実装を提供するよりも優先されます。

継承された型および継承された型のメンバーの動作を変更する方法の詳細については、次を参照してください。[オーバーライド指定子を](../windows/override-specifiers-cpp-component-extensions.md)します。

## <a name="windows-runtime"></a>Windows ランタイム

### <a name="requirements"></a>要件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

### <a name="remarks"></a>Remarks

ネイティブ コードでの情報について明示的なオーバーライドまたはコードをコンパイル`/clr:oldSyntax`を参照してください[明示的なオーバーライド](../cpp/explicit-overrides-cpp.md)します。

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`

### <a name="examples"></a>使用例

次のコード例は、基本インターフェイスでの単純な明示的なオーバーライドとメンバーの実装を示しています明示的なオーバーライドを使用していないを提供します。

```cpp
// explicit_override_1.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

ref class X : public I1 {
public:
   virtual void f() {
      System::Console::WriteLine("X::f override of I1::f");
   }
};

int main() {
   I1 ^ MyI = gcnew X;
   MyI -> f();
}
```

```Output
X::f override of I1::f
```

次のコード例では、すべてのインターフェイス メンバー一般的なシグネチャを持つが明示的なオーバーライド構文を使用して実装する方法を示します。

```cpp
// explicit_override_2.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

interface struct I2 {
   virtual void f();
};

ref struct X : public I1, I2 {
   virtual void f() = I1::f, I2::f {
      System::Console::WriteLine("X::f override of I1::f and I2::f");
   }
};

int main() {
   I1 ^ MyI = gcnew X;
   I2 ^ MyI2 = gcnew X;
   MyI -> f();
   MyI2 -> f();
}
```

```Output
X::f override of I1::f and I2::f
X::f override of I1::f and I2::f
```

次のコード例では、関数のオーバーライドが実装しています。 関数とは異なる名前を持つことができる方法を示します。

```cpp
// explicit_override_3.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

ref class X : public I1 {
public:
   virtual void g() = I1::f {
      System::Console::WriteLine("X::g");
   }
};

int main() {
   I1 ^ a = gcnew X;
   a->f();
}
```

```Output
X::g
```

次のコード例では、タイプ セーフのコレクションを実装する明示的なインターフェイス実装を示します。

```cpp
// explicit_override_4.cpp
// compile with: /clr /LD
using namespace System;
ref class R : ICloneable {
   int X;

   virtual Object^ C() sealed = ICloneable::Clone {
      return this->Clone();
   }

public:
   R() : X(0) {}
   R(int x) : X(x) {}

   virtual R^ Clone() {
      R^ r = gcnew R;
      r->X = this->X;
      return r;
   }
};
```

## <a name="see-also"></a>関連項目

[Component Extensions for .NET と UWP](../windows/component-extensions-for-runtime-platforms.md)