---
title: 変更可能なデータ メンバー (C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: db3a9594a77a9ada971213eaea74a9842bd96a54
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179342"
---
# <a name="mutable-data-members-c"></a>変更可能なデータ メンバー (C++)

このキーワードは、クラスの non-static データ メンバーおよび non-const データ メンバーにのみ適用できます。 データメンバーが**mutable**と宣言されている場合は、 **const**メンバー関数からこのデータメンバーに値を割り当てることができます。

## <a name="syntax"></a>構文

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>解説

たとえば、次のコードはエラーなしでコンパイルされます。 `m_accessCount` は変更**可能と**して宣言されているため、`GetFlag` が const メンバー関数であっても `GetFlag` によって変更できます。

```cpp
// mutable.cpp
class X
{
public:
   bool GetFlag() const
   {
      m_accessCount++;
      return m_flag;
   }
private:
   bool m_flag;
   mutable int m_accessCount;
};

int main()
{
}
```

## <a name="see-also"></a>参照

[キーワード](../cpp/keywords-cpp.md)
