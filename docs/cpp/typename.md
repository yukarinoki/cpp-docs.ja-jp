---
title: typename
ms.date: 11/04/2016
f1_keywords:
- typename_cpp
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
ms.openlocfilehash: 62e8a2026babbfea3cd1583def05a03b4bc4a229
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223513"
---
# <a name="typename"></a>typename

テンプレート定義では、不明な識別子が型であることをコンパイラにヒントとして示します。 テンプレートパラメーターリストでは、を使用して型パラメーターを指定します。

## <a name="syntax"></a>構文

```
typename identifier;
```

## <a name="remarks"></a>解説

テンプレート定義内の名前がテンプレート引数に依存する修飾名である場合は、このキーワードを使用する必要があります。修飾名が依存していない場合は省略可能です。 詳細については、「[テンプレートと名前解決](../cpp/templates-and-name-resolution.md)」を参照してください。

**`typename`** テンプレート宣言または定義内の任意の型で使用できます。 テンプレート基底クラスへのテンプレート引数として使用する場合を除いて、このキーワードを基底クラス リストで使用することはできません。

```cpp
template <class T>
class C1 : typename T::InnerType // Error - typename not allowed.
{};
template <class T>
class C2 : A<typename T::InnerType>  // typename OK.
{};
```

キーワードは、 **`typename`** **`class`** テンプレートパラメーターリストでの代わりに使用することもできます。 たとえば、次のステートメントは意味的に等価です。

```cpp
template<class T1, class T2>...
template<typename T1, typename T2>...
```

## <a name="example"></a>例

```cpp
// typename.cpp
template<class T> class X
{
   typename T::Y m_y;   // treat Y as a type
};

int main()
{
}
```

## <a name="see-also"></a>関連項目

[テンプレート](../cpp/templates-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
