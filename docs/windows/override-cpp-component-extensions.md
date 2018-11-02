---
title: オーバーライド (C +/cli および C++/cli CX)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
ms.openlocfilehash: be7a347e4ddc700acaf4c5a968af648195445485
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647370"
---
# <a name="override--ccli-and-ccx"></a>オーバーライド (C +/cli および C++/cli CX)

**オーバーライド**状況依存のキーワードは、型のメンバーが基底クラスまたは基本インターフェイスのメンバーをオーバーライドすることを示します。

## <a name="remarks"></a>Remarks

**オーバーライド**キーワードは、ネイティブ ターゲット (既定のコンパイラ オプション) をコンパイルするときに有効な Windows ランタイム ターゲット (`/ZW`コンパイラ オプション)、または共通言語ランタイム ターゲット (`/clr`コンパイラ オプション)。

オーバーライド指定子の詳細については、次を参照してください。[オーバーライド指定子](../cpp/override-specifier.md)と[オーバーライド指定子とネイティブ コンパイル](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)します。

状況依存のキーワードの詳細については、次を参照してください。[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)します。

## <a name="examples"></a>使用例

コード例を次に示します**オーバーライド**ネイティブ コンパイルでも使用できます。

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

コード例を次に示します**オーバーライド**Windows ランタイム コンパイルで使用できます。

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

コード例を次に示します**オーバーライド**共通言語ランタイム コンパイルで使用できます。

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

## <a name="see-also"></a>関連項目

[override 指定子](../cpp/override-specifier.md)<br/>
[オーバーライド指定子](../windows/override-specifiers-cpp-component-extensions.md)