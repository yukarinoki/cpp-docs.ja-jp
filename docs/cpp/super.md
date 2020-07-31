---
title: __super
ms.date: 11/04/2016
f1_keywords:
- __super_cpp
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
ms.openlocfilehash: 3afc2e8049cfcca40db389bed84baa6f42dae126
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213152"
---
# `__super`

**Microsoft 固有の仕様**

オーバーライドする関数について、基底クラス実装を呼び出すことを明示できます。

## <a name="syntax"></a>構文

```
__super::member_function();
```

## <a name="remarks"></a>解説

オーバーロード解決フェーズ時にすべてのアクセス可能な基底クラス メソッドが考慮され、最優先の一致を示す関数が呼び出されます。

**`__super`** は、メンバー関数の本体内でのみ使用できます。

**`__super`** using 宣言と共に使用することはできません。 詳細については、「 [Using 宣言」を](../cpp/using-declaration.md)参照してください。

コードを挿入する[属性](../windows/attributes/attributes-alphabetical-reference.md)の導入により、コードには既知の名前ではないが、呼び出すメソッドを含む1つ以上の基底クラスが含まれている場合があります。

## <a name="example"></a>例

```cpp
// deriv_super.cpp
// compile with: /c
struct B1 {
   void mf(int) {}
};

struct B2 {
   void mf(short) {}

   void mf(char) {}
};

struct D : B1, B2 {
   void mf(short) {
      __super::mf(1);   // Calls B1::mf(int)
      __super::mf('s');   // Calls B2::mf(char)
   }
};
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)
