---
title: override (C++/CLI および C++/CX)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
ms.openlocfilehash: 32c825539efe670528eab7416afefe07d4cb1b6c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172101"
---
# <a name="override--ccli-and-ccx"></a>override (C++/CLI および C++/CX)

状況依存の **override** キーワードは、型のメンバーが基底クラスまたは基底インターフェイスのメンバーをオーバーライドすることを示します。

## <a name="remarks"></a>解説

**override** キーワードは、ネイティブ ターゲット (既定のコンパイラ オプション)、Windows ランタイム ターゲット (`/ZW` コンパイラ オプション)、または共通言語ランタイム ターゲット (`/clr` コンパイラ オプション) に対するコンパイル時に有効です。

オーバーライド指定子の詳細については、「[override 指定子](../cpp/override-specifier.md)」と「[override 指定子とネイティブ コンパイル](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)」を参照してください。

状況依存キーワードの詳細については、「[状況依存キーワード](context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。

## <a name="examples"></a>例

次のコード例に、**override** をネイティブ コンパイルでも使用できることを示します。

```cpp
// override_keyword_1.cpp
// compile with: /c
struct I1 {
   virtual void f();
};

struct X : public I1 {
   virtual void f() override {}
};
```

### <a name="example"></a>例

次のコード例に、Windows ランタイムのコンパイルに **override** を使用できることを示します。

```cpp
// override_keyword_2.cpp
// compile with: /ZW /c
ref struct I1 {
   virtual void f();
};

ref struct X : public I1 {
   virtual void f() override {}
};
```

#### <a name="requirements"></a>必要条件

コンパイラ オプション: `/ZW`

### <a name="example"></a>例

次のコード例に、共通言語ランタイムのコンパイルに **override** を使用できることを示します。

```cpp
// override_keyword_3.cpp
// compile with: /clr /c
ref struct I1 {
   virtual void f();
};

ref struct X : public I1 {
   virtual void f() override {}
};
```

#### <a name="requirements"></a>必要条件

コンパイラ オプション: `/clr`

## <a name="see-also"></a>参照

[override 指定子](../cpp/override-specifier.md)<br/>
[オーバーライド指定子](override-specifiers-cpp-component-extensions.md)
