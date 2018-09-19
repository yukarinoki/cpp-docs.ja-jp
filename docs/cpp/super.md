---
title: _ _super |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __super_cpp
dev_langs:
- C++
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db00272a6fa779458871814bd51ccab7b3e309c6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040169"
---
# <a name="super"></a>__super

**Microsoft 固有の仕様**

オーバーライドする関数について、基底クラス実装を呼び出すことを明示できます。

## <a name="syntax"></a>構文

```
__super::member_function();
```

## <a name="remarks"></a>Remarks

オーバーロード解決フェーズ時にすべてのアクセス可能な基底クラス メソッドが考慮され、最優先の一致を示す関数が呼び出されます。

**_ _super**メンバー関数の本体でのみ表示できます。

**_ _super**を使用してでは使用できません宣言します。 参照してください[宣言を使用して](../cpp/using-declaration.md)詳細についてはします。

導入に伴い[属性](../windows/cpp-attributes-reference.md)コードを挿入する、コードには、名前がわからないに呼び出すメソッドを含む 1 つまたは複数の基底クラスが含まれます。

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