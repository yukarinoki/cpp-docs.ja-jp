---
description: 詳細については、「コンパイラエラー C3772」を参照してください。
title: コンパイラ エラー C3772
ms.date: 11/04/2016
f1_keywords:
- C3772
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
ms.openlocfilehash: 679c5bc47e9b31ebf085dec63a46549a10484cac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340126"
---
# <a name="compiler-error-c3772"></a>コンパイラ エラー C3772

"name" : 無効なフレンド テンプレートの宣言

クラス テンプレートの特殊化のフレンドを宣言することは無効です。 クラス テンプレートの明示的または部分的な特殊化を宣言し、同じステートメントでその特殊化のフレンドを宣言することはできません。 *name* プレースホルダーは、無効な宣言を識別します。

### <a name="to-correct-this-error"></a>このエラーを解決するには

- クラス テンプレートの特殊化のフレンドを宣言しません。

- アプリケーションに適切な場合は、クラス テンプレートのフレンドを宣言するか、特定の部分的または明示的な特殊化のフレンドを宣言します。

## <a name="example"></a>例

次のコード例は、クラス テンプレートの部分的特殊化のフレンドを宣言しているため、失敗します。

```cpp
// c3772.cpp
// compile with: /c

// A class template.
    template<class T> class A {};

// A partial specialization of the class template.
    template<class T> class A<T*> {};

// An explicit specialization.
    template<> class A<char>;

class X {
// Invalid declaration of a friend of a partial specialization.
    template<class T> friend class A<T*>; // C3772

// Instead, if it is appropriate for your application, declare a
// friend of the class template. Consequently, all specializations
// of the class template are friends:
//    template<class T> friend class A;
// Or declare a friend of a particular partial specialization:
//    friend class A<int*>;
// Or declare a friend of a particular explicit specialization:
//    friend class A<char>;
};
```

## <a name="see-also"></a>関連項目

[テンプレート](../../cpp/templates-cpp.md)<br/>
[テンプレートの特殊化](../../cpp/template-specialization-cpp.md)
